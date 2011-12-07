--- 
layout: post
title: Introducing Skeletor and Grayskull
categories:
- Ruby
- Gems
tags: 
- gems
- json
- ruby
- skeleton
- templates
- validation
- yaml
status: publish
type: post
published: true
---

So this month I've been playing with something new... again (I'm going through an experimental phase I guess). This month it was Ruby, or more specifically Ruby Gems. I've used Ruby a little in the Rakefiles I 
use for building my javascript projects but not really done any major work with it, until now.

I've been trying to find a nice simple solution for setting up my project skeletons quickly and easily. I'd thought of some sort of Git repository but then I'd end up with some faffy process involving multiple 
branches for different project types and having to clone a repository and then remove the git repository in the newly cloned folder and well, this didn't sound quick or easy. Eventually I hit on the idea of a 
command line ruby gem that could use templates defining a directory structure to set up what I needed. A quick search turned up nothing that seemed to do the job, the closest thing was 
[Mr Bones](https://rubygems.org/gems/bones) but that seemed to be entirely for Ruby projects and the template skeleton wasn't easily customisable.  I was disappointed that it existed though as I wanted to name 
my gem bones but hey, how many things am I going to write that I can actually justify calling Skeletor?

So I started looking into what was involved in creating ruby gems. Initially I started of using [Jeweler](https://github.com/technicalpickles/jeweler) but this created a lot of stuff I didn't really understand 
so I decided to strip everything back and just look at the structure of some gems I already used. My main source of reference was Sprockets but I also used Capistrano when trying to understand the command line 
aspect of the gem. These gave me a good source of reference for what was required in the various gem files.

For anyone who's not created gemfiles before the basic folder structure is as follows:

* lib - contains 1 ruby file with the same name as the gem and a folder also named after the gem which contains all the code for the gem
* bin - optional folder that contains the command line executable files for the gem
* test - contains the unit test files
* a Gemfile that contains the dependencies for the gem
* a.gemspec file that contains the configuration details for building the gem
* the usual README and LICENSE files in your choice of format

I'm not going to go into the details of each of those files.  I'd say the best thing to do is to check out the source of some of the gems that you use and that will probably give you the best understanding of 
what's required. I'm using [Thor](https://github.com/wycats/thor) for the command line interface and [Hike](https://github.com/sstephenson/hike) to locate the files in the 2 possible load paths.

Skeletor supports defining a directory structure with files and folders. You can also specify include files which will be copied into the directory, either from a local file or a remote url, and define build 
tasks to be run after the directory is set up.

The code for Skeletor is actually pretty simple. Ruby's built in YAML.load function converts the template file into a Ruby Hash object which can then be looped through and there is a 
[JSON gem](http://flori.github.com/json/) that works in the same way. The most complicated part was the validation code as I needed to be able to specify custom data types that a node could match any one of.  
The only gem I could find for YAML validation was [Kwalify](http://www.kuwata-lab.com/kwalify/) but that wasn't flexible enough for what I needed so I had to write my own. I eventually managed to get a working 
validation class that worked for what I wanted and decided to extract it into it's own gem so it could be used for other projects, and thus Grayskull was born.

Grayskull will validate JSON and YAML files against a given schema including matching against custom types. All the details for how to create the schema are at the GitHub page, as are the instructions on how to 
install and use it. The same goes for Skeletor. Grayskull is also using Thor for the command line as well as the aforementioned JSON gem for validation.

Check out the GitHub repositories for the source code and instructions.

[Skeletor](http://github.com/OiNutter/skeletor/) | [Grayskull](http://github.com/OiNutter/grayskull)