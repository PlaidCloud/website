# The PlaidCloud documentation

This repository contains the assets required to build the [PlaidCloud documentation](https://docs.plaidcloud.com/). We're glad that you want to contribute!

There are also CI and beta versions of the documentation here:
 * [PlaidCloud CI Documentation](https://docs.plaidcloud.io)
 * [PlaidCloud Beta Documentation](https://docs.plaidcloud.net)

## Using this repository

You can run the website locally using Hugo (Extended version), or you can run it in a container runtime. For web deployments, we strongly recommend using the container runtime, as it gives deployment consistency with the live website.
However, for documentation development locally, the live local server is fast and efficient.

## Prerequisites

To use this repository, you need the following installed locally:

- [npm](https://www.npmjs.com/)
- [Go](https://golang.org/)
- [Hugo (Extended version)](https://gohugo.io/)
- A container runtime, like [Docker](https://www.docker.com/).

Before you start, install the dependencies. Clone the repository and navigate to the directory:

```bash
git clone https://github.com/PlaidCloud/website.git
cd website
```

The PlaidCloud website uses the [Docsy Hugo theme](https://github.com/google/docsy#readme). Even if you plan to run the website in a container, we strongly recommend pulling in the submodule and other development dependencies by running the following:

```bash
# pull in the Docsy submodule
git submodule update --init --recursive --depth 1
```

## Running the website using a container

To build the site in a container, run the following to build the container image and run it:

```bash
make container-image
make container-serve
```

If you see errors, it probably means that the hugo container did not have enough computing resources available. To solve it, increase the amount of 
allowed CPU and memory usage for Docker on your machine ([MacOSX](https://docs.docker.com/docker-for-mac/#resources) and 
[Windows](https://docs.docker.com/docker-for-windows/#resources)).

Open up your browser to <http://localhost:1313> to view the website. As you make changes to the source files, Hugo updates the website and forces a browser refresh.

## Running the website locally using Hugo

To build and test the site locally, run:

```bash
# install dependencies
npm ci
make serve
```

Now you can just run this command:

```bash
hugo serve -D --panicOnWarning
```

This will start the local Hugo server on port 1313. Open up your browser to <http://localhost:1313> to view the website. As you make changes to the source files, Hugo updates the website and forces a browser refresh.

Keep in mind that the local server is not recreating all the static content so changes to templates might require a restart of the local hugo server for the template changes to be incoporated in what you see.


## Troubleshooting

### error: failed to transform resource: TOCSS: failed to transform "scss/main.scss" (text/x-scss): this feature is not available in your current Hugo version

Hugo is shipped in two set of binaries for technical reasons. The current website runs based on the **Hugo Extended** version only. In the [release page](https://github.com/gohugoio/hugo/releases) look for archives with `extended` in the name. To confirm, run `hugo version` and look for the word `extended`.

### Troubleshooting macOS for too many open files

If you run `make serve` on macOS and receive the following error:

```bash
ERROR 2020/08/01 19:09:18 Error: listen tcp 127.0.0.1:1313: socket: too many open files
make: *** [serve] Error 1
```

Try checking the current limit for open files:

`launchctl limit maxfiles`

Then run the following commands (adapted from <https://gist.github.com/tombigel/d503800a282fcadbee14b537735d202c>):

```shell
#!/bin/sh

# These are the original gist links, linking to my gists now.
# curl -O https://gist.githubusercontent.com/a2ikm/761c2ab02b7b3935679e55af5d81786a/raw/ab644cb92f216c019a2f032bbf25e258b01d87f9/limit.maxfiles.plist
# curl -O https://gist.githubusercontent.com/a2ikm/761c2ab02b7b3935679e55af5d81786a/raw/ab644cb92f216c019a2f032bbf25e258b01d87f9/limit.maxproc.plist

curl -O https://gist.githubusercontent.com/tombigel/d503800a282fcadbee14b537735d202c/raw/ed73cacf82906fdde59976a0c8248cce8b44f906/limit.maxfiles.plist
curl -O https://gist.githubusercontent.com/tombigel/d503800a282fcadbee14b537735d202c/raw/ed73cacf82906fdde59976a0c8248cce8b44f906/limit.maxproc.plist

sudo mv limit.maxfiles.plist /Library/LaunchDaemons
sudo mv limit.maxproc.plist /Library/LaunchDaemons

sudo chown root:wheel /Library/LaunchDaemons/limit.maxfiles.plist
sudo chown root:wheel /Library/LaunchDaemons/limit.maxproc.plist

sudo launchctl load -w /Library/LaunchDaemons/limit.maxfiles.plist
```

This works for Catalina as well as Mojave macOS.

## Thank you

PlaidCloud thrives on community participation, and we appreciate your contributions to our website and our documentation!
