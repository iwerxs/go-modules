## Golang Modules, Packages and versioning

### Modules

<code>go get ./...</code>

uses Module Aware feature

another way to fetch all of the modules and dependencies is with
- go run
- go build
- go test

to clean local golang cache
<code>go clean -cache -modcache -i -r<code/>

then run <code>go build<code/>

