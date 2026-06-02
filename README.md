<!--????

TEMPLATE for GitHub repos

Source: https://github.com/hh-lohmann/template-gh

The template consists of the files

  - LICENSE
    - Should not be deleted - exposing no license may hinder usage

  - .gitignore

  - package.json

  - ISSUES.json
    - TODO / Task Tracking / Planning for creating / maintaining the actual project
    - No fixed entry structure, but always programmatically parsable due to being JSON

  - README.md (this file)

Usage of full template:

  - LICENSE:
    - Replace "...year..." / "...author..." / "...email..." appropriately
    - "...author..." should match with "author.name" in package.json and "...author / contact..." in README.md (see below)
    - "...email..." should match with "author.email" in package.json and "...email..." in README.md (see below)
    - ! Any other changes except of verbatim text may make LICENSE invalid
    - If the given MIT license does not fit: Get alternative from https://choosealicense.com/

  - .gitignore
    - Add files / patterns
    - ! Note that exclusion for privacy (= not exposing sensitive contents to remotes) has always to be defined per case
    - ! Delete predefined files / patterns only if you know what you are doing
      - Note that superfluous entries are less harmful than missing ones

  - package.json
    - Should also be used for "meta information" if no publication for npm is planned
    - "name" entry should match with "...project-name..." in ISSUES.json and in README.md (see below)
    - Replace "..." placeholders with content or delete the respective entry
      - Replace "...project-name..." with the value you have set for the "name" entry
      - Replace "...repo-owner..." with the GitHub user / organisation that hosts the repo
    - "author.name" should match with "...author..." in LICENSE and "...author / contact..." in README.md (see below)
    - "author.email" should match with "...email..." in LICENSE and "...email..." in README.md (see below)
    - "license" has to be adjusted if "MIT" is not appropriate (see LICENSE)
    - "homepage" is predefined for the GitHub Pages rendering of the actual project since rich documentation often collides with the (sensible) restrictions in GitHub's repo view, so the Pages rendering is ofter the better entrance
    - Adjust defaults for "type" and "exports" if necessary
    - ! Delete predefined entries only if you know what you are doing
      - Note that superfluous entries are less harmful than missing ones

  - ISSUES.json
    - Keep the entry `"i": "ISSUES"` meaning "is an ISSUES files"
    - Replace "...project-name..." for "o" (meaning "ISSUES on") identically to the "name" entry of package.json and "...project-name..." in README.md (see below)
    - Note that this file is meant for development only, you should delete it from "release" branches

  - README.md (this file)
    - See below


Usage of this file as README.md for actual repo:

      > The suggested structure here follows the well established man page schema, see e.g. https://man7.org/linux/man-pages/man7/man-pages.7.html

      > HTML comments starting with "<!--????" (like this one) are tips / infos and may be deleted.

  - Delete unused sections ("## XY")

  - Replace "..." placeholders, lines starting with them and parts surrounded by them with content or delete them

  - "..." placeholders surrounded by "%%" must not be deleted, but always replaced with content

  - Add sections, change order etc. according to your needs

-->

# %%TITLE%%

%%SHORT_DESCRIPTION%% <!--???? Same as for "description" in package.json -->

*[...author / contact...](mailto:...email...?subject=...project-name...)*<!--???? Same as for "author" in package.json -->


## Synopsis

... syntax of exposed function(s) / executable(s) and / or short explanation


## Options

... parameters of exposed function(s) / executable(s)


## Exit status /  Return values

... codes / states / data returned by exposed function(s) / executable(s)
<!--???? for normal program termination, compare "Errors" -->


## Examples

... example calls for exposed function(s) / executable(s)


## Demo

<!--???? Interactive use case(s) for exposed function(s) / executable(s) -->

<!-- ! HTML demo: dev vs. release switch
  * GitHub repo view does not render HTML, so a GitHub Pages view is linked
    * NB: GitHub Pages allows to maintain a single instance of the HTML demo file in the repo
  * In dev a GitHub Pages view would require a Pages build for any change to check instead of live reloading, so JavaScript is utilized here to detect a dev environment and reroute the link to the local repo instance
    * NB: JavaScript is stripped off in GitHub repo view
    * "dev environment" is defined by using "localhost" or a numerical ID as hostname 
      * NB RegEx: `.replace( /\d/g, '' ).replaceAll( '.', '' )` instead of `location.hostname.replace( /[\d\.]/g, '' )` to avoid `[]` which may mislead Markdown parsers to read it as link syntax
  * Unfortunately GitHub repo view displays "<script>" tags and their contents as literal content (for security), so the JavaScript here has to be pressed into an "onclick"
-->
See <a aria-description="Release vs. Dev switch = GitHub Pages vs. local file" href="https://hh-lohmann.github.io/...package.../demo.html" onclick="if( location.hostname.replace( /\d/g, '' ).replaceAll( '.', '' ) === '' || location.hostname === 'localhost' ){ this.href='./demo.html'; alert( 'Dev environment detected - switching to local version' ); }">demo.html</a>


## Errors

... thrown errors of exposed function(s) / executable(s)
<!--???? for abnormal program termination, compare "Exit status / Return values" -->


## Caveats

... things that may not work / not work as expected


## Details

... for deeper understanding what the exposed function(s) / executable(s) and / or short explanation does / do


## Installation

Pick for your preferred package manager:

```shell
  npm i ...repo-owner.../...project-name...
```

```shell
  pnpm i ...repo-owner.../...project-name...
```

```shell
  yarn add ...repo-owner.../...project-name...
```

```shell
  bun i ...repo-owner.../...project-name...
```


## See also

<!--???? Source to refer to in text by GFM Markdown internal links (cf. https://github.github.com/gfm/) -->

### ...authors...: ...title...
  * ...https://the-authors-page.xyz/title...

