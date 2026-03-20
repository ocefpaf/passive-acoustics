## Passive Acoustics -- Eavesdropping on Fish, Whales, and Other Sea Creatures

Passive acoustics is a rapidly emerging field of marine biology that since recently has received a lot of attention from fisheries scientists and managers. Passive Acoustic Monitoring (PAM) can serve as a useful monitoring tool that complements traditional survey methodologies (aerial, visual, trawl, etc.).

## Contributing to the documentation
See [CONTRIBUTING](CONTRIBUTING.md).

## Deploying site locally
Requirements:
* bundle
* Jekyll

See [IOOS How To: Local Development with Jekyll](https://ioos.github.io/ioos-documentation-jekyll-skeleton/howto.html#local-development-with-jekyll).

Clone this repository:
```commandline
git clone https://github.com/ioos/passive-acoustics.git
```
To build the site, in the `passive-acoustics/` directory run:
```commandline
bundle exec jekyll serve --config _config.yml --watch --verbose --incremental
```
This will deploy a website at: http://127.0.0.1:4000/passive-acoustics/

Make edits to the appropriate markdown files in `_docs/`. 

If changing headers and menus, stop the running server by entering `ctrl-c` in the terminal. Then run:
```commandline
bundle exec jekyll clean
```
Then build the site again.
```commandline
bundle exec jekyll serve --config _config.yml --watch --verbose --incremental
```
And review at http://127.0.0.1:4000/passive-acoustics/