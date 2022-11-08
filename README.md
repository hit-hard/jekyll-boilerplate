# Jekyll boilerplate

A starting point for Jekyll projects 

## Introduction

This static site is build using Jekyll (a static site generator) which uses liquid to make things easy.

## Prerequisites

Jekyll requires the following:

- [Ruby](https://www.ruby-lang.org/en/downloads/) version **2.5.0** or higher, including all development headers (check your Ruby version using `ruby -v`)
- [RubyGems](https://rubygems.org/pages/download) (check your Gems version using `gem -v`)

## Guides

For detailed install instructions, follow the guide for your operating system.

- [macOS](https://jekyllrb.com/docs/installation/macos/)
- [Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/)
- [Other Linux](https://jekyllrb.com/docs/installation/other-linux/)
- [Windows](https://jekyllrb.com/docs/installation/windows/)

## Instructions

### Step 1

Once you install Ruby and RubyGems, now follow the instructions below to install Jekyll and bundler gems

```shell
gem install jekyll bundler
```

### Step 2

Initial npm 

```shell
npm init -y
```

Within the package.json file, replace the **scripts** with the following

```shell
"scripts": {
    "dev": "bundle exec jekyll serve --trace --livereload",
    "lint:style": "npx stylelint \"**/*.scss\"",
    "fix:style": "npx stylelint --fix \"**/*.scss\""
}
```

and add the following devDependencies after the scripts

```shell
"devDependencies": {
    "stylelint": "^14.3.0",
    "stylelint-config-idiomatic-order": "^8.1.0",
    "stylelint-config-standard-scss": "^3.0.0"
}
```

Note the commas after each object in the json file.

now do:

```shell
npm install
```

**Note**: Jekyll is not a NPM package site, we use this in order to use some npm packages such as stylint etc. But we do not want those to be ship to the codebase, we only use them for the dev version. That is why you will not see the package.json and package-lock.json in the codebase.

You will see them once you finish this step, but don't worry, they are ignored in the .gitignore file.

### Step 3

Run the site and make it available on a local server.

```shell
npm run dev
```

### Step 3

Browse to [http://localhost:4000](http://localhost:4000/) to see the site

**Note**:

If you are using Ruby version 3.0.0 or higher, step 3 [may fail](https://github.com/github/pages-gem/issues/752). You may fix it by adding `webrick` to your dependencies: 

```shell
bundle add webrick
```



If you encounter any errors during this process, check that you have installed all the prerequisites in [Requirements](https://jekyllrb.com/docs/installation/#requirements). If you still have issues, see [Troubleshooting](https://jekyllrb.com/docs/troubleshooting/#configuration-problems).
