# learn-jekyll

## Install Ruby and Jekyll

Jekyll is written in the Ruby programming language. 

Your computer must understand Ruby if you want to use Jekyll.

You must install the latest Ruby language interpreter for your operating system, found at https://rubyinstaller.org/downloads/.

This also installs RubyGems, the package manager for Ruby programs (or Ruby "packages"). (To install Ruby programs, your computer must have a Ruby package manager.)

Run your Windows command prompt and ensure that Ruby was installed:

```
ruby -v
```

Ensure that RubyGems was installed:

```
gem -v
```

Install Jekyll:

```
gem install jekyll bundler
```

Ensure that Jekyll was installed:

```
jekyll -v
```

## Create a Jekyll Project

Create a Jekyll site called *my_first_jekyll_site*:

```
jekyll new my_first_jekyll_site
```

This creates a default Jekyll site.

Go into the project directory:

```
cd my_first_jekyll_site
```

"serve" your site locally:

```
bundle exec jekyll serve
```

> **Note:** `bundle exec` is not always necessary. Sometimes you can just use only `jekyll serve`.

Open a web browser and enter the URL `localhost:4000`.

Keep the server running.

In Windows Explorer, go into `C:\Users\Kistlers\my_first_jekyll_site\_posts` and make a simple edit to the **YYYY-DD-MM-welcome-to-jekyll.markdown** file.

After you save the file, refresh your browser, and you'll see the update.

Add another .markdown file to the *_posts* directory, with the necessary front matter and a little bit of test content. After saving the file, refresh your browser, and the new page will be available. 

## Themes

Go to https://rubygems.org/.

Search for `jekyll-theme`.

Click a theme link.
Click *LINKS: Homepage*. This takes you to a GitHub repo.
In the README, click the preview link.
When you see one you like, copy the theme name (usually in a code block in the README), open your site's Gemfile file, and add it after the default `minima` theme.
Save the Gemfile file.
Stop your server.
Enter `bundle install` in the Command Prompt.
Change the theme in the *_config.yml* file. (Save the file.)
Restart the server.
Refresh the site.
Behold the blank screen. (The new theme probably uses different layouts than minima does, so each page's front matter is throwing errors at build time.
