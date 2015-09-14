# Practical Exercise: A Better Development Workflow


## Goal
Be capable of setting up a theme development workflow that makes use of the
Shopify Theme Gem or Theme Kit, Git for revision control, and Grunt.


## Part 1: Shopify Theme Gem

### Step 1: Set up a development store
If you’ve worked with Shopify themes before, you’ll probably be familiar with
this step. Create a special Shopify store just for testing and development by:

1. Registering for a [Shopify Partner account](https://www.shopify.com/partners);
2. Click “Development stores” and then “Create a new development store” from
   your Partner Dashboard.
   
Your new store will have a default theme, “Launchpad”, installed - you can work
with this theme for the rest of the exercise.

### Step 2: Create a Private Application
Our Theme Gem needs API access to download and upload theme files. From your new
store’s dashboard:

1. Click “Apps” -> “Private Apps” -> “Create a Private App”;
2. Give it a name and leave the page open so we can copy API credentials over.

### Step 3: Install and configure the Shopify Theme Gem
Check that your computer has Ruby installed from a command line by typing
`ruby --version`. If you don’t have Ruby or are on a Windows machine, you may
want to try downloading and using Theme Kit instead of the Theme Gem (installing
Ruby on your machine could end up taking too much time for this exercise).

1. Install the Shopify Theme Gem with `gem install shopify_theme` (or `sudo gem
   install shopify_theme`);
2. Create a new directory to store your theme in locally (`mkdir theme`) and
   `cd` into it;
3. Run 1theme configure API_KEY API_PASSWORD store.myshopify.com1 to create a
   `config.yml` file in your direction;
4. Run `theme download` to download a copy of your theme to you local machine.

### Step 3 (Alternate): Alternative for Windows/non-Ruby users
Go to the [ThemeKit](http://themekit.cat/ website and follow the instructions to
install ThemeKit on your machine.

Use the `theme configure` command as documented on the ThemeKit site, using the
API credentials generated in step 2.

### Step 4: Test Theme Watch
Assuming you could download the theme contents okay, try running `theme watch`
then edit some theme files to see the automatic uploading in action.


## Part 2: Git

### Step 1: Initialise git repository

1. Check you have git installed (`git --version`)
2. Change to your `theme` directory
3. Run `git init .`


### Step 2: Add a .gitignore
Using `vim` or your preferred text editor, create a `.gitignore` file in your
theme directory. Add `config.yml` like this:

```
/config.yml
```

Save the file.

### Step 3: Commit all files
Commit all files in your `theme` directory to your initial commit with:

1. `git add .`
2. `git commit -m "Add a message here"`

### Step 4: Check git status
Check the commit was successful by running `git log` and checking the output.


## Part 3: Grunt

### Step 1: Check requirements
Check you have Node.js and NPM installed by running `node --version` and
`npm --version`. If you're missing them, download and install by following the
instructions on the [NPM website](https://docs.npmjs.com/getting-started/installing-node).

### Step 2: Install Grunt CLI
Install the Grunt command line by running `sudo npm install -g grunt-cli`.

### Step 3: Add package.json to your theme
Run `npm init` to install a default `package.json`.

Install the Grunt plugin we'll be using with
`npm install grunt-contrib-concat --save-dev`.

Once done, run `npm install` to make sure all node dependencies are installed.

### Step 4: Add and test Gruntfile
Copy [this Gruntfile](https://gist.github.com/gavinballard/cead3b23fe4c067b899d)
from this repository to your theme's directory, then test things out by running
`grunt concat`.

### Step 5: Experiment!
Come up with some other common tasks you might want to perform, and try to find
some Grunt plugins to help you out, then add them to your Gruntfile.






