
# Installation Notes

Set up on Windows using wsl

Followed Main instructions: `https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site`

Reached: `https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll`
- Step 12 had permissions issues
- Seems to pass following: `https://github.com/github/docs/issues/2177`
  - `sudo chown -R $(whoami) /var/lib/gems/`
  - `sudo chown -R $(whoami) /usr/local/bin`

Could not find jekyll-sass-converter-1.5.2.gem
- Manual `gem install jekyll-sass-converter -v 1.5.2`

## MathJax

Followed: https://choimon.github.io/blog/mathjax-for-minimalmistakes-githubpage/


# My Cheatsheet

## Local Testing

```
/docs: bundle install
/docs: bundle exec jekyll serve
```

## Site Paths and Contents

With config contents:
```
include: ["pages"]
```

Navigation Entries
* Filepath: `/docs/pages/projects`
* navigation.yml: `/projects`
* Deployed: `https://wesley-fisher.github.io/Wesley-Fisher/projects/`

Manual Link to Page
* Filepath: `/docs/pages/projects/optimization-nav/optimization-nav.md`
* Link: `[text](/Wesley-Fisher/projects/optimization-nav)`
* Deployed: `https://wesley-fisher.github.io/Wesley-Fisher/projects/optimization-nav/`

Media on Page
* Filepath: `/docs/pages/projects/optimization-nav/corridor.gif`
* Link: `![gif](/Wesley-Fisher/pages/projects/optimization-nav/corridor.gif)`
