# Paperboy-docs
Documentations about ThePhilosophyPaperboy 2.0 project. Check out the actual MVP version [here](https://thephilosophypaperboy.com/).


## Entities

### `Journals`

| Field | Type | Nullable | Note |
|:------|:-:|:-:|:--|
| Id | `Integer` | `false` | |
| Url | `String` | `false` | |
| Name| `String` | `false` | |
| Publisher | `String` | `true` | Could be the url domain's name |
| Active | `Boolean` | ... | if `false`, engine should not call the feed |
| Last update | `Date` | `true ` | Last RSS call date |
| Last imported | `String` | `true ` | *Last RSS retrieved per last imported:* 1) could be `0`: no new items retrieved, should generate an alert  2) colud be `null`: feed has no item 3) could be a number |
| Total imported | `Number` | `true ` | |
| Created at | `Date` | `false` | |

### `Articles`
*Need UX/UI update*

| Field | Type | Nullable |  Note |
|:------|:-:|:-:|:--|
| Id | `Integer` | `false` | |
| Unique ref | `String` | `false` | This ID should prevent duplicated importation, could be generate from url |
| Doi | `String`| `true` |  It can be parsed from Url |
| Journal | `Key` | `false` | One to one relation |
| Url | `String` | `false` |
| Name| `String` | `false` | |
| Authors | `String` | `true` | Sometime could be "creator", sometime "authors". We need schema|
| Description | `String` | `true` |
| Publication Date | `Date` | `false` | Date should be formatted, we'll retrieve differents format |


### `Users`

| Field | Type | Nullable |  Note |
|:------|:-:|:-:|:--|
| Id | `Integer` | `false` |
| Mail | `String` | `false` |
| First Name | `String` | `false` |
| Last Name | `String` | `false` |
| Registered at | `Date` | `false` | |
| Last login | `Date` | `true` | |
| Timelines | `Array` | `true` | Array of key. Users timelines content |
| Articles | `Array` | `true` |  Array of key. Users favorites articles |

### `Timelines`
*Need UX/UI update*

| Field | Type | Nullable |  Note |
|:------|:-:|:-:|:--|
| Id | `Integer` | `false` |
| Name | `String`| `false` | 
| Journals | `Array` | `true` | Array of key. Single timeline content |
| Author | `key` | `false` | 
| Ready to publish | `Boolean` | ... | **Not for MVP!** It sent alert to admin |
| Published | `Boolean` | ... | **Not for MVP!** If admin want to really publish this|
| Created at | `Date` | `false` | |


## Backend Workaround

The backend is basically a RSS engine who collect data, i.e. Aritcles,  from RSS source. i.e.: Journals

![RSS schema](img/RSS-scheme.png)

### CRUD Admin panel
This can be an Admin panel example of Journals RSS source

| Source Name       | State | Updates | Items imported | Actions |
|:-----------|:-:|:--|:-:|:-:|
| *Etudes Platoniciennes* | working/paused | **Next update:** 55 mins, **Last updated:** 3 mins ago, **Last imported:** 0 items | 120 | stop/play/edit/remove |
| *Ancient Philosophy Today* |  working/paused | **Next update:** 55 mins, **Last updated:** 3 mins ago, **Last imported:** 20 items | 34 | stop/play/edit/remove |



And this can be an Admin panel example of Articles RSS items

| Item Name       | Permalink | Date | Authors | Source | Actions |
|:-----------|:-:|:--|:-:|:-:|:-:|
| *Acids and Rust: A New Perspective on the Chemical Revolution* | http://... | 2021-02-23 03:29:38 | David, A., Ariyo, K. |  *Ancient Philosophy Today* | edit/hide/remove |
| *Beyond Causal Explanation: Einstein’s Principle Not Reichenbach’s* |  http://... | 2021-02-23 03:29:38  | Gupta, R., Morain, S. R. |  *Ancient Philosophy Today* | edit/hide/remove |



## Frontend

Check for wireframe [here](https://github.com/lc-d/paperboy-docs/tree/main/prototype/wireframes)