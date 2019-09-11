# Demo of Hosting Angular 2/3/... 8 app on GitHub pages

You'll learn to deploy an Angular application to GitHub Pages.

> Github pages allows you to host static websites and web apps for free using the same workflow you use to host repositories, you just commit and push. Build and Deploying of static website to GitHub Pages can be automated. You can even associate a custom top level domain name to your website or web app by adding a CNAME file.


## Prerequisites
- Angular requires latest Node.js version
  - To check your version, run `node -v` in a terminal/console window.
  - To get Node.js, go to https://nodejs.org
- npm package manager
  - To check your version run npm -v in a terminal/console window
  - Install npm client - https://docs.npmjs.com/cli/install
  
## Install the Angular CLI

```shell
npm install -g @angular/cli
```

## Create a workspace and Angular application with default settings

```
ng new angular-github-pages-demo --defaults
```

Run the application, your should see the running application.

```
cd angular-github-pages-demo
ng serve --open
```


## Create a Repository on GitHub

- Goto your GitHub Home page -> Repositories -> Click New
- Specify your repo name `angular-github-pages-demo`
- Leave it public and add a `README` file
- Create Repo

You should find instrutions to push an existing repository from the command line:

```
git remote add origin https://github.com/hoodaajay99/angular-github-pages-demo.git
git push -u origin master
```
> GitHub Pages allows you to create single sites per `GitHub account and organization` and unlimited `project sites`. Detailed instructions are provided here `https://pages.github.com/` 

## In your angular project, add new remote for GitHub

```
git remote add origin https://github.com/hoodaajay99/angular-github-pages-demo.git
```

Verify

```
$ git remote -v
origin	https://github.com/hoodaajay99/angular-github-pages-demo.git (fetch)
origin	https://github.com/hoodaajay99/angular-github-pages-demo.git (push)
```

## Add `angular-cli-ghpages` npm module to your project. 

```
cd angular-github-pages-demo
ng add angular-cli-ghpages
```

> `angular-cli-ghpages` is npm module which simplify the build deploy process for angular apps. It is build on top of https://github.com/tschaub/gh-pages

## Deploy your project to GitHub pages.

```
ng deploy --base-href=https://<username>.github.io/<repositoryname>
ng deploy --base-href=https://hoodaajay99.github.io/angular-github-pages-demo
```

Enter github credentials when prompted.
Your angular application is deployed to `gh-pages` branch of your repository.

> `--base-href=https://<username>.github.io/<repositoryname>` updated the base href reference in your index.html file

## Verify/Update GitHub Pages settings

- Goto Github repository settings -> GitHub Pages section
- Make sure `Source` is set to `gh-pages` branch. 
- Your site is published at https://hoodaajay99.github.io/angular-github-pages-demo/

> Your site may still not be accessible, because github pages by default looks for sites made with jekyll.


## **Important:** Add .nojekyll file to root of your pages repo

It is now possible to completely bypass Jekyll processing on GitHub Pages by creating a file named .nojekyll in the root of your pages repo and pushing it to GitHub.

> Site is accessible at https://hoodaajay99.github.io/angular-github-pages-demo/

> Note: It may take some time for the application to be become available, since github servers take some time to update the site.
