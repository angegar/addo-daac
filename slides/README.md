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
  video.inslide {
    position: absolute;
    width: 70%;
    height: 70%;
  }
paginate: false
footer: '[github/ojacques](https://github.com/ojacques) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [github/angegar](https://github.com/angegar)'
---
<!--backgroundImage: url('https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/title.jpg')-->
<br/>
<br/>
<br/>
<br/>

# CI and CD
## For documentation

<!-- 
speaker: Olivier

Thank you. Today, Laurent and I are going to talk about "Documentation as Code" and more specifically CI and CD for documentation.

But first, let us introduce ourselves:

Speakers: Olivier & Laurent
- Short intro

(NOTE: embed Olivier & Laurent's faces / OBS)

-->

---
<!--backgroundImage: url('dxc.jpg')-->

<!--

<!-- 
speaker: Olivier

Laurent and I both work for DXC technology customers. DXC technology is a global IT services leader.

With 19.6B$ of revenues, 6000 customers and 138000 employees across 70 countries, we are - in many dimensions - big.

-->

---
<!--backgroundImage: url('https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/simple.jpg')-->

The quest to great documentation

# 🏰🦄🤴👸🐴👻⚔🗡🏴‍☠️

<!-- 

Back to this presentation. This presentation is an experience report. 
We are on a quest: the quest to great documentation.

Previously, 
- our documentation was the last thing we would do,
- it had spelling and syntax mistakes,
- we were using the passive voice, but sometimes the active voice
- it was often inaccurate,
- a few were able to correct anything so we had to contact them through email,
- several authors could not work on the same piece of documentation without going through lengthy merges,
- and links would break very often without us even knowing.

Today, it's a very different situation
- we have one service catalog and 174 services documented
- documentation readers can contribute to the documentation using a Pull Request
- documentation changes go through a series of tests and gates
- our documentation is bigger yet more thorough and precise than ever
- It has the same look & feel
- it's written in the same style

-->

---

# We do a lot of documentation

## (as code)

<!-- 

The context for the experience report is our own company (but we do that with our customers too):
- A platform which provides intelligence, orchestration, and automation capabilities to our managed service offerings
- 630 contributors (developers, testers, scrum masters)
- 1 "service catalog" site
- 174 services documented

-->

---

![bg 100% right](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/service-catalog-hugo.gif)

# Service catalog
With [Hugo](https://gohugo.io/)

<!--
Speaker: Olivier

We have 2 types of documentation: 
- Service catalog
- Service documentation

Service catalog:
- Marketing / catalog site: mix of text, benefits, highlights, videos
- We use Hugo
  - shortcodes: like macro, for documentation. Ensures uniformity
-->
---

![bg 100% right](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/service-documentation-mkdocs.gif)

# Service documentation
With [MkDocs](https://www.mkdocs.org/) + [material theme](https://squidfunk.github.io/mkdocs-material/)

<!--
Speaker: Olivier

-->

---

![bg center 60%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/doc-site.jpg)

<!--
Speaker: Olivier

-->
---
# 🤯

## Microsoft, GitHub, GitLab, AWS all use "Documentation as code"

Because:

- Documentation next to the code
- Lightning fast to browse (static sites)
- Easier to contribute to / keep up-to-date
- Engineer documentation
- Battle test documentation
- Who reads what (analytics)

<!--
Documentation next to the code:
  - Versions can be aligned with code versions
  - Developers use a workflow that they know
  - Tech writers / Product owners learn the developer workflow
Lightning fast to browse (static sites)
  - Comparing to WordPress/Drupal/Confluence type solutions
  - More secure (no DB to hack)
  - Portable (even offline)
Easier to contribute to / keep up-to-date
  - The pull request / merge request workflow fully applies
Engineer documentation
Battle test documentation
Who reads what (analytics)
  - "Is this page useful?"
  - Analytics: like Google Analytics or Open Source alternative: Matomo
  - Reader journey, what is useful
-->

---

# Our challenges

- Common look & feel
- Common voice
- Lowering the bar for Tech Writers
- DRY: Don't Repeat Yourself
- Diagrams
- Broken links
- Publishing

<!--
speaker: Olivier

-->
---
<video loop class="inslide" src="https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/gource.mp4" autoplay muted />

<!--
speaker: Olivier

In summary, we needed to build great documentation, at scale, battle tested and ensure it would not break over time.

Looks like code to us!

This is a visualization of our service catalog repository documentation.
-->

---

![bg right 80%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/ci-cd-for-doc.gif)

# CI and CD for documentation

CI

- Spell checking
- Check for approved acronyms / custom dictionary
- One voice
- Periodically check for 404 links

CD

- Automate publishing

<!--
Speaker: Olivier

-->

---

![bg](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/title.jpg)
<br/>
<br/>

# In practice

<!--
Speaker: Laurent
-->

---
![bg right 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/vscode.jpg)
# Authoring

Leverage [`Markdown`](https://guides.github.com/features/mastering-markdown/)

Use your favorite code editor:

- [IntelliJ](https://www.jetbrains.com/help/idea/markdown.html#navigation)
- [Eclipse](https://marketplace.eclipse.org/content/markdown-text-editor)
- [VSCode](https://code.visualstudio.com/docs/languages/markdown)

<!--
Speaker: Laurent

No need for programmatic language, just use Markdown
-->

---
![bg right 90%](https://github.com/hediet/vscode-drawio/raw/master/docs/drawio-png.gif)
# Authoring (1)

## Pimp your editor with extensions

- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) (for syntax)
- [Draw.io](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio) (for drawings)
- [PlantUML](https://github.com/qjebbs/vscode-plantuml) (for diagrams as code)
- [Marp](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) (for slides)
- ...

<!--
Speaker: Laurent

Most of the integrated development environments (IDE) can be enhanced with multiple plugins. Here is a short list of what we used to use.
-->
---
![bg right 90%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/codespaces.jpg)

# Authoring (2)

## GitHub [Codespaces](https://github.com/features/codespaces) or GitPod

- Edit directly from the browser
- Make it easy for tech writers:
  no `git clone/branch/push`
  `git reset origin/main --hard`
- Shared extensions across development environments

---
# Authoring (3)

## Pick a tool

- [Jekyll](https://jekyllrb.com/) 🤐
- [Hugo](https://gohugo.io/): powerful, blazing fast
- [Marp](https://marp.app/): slides as code in markdown
- [MkDocs](https://www.mkdocs.org/) + [material theme](https://squidfunk.github.io/mkdocs-material/)

<!--

- Jekyll : Based on Ruby, it is hard to configure for a non developer users especially under windows => hard to contribute
- Hugo:
  - HTML + go template for documentation
  - Far from standard markdown => hard for non dev users
  - Recommended if you need to have multiple page template in your web site
- Marp:
  - Excellent to generate slide deck
  - Follow Markdown syntax
  - Presenter view
  - Template with CSS
  - Extensible
  - Output PPTX, PDF, PNG, JPEG
- MkDocs:
  - Follow Markdown syntax
  - Closest to plain markdown, great for tech docs
  - Can integrate native HTML web page => Can integrate Marp outputs
-->
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

<!--

We use linters to check code "doc" quality.

2 types of linters
- CLI: to be integrated in the pipeline 
- Editor: check syntax as you type

-->

---
# CI: Spell Checker

## CLI spell checker

![bg 90% right](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/spellcheck_code.png)

- [spellcheck-github-actions](https://github.com/rojopolis/spellcheck-github-actions)
- [spellchecker-cli](https://github.com/tbroadley/spellchecker-cli)

<!-- 

-->
## Editor spell checker

- [VS Code code-spell-checker extension](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

---
# CI: Link checker

![bg right:65% 95%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/markdown-link-check.jpg)

<!-- 

Links must be checked regularly (cron) as they break without you doing any change.

-->

## 404 links

[markdown-link-check](https://github.com/tcort/markdown-link-check)

---

![bg right:65% 95%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/style-vale.jpg)

# CI: Testing (4)

## Style / voice

[Vale](https://github.com/errata-ai/vale)

---
# Publishing (CD)

![bg right 95%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/github_actions.png)

## GIT Hosting

GitHub, GitLab, Bitbucket

## Web hosting

[GitHub pages](https://pages.github.com/), [GitLab pages](https://docs.gitlab.com/ee/user/project/pages/), [Netlify](https://www.netlify.com/), an AWS S3 bucket.

---
![bg right 95%](https://github.com/documentation-as-code/ci-cd-for-documentation/raw/main/slides/github_template.png)
# Spread practices

- [GitHub templates](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-template-repository)

<!--
Speaker: Laurent

We have been using GitHub template to ease the creation of Documentation As Code

-->
---
# Thank you 🙏
