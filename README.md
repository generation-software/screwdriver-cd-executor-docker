# Docker Executor

[![Version][npm-image]][npm-url]
![Downloads][downloads-image]
[![GitHub Workflow Status][GitHub Workflow Status]](https://github.com/QubitPi/screwdriver-cd-executor-docker/actions/workflows/ci-cd.yml)
![Last Commit](https://img.shields.io/github/last-commit/QubitPi/screwdriver-cd-executor-docker/master?logo=github&style=for-the-badge)
[![Open Issues][issues-image]][issues-url]
![License][license-image]

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

[npm-image]: https://img.shields.io/npm/v/screwdriver-cd-executor-docker.svg?style=for-the-badge
[npm-url]: https://www.npmjs.com/package/screwdriver-cd-executor-docker
[downloads-image]: https://img.shields.io/npm/dt/screwdriver-cd-executor-docker.svg?style=for-the-badge
[license-image]: https://img.shields.io/npm/l/screwdriver-cd-executor-docker.svg?style=for-the-badge
[issues-image]: https://img.shields.io/github/issues/screwdriver-cd/screwdriver.svg?style=for-the-badge
[issues-url]: https://github.com/QubitPi/screwdriver-cd-executor-docker/issues

[dockerode]: https://www.npmjs.com/package/dockerode#getting-started
[circuitbreaker]: https://www.npmjs.com/package/circuit-fuses#constructor
[executor-base]: https://github.com/screwdriver-cd/executor-base

[GitHub Workflow Status]: https://img.shields.io/github/actions/workflow/status/QubitPi/screwdriver-cd-executor-docker/ci-cd.yml?branch=master&logo=github&style=for-the-badge
