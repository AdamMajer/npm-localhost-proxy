
Certain build environments like the [Open Build Service](https://build.opensuse.org/) require applications to be built without network access. This guarantees that sources are not altered during the actual build. The downside for Node applications is inability to run `npm install`. This proxy does two things

* it reads NPM published tarballs and presents them on a localhost interface
* it configures npm to use this interface as the registry to resolve dependencies via `npm config set registry`
* it runs `npm` with any parameters and then shuts down

- [Installation](#installation)
	- [From Release](#from-release)
	- [From Git](#from-git)
- [Usage](#usage)
- [Open Build Service](#open-build-service)

# Installation

## From Release
`npm install --production`

## From Git
`npm install`
`npm run build`

At this point the application is in `dist/` and can be used as from a tagged released version

# Usage

From the directory of an application where you want to run `npm install`,

	NPM_TGZ = (list of all NPM tgz tarballs or directory containing them)
	node ${path_to_this_app}/dist ${NPM_TGZ} install ${npm_install_param}

# Open Build Service

You can find this in `devel:languages:javascript`
