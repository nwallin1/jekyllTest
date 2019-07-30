# jekyllTest
<hr>

This is a Test Repository to Learn how to use Jekyll both on GitHub as well as my local device.

<hr>

## Using Jekyll on GitHub (http://jmcglone.com/guides/github-pages/)
There are only a few basic steps you need to follow to get started with jekyll.
* Steps:
    * <a href="#1">Step 1:</a> Create an index.html file
    * <a href="#2">Step 2:</a> Make .gitignore and config.yml Files
    * <a href="#3">Step 3:</a> Create a _layouts folder with a default.html
    * <a href="#4">Step 4:</a> 


--- 
**NOTE THAT I AM USING USING THE /docs SETUP TO USE GITHUB PAGES**
This means that my github pages site is located in the master/docs folder. To Access my site I type:
http://nwallin1.github.io/${repository_name}    - Where repository_name is the name of the repository.
This just allows me to make multiple websites on different repositories on github.
For instructions on how to use github pages please go here: https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages
---



<div id="1"></div>

#### Create index.html file

* Create a File called index.html: Example file below (Mine is made in master/docs due to my github pages configuration, see https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages)

<code>
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/cv">CV</a></li>
            <li><a href="/blog">Blog</a></li>
        </ul>
    </nav>
    <div class="container">
        <p>This is my Website! One day it will have lots of cool features, and building it will be super quick and easy thanks to @jekyll!</p>
    </div>
    <footer><a href="https://github.com/nwallin1">github.com/nwallin1</a></footer>
    
</body>

</html>
</code>
<div id="2"></div>

#### Making .gitignore and config.yml Files

* *.gitignore*
    *  Create the .gitignore file in the root directory. (Where your index.html is located. Mine is going to be in master/docs)
    * Add this single line to .gitignore:
        * <code>_site/</code>
    * This ignores the jekyll generated _site/ folder.

* *config.yml*
    * Create the config.yml in the root directory
        * Add These lines:
            * <code>name: your_name
            markdown: kramdown</code>
            * Name is the name of the site the markdown is the version of Markdown being used
            * *NOTE* Any items you define in config.yml can be accessed in the files we will create later. If we created a <code>my_number: 111-111-1111</code> you will be able to access this with <code>{{ site.my_number }}</code> in the .html files later on.

<div id="3"></div>

#### Create _layouts folder

* At this point in Time we have access to our website at http://your_username.github.io/repo_name
* Now here's were Jekyll starts to take effect:
* Create a _layouts folder in the root directory
    * Inside the _layouts folder create a file called default.html
        * We are going to insert inside default.html information that will be similar between all of the different pages/tabs in our site. For example the Home Page and the About Page will both contain the same nav bar as well as footer.
        * Lets add to our default.html file the constant information from our index.html file:
            * <code>
                <!DOCTYPE html>
                <html>
                <head>
                    <!-- Note this -->
                    <title> {{ page.title }} </title>
                </head>
                <body>
                <nav>
                <ul>
                <li><a href="/">Home</a></li>
                <li><a href="/about">About</a></li>
                <li><a href="/cv">CV</a></li>
                <li><a href="/blog">Blog</a></li>
                </ul>
                </nav>
                    <!-- And this -->
                    {{ content }}

                <footer><a href="https://github.com/nwallin1">github.com/nwallin1</a></footer>
                </body>
                </html>
                </code>
        * Note the <code>page.title</code> and <code>content</code> tags. We will understand these in a bit.
        * Now we can edit our index.html to use deafult.html as a template.
            * Go to index.html and change it to:
                * <code>
                    ---
                    layout: default
                    title: My Home Page
                    ---
                    <div class="container">
                        <p>This is my Website! One day it will have lots of cool features, and building it will be super quick and easy thanks to @jekyll!</p>
                    </div>
                    </code>
                * The <code>---</code> is called Front Matter and indicates that jekyll should treat this as a special file. (See https://jekyllrb.com/docs/front-matter/)
                * Our layout: default line means that we will be using our default.html page in _layouts as a <code>template for index.html</code>. Remember the <code>{{ page.title }}</code> tag in default.html? Well here when we say define our <code>title: My Home Page</code>, default.html will insert "My Home Page" for <code>{{ page.title }}</code>
                * The <code>{{ content }}</code> tag will insert anything below the bottom <code>---</code> into default.html. Save all the files and take a look at the new webpage. It should look the same! (Note that GitHub pages sometimes takes awhile to process changes in the source files so give it a minute or two between changes)
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

##### jekyll build
Builds the site, creating the _site folder which contains the compiled site files.

##### jekyll serve (Same as 'build' but opens a Live Server)
Builds the site, creating the _site folder, however also opens a local web server and will automatically rebuild the site files whenever a change is made.

