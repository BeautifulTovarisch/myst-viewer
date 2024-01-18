# TeXXen

> TODO: Choose a name lol

A straightforward plugin to render _proper_ LaTeX in the Obsidian editor.

## Overview

This plugin scans a markdown file in obsidian for La blocks interleaved in
the body of the document. This content is then delivered to a  installation,
which returns the content as a web-friendly SVG.

The motivation for writing this to allow Obsidian as a viable editor for math
and computer science notes intended to be published to my website.

## Usage

After installation and configuration, the plugin will automatically attempt to
render content appropriately when entering Reading mode.

## Project Scope

This plugin does not modify source files, nor does it convert between the two
flavors of markdown. Additionally, **all files** are treated as MyST and there
are no plans to support coexistence between the two within the same vault.

## Project Architecture

This core plugin is written in TypeScript and contains minimal dependencies.

### Major Dependencies

|Dependency    |Version|
|--------------|-------|
|Node          |20.11.0|
|TypeScript    |5.3.3  |
|Markdown It   |14.0.0 |
|Obsidian (API)|1.4.11 |

###  Server

TeXXen relies on a TeX server to compile LaTeX blocks. If the specified server
cannot be reached, LaTeX is rendered with limited support provided by MathJax.

> TODO: Create a dockerfile (or whatever the new thing is) of a working TeX
> installation and HTTP server.

## Getting Started

### Development Setup

Begin by creating an empty vault in order to test the plugin. A sample MD
file called `example.md` has been included to help with testing.

Next, clone this repository with:

```bash
cd <path/to/new/vault>/.obsidian/plugins

git clone git@github.com:BeautifulTovarisch/texxen.git --branch=develop
```

and install its dependencies:

```bash
npm i
```

Verify the setup by creating a build:

```bash
npm run build
```

This will create a file named `main.js`

### Installing the Plugin

TODO
