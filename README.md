# ZEBOV 

This is the begginings of an interactive description of the all known ZEBOV outbreaks.
Currently it is being used as an example of a serverless customised auspice build.

## build customised serverless auspice instance
> _This is currently in flux_

* Ensure auspice is available globally -- i.e. `auspice -h` works.

* Development (i.e. live updating as you edit the code) can either be done from this repo, or from the auspice repo:
```bash
# cwd: ZEBOV
auspice develop --verbose --extend ./auspiceCustomisations/config.json --gh-pages .
# cwd: auspice source (e.g. nextstrain/auspice) -- this assumes a certain folder structure
node auspice.js develop --verbose --extend ../../blab/ZEBOV/auspiceCustomisations/config.json --gh-pages ../../blab/ZEBOV
```

* To build the auspice code (note that this will create the `index.html` and `dist/*` files, you'll need to add `favicon.png` manually)
```bash
# cwd: ZEBOV
auspice build --verbose --extend ./auspiceCustomisations/config.json --serverless
```

* To view the website locally (this mimicks the server used for github pages, and is required to process requests for the datset JSON).
```bash
# cwd: ZEBOV
auspice view --verbose --gh-pages . --customBuild
```

## Deploy
Just push to master! (gh-pages is configured to run off of master branch). It will then be available at [blab.github.io/ZEBOV](https://blab.github.io/ZEBOV).
```bash
git push -f origin
```


## data json
This should use the auspice JSON spec v2.0, but this is not yet supported by auspice, so it is a mixture of v1.0 and v2.0. Upon release auspice should support v2.0
