# SeroHub
This website is created by [Helmholtz HZI](https://www.helmholtz-hzi.de/en) to support the open collaboration of researchers around COVID-19.

## Get help
For any issues with the site including typos or rendering issues, please file an [issue](https://github.com/INSERTREPO/issues) or send a pull request. The site automatically deploys once pull requests are merged.

## Contributing content
To contribute content, you can create a Pull Request with the content.

1. Fork the repository (repo) of the serohub website.
1. Draft your post in R Markdown or Markdown.
1. (Optional) Preview and refine your post locally.
1. Submit via pull request and preview your post.
1. A SeroHub maintainer accepts your content, or requests changes.

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


### Publications
The default site (en):

- The folder `content/publication` contains the reference to scientific papers. **It's our main folder to curate publications!**
- Each `.md` refers to one scientific paper, and is named by its DOI, e.g. `10.1101-2020.05.18.20103283.md`
- The markdown files are organized by the publisher, e.g. `content/publication/biorxiv/10.1101-2020.05.18.20103283.md`

The language-specific sites (e.g. de):

- The majority of scientific papers are written in English language. 
- In `config.toml` each language (except `en`) has an additional content folder defined, e.g. `contentDir="content_de"` for the German site. 
- In order to display English papers, we will copy/mirror whole folders to the language-specific directory, e.g. `cp content/publication/biorxiv content_de/publication/biorxiv`

## Getting things set up locally
### Get the repo locally
1. If you're a member of the organisation, `git clone --recurse-submodules git@github.com:hzi-braunschweig/serohub.git`
2. If you're not a member of the organisation, fork the repo, then 
    - `git clone --recurse-submodules git@github.com:<your account>/serohub.git`
    - `git remote add upstream https://github.com/hzi-braunschweig/serohub.git`


### Get the submodule
We use a theme [hugo-infinite](https://github.com/lambdafu/hugo-finite) as the basis for the site. The `--recurse-submodules` argument in `git clone` will have established a connection. *You should not make changes to contents in the submodule* instead, you should copy files from the themes structure and paste them into the corresponding section of the main repository and edit it there. You only work with the submodule contents directly if you want to fix a bug and that is best done with a fresh fork of the theme directly from the theme's repository.

### Run hugo locally
From inside the website directory, run `hugo serve` to get a live local copy (typically on <http://localhost:1313>) that will update whenever you make changes.

## Infrastructure

### GitHub
We will host the solution on Netlify with the source files hosted on GitHub. This will
enable HZI researchers to work in an open way and accept collaborations from others.

### Hugo
This website uses [Hugo](https://gohugo.io). To work with Hugo locally, you will need to [install it](https://gohugo.io/getting-started/quick-start/).

Hugo is a website generator that pre-generates web pages so that they can be hosted
very cheaply. It is used by a significant amount of the research and science
communities due to its excellent support for markdown which enables researchers to use literate
programming techniques in R and Python to interleave analysis and text. 

### Netlify
The website is hosted on [Netlify](https://netlify.com).

#### Automated deployments
The website is automatically updated everytime there is a change to the master branch in GitHub. Additionally, any pull requests or branches will also have preview URLs built. The preview links for Pull Requests will be included in the Pull Request interface on GitHub.

#### Authentication
The Netlify hosting has Visitor access > OAuth authentication enabled with a [GitHub OAuth application](https://developer.github.com/apps/building-oauth-apps/) - this is important for the Netlify CMS to support open authoring.

#### SSL
Netlify can support custom SSL certificates to be associated with the intended domain of `serohub.helmholtz-hzi.de`  The SSL can either be a letsencrypt managed certificate or it can support [a wildcard domain SSL](https://docs.netlify.com/domains-https/https-ssl/#custom-certificates). Note that the custom certificate route requires the SSL certificate to be updated manually, whenever a new one is issued.

### Netlify CMS
The user interface for adding and managing studies is built using the [Netlify CMS](https://www.netlifycms.org/).

#### How it works
The CMS is used to provide an interface to GitHub and Git activities behind the scenes. 
You can login with your Github account at [serohub.netlify.app/admin](https://serohub.netlify.app/admin).
Please note,

- You need to use a github account that has **NO access rights** to the [serohub repository](https://github.com/hzi-braunschweig/serohub). When you write a blog post ("General Content"), a study, or publication, it will create a fork of the repository in the users account and they can perform edits that will become pull requests for serohub maintainers to approve.
- If you are a maintainer or have any write access rights to [serohub repository](https://github.com/hzi-braunschweig/serohub), you will end with an error `Failed to persist entry: API_ERROR: Not Found` when trying to save a new blog entry.


## Resources
- Git
    + [GitHub guides](https://guides.github.com/)
    + [Happy Git and GitHub for the useR](https://happygitwithr.com/)
    + [Version Control with Git](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)
- Hugo
    + [Hugo Quickstart](https://gohugo.io/getting-started/quick-start/)
    + In repo: [Intro to (Hu)go templates](content/posts/goisforlovers/index.md) and [Writing Markdown](content/posts/writing-markdown-latex/index.md)
    + [Intro to markdown](https://commonmark.org/help/tutorial/index.html)
    + [Maëlle Salmon](https://masalmon.eu/tags/hugo/), [ROpenSci](https://ropensci.org/tags/hugo/) blog posts
- Netlify
    + [Netlify docs](https://docs.netlify.com/#get-started)
- Blogdown
    + [ROpenSci notes](https://blogguide.ropensci.org/technical.html)