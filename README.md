# jekyllTest
<hr>

This is a Test Repository to Learn how to use Jekyll both on GitHub as well as my local device.

<hr>

## Using Jekyll on GitHub (http://jmcglone.com/guides/github-pages/)
There are only a few basic steps you need to follow to get started with jekyll.
* Steps:
    * <a href="#1">Step 1:</a> Make .gitignore and config.yml Files
    * <a href="#2">Step 2:</a> Create an index.html file
    * <a href="#3">Step 3:</a> Create a _layouts folder with a default.html
    * <a href="#4">Step 4:</a> 
<hr>

<div id="1"></div>

#### Making .gitignore and config.yml Files

<div id="2"></div>

#### Create index.html file

<div id="3"></div>

#### Create _layouts folder

<div id="4"></div>



## Setting Up Jekyll Locally

This Depends on Ruby and RubyGems. To download Ruby I used: Ruby Installer (https://rubyinstaller.org/downloads/)
This came coupled with RubyGems along with the MSYS2-Devkit.

Since I'm using VisualStudio Code I downloaded the following extension for debugging Ruby and jekyll utility:
###### Extension 1: "Ruby:
Provides Ruby Language and debugging
###### Extension 2: "Jekyll Snippits" "Jekyll Syntax Support" (optional most likely)
Provides useful? Jekyll snippits and syntax. I didn't try using jekyll without downloading these so I'm not sure if they added useful/required functionality or not so you can try using VSCode without them

## Using Jekyll (https://jekyllrb.com/docs/step-by-step/01-setup/)
Now lets get into using Jekyll Locally. First we will install jekyll.
To do this, I opened the "Start Command Prompt with Ruby" from my Windows 10 search bar.
I used Ruby -v and gem -v to make sure that I had Ruby and RubyGems installed.
Then type: <code>gem install jekyll bundler</code>
After this step whenever you want to use jekyll in a project you just have to initialize it.

* Run the Following commands in your project:
    * First we create a Gemfile in our project since jekyll is a "RubyGem" aka a gem: <code>bundle init</code>
    * Second we add jekyll to the Gemfile so that jekyll will be installed once we compile the Gemfile. Add the following line to the Gemfile: <code>gem "jekyll"</code>
    * Last run: <code>bundle</code> This compiles the Gemfile and imports certain 'gems' such as jekyll for use in the project. This generates a Gemfile.lock that saves information on the current state of the project and what gems are in use.
Jekyll will now be available for use in your project!

*** After following these steps any jekyll command you run can be prefixed with <code>bundle exec</code>
Example: <code>bundle exex jekyll build</code>

#### Jekyll Commands

#####jekyll build
Builds the site, creating the _site folder which contains the compiled site files.

#####jekyll serve (Same as 'build' but opens a Live Server)
Builds the site, creating the _site folder, however also opens a local web server and will automatically rebuild the site files whenever a change is made.

