# Paperboy-docs
Documentations about ThePhilosophyPaperboy project


## Backend Idea

The backend is basically a RSS engine who collect data from RSS source. i.e.:

![RSS schema](img/RSS-scheme.png)

This can be an Admin panel example of RSS source

| Source Name       | State | Updates | Items imported | Actions |
|:-----------|:-:|:--|:-:|:-:|
| *Etudes Platoniciennes* | working/paused | **Next update:** 55 mins, **Last updated:** 3 mins ago, **Last imported:** 0 items | 120 | stop/play/edit/remove |
| *Ancient Philosophy Today* |  working/paused | **Next update:** 55 mins, **Last updated:** 3 mins ago, **Last imported:** 20 items | 34 | stop/play/edit/remove |


And this can be an Admin panel example of RSS items

| Item Name       | Permalink | Date | Authors | Source | Actions |
|:-----------|:-:|:--|:-:|:-:|:-:|
| *Acids and Rust: A New Perspective on the Chemical Revolution* | http://... | 2021-02-23 03:29:38 | David, A., Ariyo, K. |  *Ancient Philosophy Today* | edit/hide/remove |
| *Beyond Causal Explanation: Einstein’s Principle Not Reichenbach’s* |  http://... | 2021-02-23 03:29:38  | Gupta, R., Morain, S. R. |  *Ancient Philosophy Today* | edit/hide/remove |

## Frontend

Check for wireframe [here](https://github.com/lc-d/paperboy-docs/tree/main/prototype/wireframes)