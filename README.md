# 2017.code4lib.org

[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/C4L-PHL?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Intro

This site was developed by the [Code4Lib 2017 Conference Committee Website Working Group](http://wiki.code4lib.org/2017_Conference_Committees#Website_Working_Group) based on a design by the [2016 working group](http://wiki.code4lib.org/2016_Conference_Committees#Website_Working_Group). The site was designed to provide a comprehensive overview
of the Code4Lib 2017 Annual Conference. A great deal of conference and organizational info can be found on the [Code4Lib Wiki](http://wiki.code4lib.org/Main_Page) and the [Code4Lib Site](http://code4lib.org), but this site should serve as a gateway to the various sources of Code4Lib information while providing visitors with a user-friendly way to find conference-specific info.

This site was designed with future users in mind, so the group chose platforms that would be accessible to a wide range of users: [Jekyll](http://jekyllrb.com) and [GitHub Pages](https://pages.github.com).  We also custom build  Bootstrap 3.3.4 from less files for basic site colors and fonts.

## About Jekyll

[Jekyll](http://jekyllrb.com) is a Rails gem that generates static websites from markdown, HTML, and other formats. See the [official Jekyll documentation](http://jekyllrb.com/docs/home/) for details.


## Contributing

Steps for contributing have been documented in the [wiki on the 2016 site's GitHub page](https://github.com/code4lib/2016.code4lib.org/wiki) and will be updated as needed.

See a list of [outstanding issues](https://github.com/code4lib/2017.code4lib.org/issues). The following example uses "issue#3" as a subject. That's the branch name and used in the commit message.

### Setup:

1. cd to repo root and ```git pull```
2. ```bundle install```
3. Continue with step 3 below

### Contributing:
1. Make sure you're on the master branch
  * ```git checkout master```
2. Make sure your master branch is up to date
  * ```git pull origin master```
3. Start up jekyll
  * ```jekyll serve```
  * check [http://localhost:4000](http://localhost:4000)
  * make sure that your ```_data/path.yml``` file's content is simply ```'/'```
4. create a new branch for your changes
  * ```git checkout -b issue#3```
5. make changes, check [http://localhost:4000](http://localhost:4000) to see your changes
6. add your changed files
  * ```git add {changed-files}```
7. commit your changes with a fancy message
  * ```git commit -m "fixes issue #3"```
8. add your branch to the repo
  * ```git push --set-upstream origin issue#3```
9. switch back to the master branch
  * ```git checkout master```

10. go to https://github.com/code4lib/2017.code4lib.org
11. make a pull request base:master and compare:issue-3
12. wait for someone to test your changes and merge
13. do the dance of joy

### Managing Pull Requests

1. Follow steps 1-3 from Subsequent work
2. Get any remote branches
  * ```git fetch```
3. Switch to the branch in question
  * ```git checkout BRANCHNAME```
4. Check [http://localhost:4000](http://localhost:4000) that nothing is broken
5. Merge that branch and master (easiest to manage on the github site)

### Making changes to site CSS
Site uses Bootstrap 3.3.5 and SCSS.

SCSS partials  are found in /assets/_scss. Edit ```_variables.scss``` to override bootstrap defaults.
You're encouraged to reuse those variables throughout the custom scss files.
You should not edit anything in /assets/_scss/bootstrap as this represents the official boostrap-sass files.

### Sponsor Badges
Use the following template for sponsor badges:

```
<svg alt="" width="100%" xmlns:xlink="http://www.w3.org/1999/xlink">
    <use class="sponsor-badge <add-class>" xlink:href="/assets/img/badges/badges.svg#<badge-name>"></use>
</svg>
```

Where ```<badge-name>``` is one of the following:
* trophy-badge
* star-badge
* thumbs-badge
* medal-badge (with ```<add-class>``` = **gold**, **silver**, or **bronze**)

The container element (i.e., wrapper of ```<svg>```), should have the style ***position:relative** (allows the svg to scale). Or use bootstrap column classes ```col-xs-*```,```col-sm-*```, etc.

Edit the colors in ```/assets/css/main.scss``` under the **SVGs** header.

## Site Structure

coming soon...


## Code4Lib Conference Website Workflows

### Presentations

#### Overview

1. Proposal Submission
2. Vote for Proposals
3. Publish Selected Talks


#### Proposal Submission

##### Create Proposal Form

Form Fields

* Title
* Absctract
* Speaker Name
* Speaker Affiliation (optional)
* Speaker Email
*(repeat Name/Affiliation/Email for speaker 2-5)*

##### Publish Proposal Form

**schedule/timeline.html**

1. Uncomment and add the submission link.
2. Uncomment the link to ```proposed-talks.html```

**/proposed-talks.html**

1. In Google Drive, go to the Responses Sheet. Publish this sheet to the web and copy the resulting url.
2. Change **ResponseSheetURL** to the url
3. Edit the rest of the frontmatter to reflect the Sheet Columns (Title, Abstract, & Presenter Names)
4. Uncomment the submission link. Add the submission url.

#### Vote for Proposals

**/schedule/timeline.html**
1. Uncomment and add the link to the voting system.

#### Publish Selected Proposals

1. Make a copy of the response sheet
2. Add columns for additional metadata:
    * day
    * group
    * spot
    * length
    * startTime (timestamp)
    * endTime (timestamp)
    * milTime (readable militaryTime)


##### Convert sheet to _post files

use [FromSheetsToJekyll](http://queryluke.github.io/fromSheetsToJekyll/)

(better instructions coming soon)

Template
```
layout: presentation
speakers-text: [Presenter-Name]
speakers:
- [Presenter-Email-1|hash]
- [Presenter-Email-2|hash]
- [Presenter-Email-3|hash]
- [Presenter-Email-4|hash]
- [Presenter-Email-5|hash]
voteCount: [Vote-Count]
day: [Day]
group: [Group]
spot: [Spot]
length: [Length]
type: talk
categories: talks
startTime: [StartTime]
endTime: [EndTime]
milTime: [Time]

```

Values in brackets ```[]``` represent Spreatsheet Column Labels.
For the initial ingest, it is not necessary to have all the values (e.g., day, group, spot, length) as these will be decided later.

Unzip the resulting file and put contents into ```/_posts```

/talks/index.html should now have all the selected talks

### Preconference Workshops

#### Overview

1. Proposal Submission
2. Vote for Proposals
3. Publish Selected Workshops

### Speakers

#### Overview

1. Get Speaker Info
2. Import & Check Speaker Data (on-going)

### Schedule


## Resources
More details are available in the [GitHub wiki for the 2016 page](https://github.com/code4lib/2016.code4lib.org/wiki)

[Conference Website Working Group wiki page: Working Group Documents](http://wiki.code4lib.org/Website_Working_Group_Documents)
