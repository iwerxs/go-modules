## Golang Modules, Packages and versioning

### Modules

<code>go get ./...</code>

uses Module Aware feature

another way to fetch all of the modules and dependencies is with

- go run
- go build
- go test

to clean local golang cache

<code>go clean -cache -modcache -i -r</code>

then run

<code>go build</code>

### Vendor Directory

<code>go mod vendor</code>

### Download all modules available for all versions of Go

fetch 3rd party packages from terminal

<code>go list -m -versions (pkg name)</code>

if vendor directory is present, remove it with

<code>rm -rf vendor</code>

then run cmd again

use this to download a 3rd part pkg, library, whilst not knowing which version to use. Versions above 'major' v2 versions, the path to the module needs to be adjusted 

another command to use is

<code>go mod download</code>

### Internals of Go Modules and Paths

- inside GoPath directory

- bin, pkg, src

- inside pkg: dep, mod, sumdb

- mod: all downloaded module packages are stored here

- inside mod is the cache dir, inside is download dir

### GOPROXY

<code>go env | grep "GOPROXY"</code>

returns

GOPROXY="https://proxy.golang.org,direct"

### GOSUMDB check sum

<code>go env | grep "GOSUMDB"</code>

returns

GOSUMDB="sum.golang.org"

### Semanic Import Versioning

- major version must be compatible: should be v0 or v1, Not v3

There are 3 stages for versioning
- v0 Unstable
- v1 Minor Stable
- v2 Major Stable

there has to explicity after v2 of a module package that needs to be downloaded

this is simply done by adding '/v(num)' a forward slash and then the explicit version number of the package needed to be installed within the module.

- example: rsc.io/quote/v3 gives an upgrade => v3.1.0

