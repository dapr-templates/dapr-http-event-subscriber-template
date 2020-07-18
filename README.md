# dapr-event-subscriber-template

[![Test](https://github.com/mchmarny/dapr-event-subscriber-template/workflows/Test/badge.svg)](https://github.com/mchmarny/dapr-event-subscriber-template/actions?query=workflow%3ATest) ![Release](https://github.com/mchmarny/dapr-event-subscriber-template/workflows/Release/badge.svg?query=workflow%3ARelease) ![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/mchmarny/dapr-event-subscriber-template) [![Go Report Card](https://goreportcard.com/badge/github.com/mchmarny/dapr-event-subscriber-template)](https://goreportcard.com/report/github.com/mchmarny/dapr-event-subscriber-template)

Template project to bootstrap development of a new Dapr event processing services in `go`.

```shell
$ make help
tidy                           Updates the go modules and vendors all dependencies
test                           Tests the entire project
debug                          Runs uncompiled code in Dapr
build                          Builds local release binary
run                            Builds binary and runs it in Dapr
jsonevent                      Publishes sample JSON message to Dapr pubsub API
xmlevent                       Publishes sample XML message to Dapr pubsub API
binevent                       Publishes sample binary message to Dapr pubsub API
image                          Builds and publishes docker image
lint                           Lints the entire project
tag                            Creates release tag
clean                          Cleans up generated files
reset                          Resets go modules
help                           Display available commands
```

This project also includes GitHub actions in [.github/workflows](.github/workflows) that test on each `push` and build images and mark release on each `tag`. Other Dapr GitHub templates to accelerate development:
	
* [dapr-grpc-event-subscriber-template](https://github.com/mchmarny/dapr-grpc-event-subscriber-template)
* [dapr-http-event-subscriber-template](https://github.com/mchmarny/dapr-event-subscriber-template)
* [dapr-ui-app-template](https://github.com/mchmarny/dapr-ui-app-template)
* [dapr-http-cron-handler-template](https://github.com/mchmarny/dapr-http-cron-handler-template)

## usage 

* Click "Use this template" above and follow the wizard to select owner and name your new repo
* Clone your new repo locally (`git clone git@github.com:<GITHUB-USERNAME>/<GITHUB-USERNAME>.git`)
* Navigate to your newly cloned repo (`cd <REPO-NAME>`)
* Cleanup old artifacts (`make reset`)
* Init go module with your repo URL (`go mod init github.com/<GITHUB-USERNAME>/<GITHUB-USERNAME>`)
* Add missing modules (`go mod tidy`)
* Copy all dependencies locally (`go mod vendor`)
* Test to ensure everything is working (`make test`)

### deployment files

> If deploying to Kubernates you will also need to update the components and deployment files in the [deploy](deploy) directory and define your DockerHub username (`DOCKER_USER`)

To build and publish image:

```shell
make image
```

## Disclaimer

This is my personal project and it does not represent my employer. I take no responsibility for issues caused by this code. I do my best to ensure that everything works, but if something goes wrong, my apologies is all you will get.

## License

This software is released under the [MIT](./LICENSE)
