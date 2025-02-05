# Advanced configuration

You can configure `burrito` with environment variables.

| Environment variable |         Description         |   Default    |
| :------------------: | :-------------------------: | :----------: |
| `BURRITO_REDIS_URL`  | the redis URL to connect to | `redis:6379` |

## Controllers' configuration

|            Environment variable                      |                                       Description                                            |             Default              |
| :--------------------------------------------------: | :------------------------------------------------------------------------------------------: | :------------------------------: |
|         `BURRITO_CONTROLLER_TYPES`                   |                                list of controllers to start                                  |        `layer,repository`        |
| `BURRITO_CONTROLLER_TIMERS_DRIFTDETECTION`           |                         period between two plans for drift detection                         |              `20m`               |
|     `BURRITO_CONTROLLER_TIMERS_ONERROR`              |           period between two runners launch when an error occurred in the controllers        |               `1m`               |
|   `BURRITO_CONTROLLER_TIMERS_WAITACTION`             |                   period between two runners launch when a layer is locked                   |               `1m`               |
|   `BURRITO_CONTROLLER_TIMERS_FAILUREGRACEPERIOD`     |           initial time before retry, goes exponential function of number failure             |              `15s`               |
| `BURRITO_CONTROLLER_LEADERELECTION_ENABLED`          |                           whether leader election is enabled or not                          |              `true`              |
|   `BURRITO_CONTROLLER_LEADERELECTION_ID`             |                               lease id used for leader election                              | `6d185457.terraform.padok.cloud` |
| `BURRITO_CONTROLLER_HEALTHPROBEBINDADDRESS`          |             address to bind the health probe server embedded in the controllers              |             `:8081`              |
|   `BURRITO_CONTROLLER_METRICSBINDADDRESS`            |               address to bind the metrics server embedded in the controllers                 |             `:8080`              |
| `BURRITO_CONTROLLER_KUBERNETESWEBHOOKPORT`           |             port used by the validating webhook server embedded in the controllers           |              `9443`              |

## Server's configuration

| Environment variable  |        Description         | Default |
| :-------------------: | :------------------------: | :-----: |
| `BURRITO_SERVER_ADDR` | addr the server listens on | `:8080` |

!!! info
    For webhook configuration see [Setup a git webhook](./git-webhook.md).

## Runners' configuration

Currently, runners' configuration is not exposed.

!!! info
    You can override some of the runner's pod spec. See [override the runner pod spec](../user-guide/override-runner.md) documentation.
