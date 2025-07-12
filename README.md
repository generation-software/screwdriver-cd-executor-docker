# Docker Executor

[![Version][NPM badge]][NPM URL]
[![GitHub Workflow Status][GitHub Workflow Status badge]][GitHub Workflow Status URL]
![GitHub Last Commit badge]
![License badge]

> Docker Executor for Screwdriver

This is an executor for Screwdriver CD that interacts with Docker (local and remote).

## Usage

```bash
npm install screwdriver-cd-executor-docker
```

### Initialization

The class has a variety of knobs to tweak when interacting with Docker.

| Parameter        | Type  |  Description |
| :-------------   | :---- | :-------------|
| config        | Object | Configuration Object |
| config.docker | Object | [Dockerode configuration][dockerode] |
| config.ecosystem | Object | Screwdriver Ecosystem (ui, api, store, etc.) |
| config.fusebox | Object | [Circuit Breaker configuration][circuitbreaker] |
| config.launchVersion | String | Launcher container version to use (stable) |
| config.prefix | String | Prefix to container names ("") |
```js
const executor = new DockerExecutor({
    docker: {
        socketPath: '/var/lib/docker.sock'
    },
    launchVersion: 'stable'
});
```

### Methods

For more information on `start`, `stop`, and `stats` please see the [executor-base].

## Testing

```bash
npm test
```

## License

Code licensed under the BSD 3-Clause license. See LICENSE file for terms.

[circuitbreaker]: https://www.npmjs.com/package/circuit-fuses#constructor

[dockerode]: https://www.npmjs.com/package/dockerode#getting-started

[executor-base]: https://github.com/screwdriver-cd/executor-base

[GitHub Last Commit badge]: https://img.shields.io/github/last-commit/QubitPi/screwdriver-cd-executor-docker/master?logo=github&style=for-the-badge
[GitHub Workflow Status badge]: https://img.shields.io/github/actions/workflow/status/QubitPi/screwdriver-cd-executor-docker/ci-cd.yaml?branch=master&logo=github&style=for-the-badge
[GitHub Workflow Status URL]: https://github.com/QubitPi/screwdriver-cd-executor-docker/actions/workflows/ci-cd.yaml

[License badge]: https://img.shields.io/npm/l/screwdriver-cd-executor-docker.svg?style=for-the-badge

[NPM badge]: https://img.shields.io/npm/v/screwdriver-cd-executor-docker.svg?style=for-the-badge
[NPM URL]: https://www.npmjs.com/package/screwdriver-cd-executor-docker
