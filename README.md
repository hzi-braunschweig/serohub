# SeroHub
This website is created by [Helmholtz HZI](https://www.helmholtz-hzi.de/en) to support the open collaboration of researchers around COVID-19.

## TODO
- implement the Netlify CMS solution 
- DNS change 
- introduce a better data sharing mechanism
- (maybe) add a blog section
- (maybe) make site multi-lingual

## Get help
For any issues with the site including typos or rendering issues, please file an [issue](https://github.com/INSERTREPO/issues) or send a pull request. The site automatically deploys once pull requests are merged.

## Contributing content
To contribute content, you can create a Pull Request with the content.

1. Fork the repository (repo) of the serohub website.
1. Draft your post in R Markdown or Markdown.
1. (Optional) Preview and refine your post locally.
1. Submit via pull request and preview your post.
1. A serohub maintainer accepts your content, or requests changes.

An excellent place to learn about contributing science related blog posts is [ropensci technical guidelines](https://blogguide.ropensci.org/technical.html).

## Add a researcher
If you would like to add a researcher, the general content steps are taken but instead of generating files with markdown you amend the [Researcher list](data/researchers.csv).

## Making changes to the website
For changes to the website, there are a few key areas:

- The [config](config.toml) file that supports changing many values used in the repository
- [index.html](layouts/index.html) determines what the home page looks like. It may reference files in syntax like `{{ partial "leaflet.html" . }}` -- these are sub-templates and are found in [layouts/partials](layouts/partials)
- [baseof.html](layouts/_default/baseof.html) describes header and footer content used across the site. This is where you would change things like JavaScript files, the nav bar, and the footer
- [share_study.md](content/share_study.md) contains the html used to generate the contact form that will submit the contents to netlify. Note the Netlify free tier has an upload limit of 10Mb per month. This is *not*  a long-term solution.
- [hzi.css](assets/hzi.css) is the custom style sheet for the website. Use this to tweak or override the website appearance.

## Getting things set up locally
### Get the repo locally
1. If you're a member of the organisation, `git clone  --recurse-submodules https://`
2. If you're not a member of the organisation, fork the repo, then `git clone  --recurse-submodules https://`

### Get the submodule
We use a theme [hugo-infinite](https://github.com/lambdafu/hugo-finite) as the basis for the site. The `--recurse-submodules` argument in `git clone` will have established a connection. *You should not make changes to contents in the submodule* instead, you should copy files from the themes structure and paste them into the corresponding section of the main repository and edit it there. You only work with the submodule contents directly if you want to fix a bug and that is best done with a fresh fork of the theme directly from the theme's repository.

### Run hugo locally
From inside the website directory, run `hugo serve` to get a live local copy (typically on <http://localhost:1313>) that will update whenever you make changes.

## Infrastructure
### Hugo
This website uses [Hugo](https://gohugo.io). To work with Hugo locally, you will need to [install it](https://gohugo.io/getting-started/quick-start/).

Hugo is a website generator that pre-generates web pages so that they can be hosted
very cheaply. It is used by a significant amount of the research and science
communities due to its excellent support for markdown which enables researchers to use literate
programming techniques in R and Python to interleave analysis and text. 

### Netlify
The website is hosted on [Netlify](https://netlify.com). 

### GitHub
We will host the solution on Netlify with the source files hosted on GitHub. This will
enable HZI researchers to work in an open way and accept collaborations from others.

## Resources
- Git
    + [gitHub guides](https://guides.github.com/)
    + [Happy Git and GitHub for the useR](https://happygitwithr.com/)
    + [Version Control with Git](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)
- Hugo
    + [Hugo Quickstart](https://gohugo.io/getting-started/quick-start/)
    + [Intro to markdown](https://commonmark.org/help/tutorial/index.html)
    + [Maëlle Salmon](https://masalmon.eu/tags/hugo/), [ROpenSci](https://ropensci.org/tags/hugo/) blog posts
- Netlify
    + [Netlify docs](https://docs.netlify.com/#get-started)
- Blogdown
    + [ROpenSci notes](https://blogguide.ropensci.org/technical.html)