# Rosid

[![Travis Build Status](https://travis-ci.org/electerious/Rosid.svg?branch=master)](https://travis-ci.org/electerious/Rosid) [![AppVeyor Status](https://ci.appveyor.com/api/projects/status/9pm47cxt4oqq0fg1?svg=true)](https://ci.appveyor.com/project/electerious/rosid) [![Coverage Status](https://coveralls.io/repos/github/electerious/Rosid/badge.svg?branch=master)](https://coveralls.io/github/electerious/Rosid?branch=master) [![Dependencies](https://david-dm.org/electerious/Rosid.svg)](https://david-dm.org/electerious/Rosid#info=dependencies) [![Donate via Flattr](https://img.shields.io/badge/flattr-donate-009cde.svg)](https://flattr.com/profile/electerious) [![Donate via PayPal](https://img.shields.io/badge/paypal-donate-009cde.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=CYKBESW577YWE)

Just-in-time server and static site generator written in [Node.js](https://nodejs.org/). Rosid transforms your files on-the-fly before serving them to the browser.

## Contents

- [Introduction](#introduction)
- [Get started](#get-started)
- [Documentation](#documentation)
- [Tips](#tips)

## Introduction

### What is Rosid?

Rosid is a framework that focus on two features:

1. A **development server with live reloading**, which transforms files as soon as you request them.
2. A **static site generator**, which transforms files using defined transform functions.

### Why Rosid?

- It doesn't force you to use a defined directory structure
- It's built on popular modules like [Browsersync](https://www.browsersync.io)
- It integrates nicely with tools you are are already using to transform your files (e.g. [Gulp](http://gulpjs.com), [Grunt](http://gruntjs.com) or Vanilla JS)
- It's lightweight and only includes what it really needs
- Transformed files don't need to be saved along their source files
- It lets you compile code to static files to host them anywhere

### How does it work?

Rosid starts a server and compares requested URLs with [user-defined patterns](docs/Routes.md). An associated [file handler](docs/Handlers.md) will be executed when a pattern matches. The handler receives information about the request and can transform the file, which will be sent to the browser.

## Get started

Rosid can be integrated into your project in two ways: Using the CLI *or* using the API of Rosid. Check out our [get started guide](docs/Get%20started.md) for more information.

## Documentation

### Requirements

Rosid depends on...

- [Node.js](https://nodejs.org/en/) (v6.2.0 or newer)
- [npm](https://www.npmjs.com)

Make sure to install and update all dependencies before you setup Rosid.

### Routes

Routes tell Rosid how to transform your code. They specify which [handler](docs/Handlers.md) should be executed when a defined pattern matches. [Routes &#187;](docs/Routes.md)

### Handlers

Handlers are functions which load and transform files. You can write them on your own or use existing handlers from npm. [Handlers &#187;](docs/Handlers.md)

### API

Rosid can be integrated into your project using its API *or* CLI. The API gives you more flexibility and allows you to use Rosid in your existing asset pipeline or toolset. [API &#187;](docs/API.md)

### CLI

The CLI of Rosid is located in the `bin` folder and allows you to run the `serve` and `compile` functions without adding JS files to your project. This approach is simpler than using the API, but provides less flexibility. [CLI &#187;](docs/CLI.md)

### Options

If you want more control over Rosid, pass an object of options to it. [Options &#187;](docs/Options.md)

## Tips

- Install Rosid without optional dependencies using npm's `--no-optional` flag. This speeds up the installation and skips a lot of dependencies. It's perfect when used in production. The downside: Running the `serve` function isn't possible anymore.
