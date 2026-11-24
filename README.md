[![competition](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/xingxing717/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/xingxing717/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

# site-generator-speed: a faster makefun-site

A faster drop-in for makefun-site 1.0.0, make.fun's own static site
generator. `solve.js` exports `run(input)`, which returns exactly the output
tree makefun-site's `build` returns for the same input — every page's
`index.html`, the index and tag pages, `build-report.txt` and each static
file, byte for byte — and `main.ts` is the driver that reads every case from
`/input/cases.json`, answers each with `run`, and writes `/output/answers.json`.

The implementation is original, dependency-free JavaScript. It follows the
reference's own rules (front matter, template dialect, Markdown subset, slug
rule, report) in a single pass: Markdown is lexed and rendered block by
block without building tokens, inline markup is scanned for the next
character that needs handling instead of being walked one character at a
time, HTML escaping copies whole plain runs, and templates render into one
array joined once. Slugs and long dates are cached within a case; nothing is
cached from one case to the next.
