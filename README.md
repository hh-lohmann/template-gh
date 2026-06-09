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
    - Replace "...year..." appropriately
    - Replace "...author..." appropriately
      - "...author..." should match with "author.name" in package.json and "...author..." in README.md (see below)
    - Replace "...email..." appropriately
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
    - "description" should match with "...description..." in README.md (see below)
    - Replace "..." placeholders with content or delete the respective entry
      - Replace "...project-name..." with the value you have set for the "name" entry
      - Replace "...repo-owner..." with the GitHub user / organisation that hosts the repo
    - "author.name" should match with "...author..." in LICENSE and "...author..." in README.md (see below)
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

      > HTML comments starting with "<!--????" (like this one) are tips / infos and may be deleted (other comments may be literal parts of the template)

  - Delete unused sections ("## XY")

  - Replace "[...scope/path...]" placeholders with potential npm "@" scope (e.g. "@your-name/") or GitHub repo owner path (e.g. "your-name/") or delete them

  - Replace placeholders surrounded by "..." with content

  - Replace lines starting with "..." by content or delete them

  - Add sections, change order etc. according to your needs

-->

# ...project-title...

...description...

*[...author... &lt;...email...&gt;](mailto:...email...?subject=...project-name...)*

<!--????
  Switch to Pages version for better UI
  - Styles are respected in Pages view, but ignored in repo, so this is only visible in repo view
  - Delete if irrelevant
-->
<p align="center" aria-description="Hint on GitHub repo view to switch to GitHub Pages view" style="display:none;">
  <b><i>This page may be displayed less optimal in repo view - you may switch to <a href="https://...repo-owner....github.io/...project-name.../">the GitHub Pages view</a> instead</i></b>
</p>


## Caution

**... special warning if exposed function(s) / executable(s) may allow / imply risky things like changing or using sensitive settings like credentials**


## Synopsis

<!--???? ! library vs. cli -->

... syntax of exposed function(s) / executable(s) and / or short explanation

<!--???? library, else delete -->
```js
  import { ... } from '...project-name...'
```

<!--???? cli, else delete -->
```shell
  ...project-bin... ...parameters...
```


## Parameters

... parameters of exposed function(s) / executable(s)


## Returns

... codes / states / data returned by exposed function(s) / executable(s)


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
See <a aria-description="Release vs. Dev switch = GitHub Pages vs. local file" href="https://...repo-owner....github.io/...project-name.../demo.html" onclick="if( location.hostname.replace( /\d/g, '' ).replaceAll( '.', '' ) === '' || location.hostname === 'localhost' ){ this.href='./demo.html'; alert( 'Dev environment detected - switching to local version' ); }">demo.html</a>


## Caveats

... things that may not work / not work as expected


## Installation

<!--???? cli, else delete -->
CLIs should be installed systemwide ("global"). Strip off the `-g` parameter to explicitly restrict to a project bounded usage.

Pick for your preferred package manager:

<!--???? add " -g" for cli -->
```shell
  npm i [...scope/path...]...project-name...
```

<!--???? add " -g" for cli -->
```shell
  pnpm i [...scope/path...]...project-name...
```

<!--???? add " -g" for cli -->
```shell
  bun i [...scope/path...]...project-name...
```

```shell
  # For Yarn you should double check docs for your and / or
  # current Yarn version, newer versions do not treat `i package_name`
  # as an alias for `add ...` and exclude global installations
  yarn add [...scope/path...]...project-name...
```


## Details

... for deeper understanding what the exposed function(s) / executable(s) and / or short explanation does / do


## References

<!--???? Sources to refer to in text by GFM Markdown internal links (cf. https://github.github.com/gfm/) -->

### ...authors...: ...title...
  * ...info-about-source...
  * ...https://url-for-source...

