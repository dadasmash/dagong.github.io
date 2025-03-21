### Da Gong's Website
https://dadasmash.github.io/dagong.github.io/ <br>
Lecturer of Data Analytics <br>
State University of New York, Geneseo <br>
PhD in Economics <br>
Email: dgong@geneseo.edu

------------------------
A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

I think I've got things running smoothly and fixed some major bugs, but feel free to file issues or make pull requests if you want to improve the generic template / theme.

##### Note: if you are using this repo and now get a notification about a security vulnerability, delete the Gemfile.lock file. 

# Instructions

1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section
1. (Optional) Use the Jupyter notebooks or python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

See more info at https://academicpages.github.io/ <br>
another template: https://github.com/alshedivat/al-folio/tree/c1428532e0735210175034d2588ce00446d3c335 <br>
interactive example: https://github.com/alcocer-jj/TextVizStudio?tab=readme-ov-file

# Further instruction provided by Da Gong
#### here's a useful link: 
https://www.youtube.com/watch?v=jplSmg2Z-Tw

#### some hint 
first thing, change url and repository address in _config.yml <br>
for menu at the top bar, for example: Research and Datasets. <br>
their menu option is stored at _data/navigation.yml  <br>
the link and corresponding markdown is stored at /pages and corresponding files  <br>
the items or contents  (e.g. if your want to uplaod pdf file under Research section...) are stored in corresponding folder under master directory (e.g. _research)  <br>
bio content (first page) is at _pages/about.md
<br>
To set up research page, can also refer to https://kmlv.github.io/research/ and https://zwbai.github.io/#
<br>
To set two colomns in webpage, check this link (need to set CSS in the html header):https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_two_columns_unequal
<br>
enlarge image when hover (need to set CSS in the html header):https://www.educative.io/answers/how-to-enlarge-an-image-on-hover-in-html 
<br>
To set the size of profile photo: go to _sass/_sidebar.scss and find the .author__avatar (see https://opinderkaur.com/). the code for oval profile could be found in the academicpages original code

<br>
click image and direct to a specific location (within same page or other page): https://stackoverflow.com/questions/20565644/how-to-link-to-a-div-on-another-page

<br>
interactive visualization: https://github.com/plotly/plotly.py
<br>

<br>
insert Youtube video (the last answer): https://stackoverflow.com/questions/34708476/jekyll-blog-hosted-in-github-how-to-insert-youtube-embeddings
<br>

#### to be found by  Google Serach engine and set sitemap
1. google7cf42ba7c158084e.html is for verification purpose for Google search engine
2. see https://search.google.com/search-console/welcome and https://github.com/alshedivat/al-folio/discussions/442
3. to get the sitemap address: use this link, https://dadasmash.github.io/dagong.github.io/sitemap/
 and the sitemap to my website is https://dadasmash.github.io/dagong.github.io//sitemap.xml. 
4. Then creat the robots.txt file (https://dev.to/stankukucka/google-search-console-cant-fetch-sitemap-on-github-pages-31kn). this file is to allow google crawl and build index from your website.
5. click "URL Inspection" section in Google Search Console and and "Request Indexing"

## Use Git Bash (edit wepage locally)
git clone https://github.com/dadasmash/dagong.github.io
<br>
ls 
<br>
cd "C:\UCR TA\GradQaunt\Workshop\Summer2023\Webpage\dagong.github.io"
<br>
Start making changes to the content on the page
<br>
git status
<br>
git add 
<br>
git commit 
<br>
git status
<br>
git push
<br>

## To run the webpage locally (not on GitHub Pages, to serve on your own computer)

1. Clone the repository and made updates as detailed above
1. Make sure you have ruby-dev, bundler, and nodejs installed: `sudo apt install ruby-dev ruby-bundler nodejs`
1. Run `bundle clean` to clean up the directory (no need to run `--force`)
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.
1. Run `bundle exec jekyll liveserve` to generate the HTML and serve it from `localhost:4000` the local server will automatically rebuild and refresh the pages on change.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.
