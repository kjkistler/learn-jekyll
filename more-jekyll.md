JEKYLL


INSTALL EVERYTHING

1. Install Ruby (`ruby -v`).
2. Install RubyGems, if it's not already (`gems -v`).
3. Install Jekyll: `gem install jekyll bundler`.


CREATE PROJECT

1. Create Jekyll project: `jekyll new my-jekyll-project`. (Creates it in the current directory?)
2. `cd my-jekyll-project` and 'ls -a`:
	- _posts (directory)
	- _config.yml (settings for the site)
	- .gitignore
	- 404.html
	- about.markdown
	- Gemfile (stores all the site's RubyGem dependencies)
	- Gemfile.lock
	- index.markdown


BUILD AND SERVE

1. Build the site and make it available on a local server (in project directory): `bundle exec jekyll serve`. (Just `jekyll serve` on subsequent server runs.)
2. Browse to http://localhost:4000.
3. `ls -a` in my-jekyll-project now shows:
	- _posts (directory) -- the folder with the source files, contains yyyy-mm-dd-welcome-to-jekyll.markdown by default
	- _site (directory) -- the generated web output
		- about (directory)
		- assets (directory)
		- jekyll (directory)
		- 404.html
		- feed.xml
		- index.html
	- .sass-cache (directory)
	- _config.yml
	- .gitignore
	- 404.html
	- about.md
	- Gemfile
	- Gemfile.lock
	- index.md


FRONT MATTER

1. Open up default blog post source file. The front matter is in YAML (can be JSON):

---
layout: post
title: "Welcome To Jekyll!"
date: 2019-mm-dd hh:mm:ss -0000
categories: jekyll update
---


WRITE A POST

1. Go into _posts directory.
2. Create file yyyy-mm-dd-post-title.md. (Apparently, it must have the date convention.)
3. Add empty front matter:

---
---

4. Then add some dummy content.
5. Save file.
6. Refresh running site.
7. The URL of the page suggests the directory structure in the _site directory.
8. Jekyll is pulling the title and date on the page from the file name.
9. Add `layout: "post"` to the front matter of the file to clean up the layout.
10. Add `title: "New Title"` to the front matter. This overrides the file name.
11. Save the file.
12. If you add a `date: ` to the front matter, the old URL will break because the front matter date rules over the date in the file name.
13. Creating subdirectories in _site will (or will not?) be reflected in URL paths.


WORK ON DRAFTS (FILES IN PROGRESS THAT AREN'T PUBLISHED)

1. At the same level as _posts, create a _drafts directory.
2. Add a draft source file to the _drafts directory (with some front matter and dummmy content). Don't use the date convention in the file name.
3. Save the file.
4. Kill your server (if necessary): Ctrl-c.
5. Run `jekyll serve --draft`.
6. Refresh the site.
7. The URL of the draft contains the current date.


CREATE PAGES (NON-POSTS, LIKE THE DEFAULT "ABOUT" PAGE)

1. Create a new source file at the same level as about.md.
2. Add front matter with just a layout key, which is a different layout value than we've seen so far (should be in the about.md file, too):

---
layout: "page"
---

3. Add dummy content.
4. Save the file.
5. Refresh the site and add the /page-title after the URL.
6. Add a title to the front matter. (Doesn't need to be a string?)
7. Pages can be in a directory at the same level as _posts, as long as the directory name is in the URL to the page.


PERMALINKS

