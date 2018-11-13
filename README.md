<h1 align="center"><img src="http://students.washington.edu/plenum/images/logo2-300x300-white.png"/></h1>

Plenum is an online journal devoted to showcasing the highest quality scholarship in undergraduate geography while building community amongst the Geography Department at the University of Washington. It is managed, produced, and reviewed by undergraduate students from the Department of Geography at the UW.

# Plenum Website Front-End
Plenum's website is a Vue.js web application built and maintained by Plenum members.
The app is populated via JSON API data from [Contenta CMS](https://www.contentacms.org), an API first Drupal distribution.

![alt text](https://lh3.googleusercontent.com/H2b3gk6WqLkuuhu1DUDpiD94-ujfFQxoXmdSbrGonLuKlBZBRJ1AG2NlGFrOlWSbecmZ-kpf9Zn7=w8128-h4976-rw-no "Plenum website on the About Page")

# How to Contribute
## Requirements
* Github Account - Sign up for the [student developer pack](https://education.github.com/pack) for freebies
* Review the standards we try to follow at the bottom of the README
### Local
* [Node & NPM](https://nodejs.org/en/download/) - Most version should be fine, LTS option is safest
* [git](https://git-scm.com/downloads) - Install directly or via [Homebrew](https://brew.sh)(Mac) or [Chocolatey](https://chocolatey.org)(Windows)
* Your favorite IDE - The student developer pack includes JetBrains. [IntelliJ](https://www.jetbrains.com/idea/) is robust and extendable

## Getting Setup
1. [Fork](https://help.github.com/articles/working-with-forks/) this repo into your personal GitHub account
2. [Clone](https://help.github.com/articles/cloning-a-repository/) _your_ repo to your local development machine. *Cloning the OG repo will prevent you from submitting pull requests
```
git clone https://github.com/{{YOUR_GITHUB_ACCOUNT}}/plenum-website.git
```
3. Install project dependencies with NPM
```
cd /plenum-website # Navigates into the project directory
npm install # Node Package Manager installs all the necessary packages to develop the website
```
4. Prepare local [Plenum Contenta CMS](https://github.com/PlenumUW/plenum-drupal)
*Without a local copy of Plenum's Contenta CMS, development options will be severely limited. Currently, there are no 'disconnected' alternatives.
5. Create a new file **.env.development.local** at the project's root directory, paste the following code and replace `{{PORT_NUMBER}}` with the port number of the local server that is hosting your Contenta CMS:
```
VUE_APP_CONTENTA_API=http://localhost:{{PORT_NUMBER}}/contenta/web/api
VUE_APP_CONTENTA_BASE=http://localhost:{{PORT_NUMBER}}
```

Congratz! You are ready to develop!

## Serving the Website
In order to actively observe the changes that you are making during development, ['serve' the website](https://cli.vuejs.org/guide/cli-service.html#using-the-binary):
```
npm run serve
```
This creates a local dev server on which a Vue app is hosted which updates and re-compiles when changes are made within your IDE.
The terminal will output the compilation process, **_THERE WILL BE LOTS OF 'ERRORS'_**. Ignore them. The current typescript config outputs errors, even though the project is still valid; currently working on fixing the output of these errors.
P.S. Vue-CLI GUI is a feature that doesn't work with our distribution of Vue-CLI. Someday a migration will occur in order to benefit from this newer feature.

## Collaboration Workflow
We are using a [_Fork & Pull_](https://help.github.com/articles/about-collaborative-development-models/) model to manage collaborative development; this allows our team to accomodate all types of contributors, both new and experienced, without putting the code base at risk from conflicting merges.

Once you're happy with what you've developed and believe it is ready to be merged into the PlenumUW's repo:
1. Push your work to your personal fork
2. Create a [Pull Request](https://help.github.com/articles/about-pull-requests/)
   * If your work is in response to a specific [Issue](https://github.com/PlenumUW/plenum-website/issues), use [issue closing keywords](https://help.github.com/articles/closing-issues-using-keywords/) in your pull request title or message
3. Your pull request will be reviewed and merged into the main repo

# Standards and Style
### [Vue Style Guide](https://vuejs.org/v2/style-guide/#Component-style-scoping-essential)
  * [Props Down Events Up](https://vuejs.org/v2/style-guide/#Implicit-parent-child-communication-use-with-caution)
### CSS/SCSS
  * [BEM (Block, Element, Modifiers) - Naming Conventions](http://getbem.com/introduction/)
  * [SMACSS - CSS/SCSS Formatting](https://smacss.com/book/formatting)

# Accessibility Initiative
* [WebAIM](https://webaim.org) - Testing Articles
* [Getting Started with Web Accessibility in Vue](https://medium.com/@emilymears/getting-started-with-web-accessibility-in-vue-17e2c4ea0842)
* [W3 HTML Techniques for Web Content Accessibility Guidelines 1.0](https://www.w3.org/TR/WCAG10-HTML-TECHS/#edef-MAP) - Index of Web Accessibility Standards
* [Menu Navigation Concepts](https://www.w3.org/WAI/tutorials/menus/)
* [Menubar Example](https://www.w3.org/TR/wai-aria-practices/examples/menubar/menubar-1/menubar-1.html)
* [Keyboard only focus](http://kizu.ru/en/blog/keyboard-only-focus/#x)

#### Accessibility Manual Testing
* [ ] [VoiceOver Testing Tutorial](https://webaim.org/articles/voiceover/)
* [ ] [Screen Reader Testing Tutorial](https://webaim.org/articles/jaws/)
* [ ] [Non-Visual Desktop Access Testing Tutorial](https://webaim.org/articles/nvda/)
