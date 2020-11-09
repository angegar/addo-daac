---
marp: true
theme: default
style: |
  footer {
    position: absolute;
    #left: 50%;
    bottom: 7px;
  }
  section header a { color: white;}
paginate: false
footer: '[github/ojacques](https://github.com/ojacques) &nbsp; &nbsp; &nbsp; &nbsp; [github/angegar](https://github.com/angegar)'
---
<!--backgroundImage: url('https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/title.jpg')-->
<br/>
<br/>
<br/>
<br/>

# CI and CD for documentation
...in 2020

---
<!--backgroundImage: url('https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/simple.jpg')-->

Our story and how we solved our problems

# 🏰🦄🤴👸🐴👻⚔

---

# We do a lot of documentation

(...as code)

---

![bg 100% right](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/service-catalog-hugo.gif)

# Service catalog
With [Hugo](https://gohugo.io/)

---

![bg 100% left](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/service-documentation-mkdocs.gif)

# Service documentation
With [MkDocs](https://www.mkdocs.org/) + [material theme](https://squidfunk.github.io/mkdocs-material/)

---

![bg center 60%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/doc-site.jpg)

---
# 🤯

## Microsoft, GitHub, GitLab, AWS all use "Documentation as code"

Because:

- Documentation is next to the code
- Lightning fast to browse
- Easier to contribute to / keep up-to-date
- Engineer documentation
- Battle test documentation

---

# Our challenges

- Common look & feel
- Common voice
- Lowering the bar for Tech Writers
- DRY: Don't Repeat Yourself
- Diagrams
- Broken links
- Publishing

---

# CI and CD

CI

- Spell checking
- Check for approved acronyms / custom dictionary
- One voice
- Periodically check for 404 links

CD

- Automate publishing

---
![bg right 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/vscode.jpg)
# Authoring

This is (mostly) markdown:
Use your favorite code editor.

---
![bg left 90%](https://github.com/hediet/vscode-drawio/raw/master/docs/drawio-png.gif)
# Authoring (1)

## Pimp your editor with extensions

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) (for syntax)
- [Draw.io](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio) (for drawings)
- [PlantUML](https://github.com/qjebbs/vscode-plantuml) (for diagrams as code)
- [Marp](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) (for slides)

---
![bg right 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/codespaces.jpg)

# Authoring (2)

## GitHub Codespaces or GitPod

- Edit directly from the browser
- Make it easy for tech writers:
  no `git clone/branch/push`
  `git reset origin/main --hard`

---
# Authoring (3)

## Pick a tool

- [Jekyll](https://jekyllrb.com/) 🤐
- [MkDocs](https://www.mkdocs.org/) + [material theme](https://squidfunk.github.io/mkdocs-material/): closest to plain markdown, great for tech docs
- [Hugo](https://gohugo.io/): powerful, blazing fast
- [Marp](https://marp.app/): slides as code, mostly markdown

---
# Orchestrating

- GitHub Actions
- GitLab CI
- Jenkins (`Jenkinsfile`)
- AWS code pipeline
- Azure DevOps

---
# CI: Linter

## CLI linter

- [github super-linter](https://github.com/github/super-linter)
- [markdownlint](https://github.com/DavidAnson/markdownlint)
![bg right 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/linter.png)

## Editor linter

- [VS Code markdownlint extension](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
  
---
# CI: Spell Checker

## CLI spell checker

![bg left 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/spellcheck.png)

- [spellcheck-github-actions](https://github.com/rojopolis/spellcheck-github-actions)
- [spellchecker-cli](https://github.com/tbroadley/spellchecker-cli)

## Editor spell checker

- [VS Code code-spell-checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

---
# CI: Link checker

![bg right 95%](markdown-link-check.jpg)

## 404 links

[markdown-link-check](https://github.com/tcort/markdown-link-check)

---
# CI: Style checker

[Vale](https://github.com/errata-ai/vale)

---
# Publishing (CD)

## GIT Hosting
GitHub, GitLab, Bickbucket

## Web hosting
[GitHub pages](https://pages.github.com/), [GitLab pages](https://docs.gitlab.com/ee/user/project/pages/), [Netlify](https://www.netlify.com/), an AWS S3 bucket, ...

---
# Thank you! 🙏
