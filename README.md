# best-values-example

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

One of the best values parsing example charts here, exhibits several more complicated examples

**Homepage:** <https://github.com/norwoodj/helm-docs/tree/master/example-charts/best-values-example>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| John Norwood | <norwood.john.m@gmail.com> |  |

## Source Code

* <https://github.com/norwoodj/helm-docs/tree/master/example-charts/best-values-example>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.databasesToCreate[0] | string | `"postgresql"` | default database for storage of database metadata |
| config.databasesToCreate[1] | string | `"hashbash"` | database for the [hashbash](https://github.com/norwoodj/hashbash) project |
| config.usersToCreate[0] | object | `{"admin":true,"name":"root"}` | admin user |
| config.usersToCreate[1] | object | `{"name":"hashbash","readwriteDatabases":["hashbash"]}` | user with access to the database with the same name |
| statefulset.extraVolumes | list | `[{"emptyDir":{},"name":"data"}]` | Additional volumes to be mounted into the database container |
| statefulset.image.repository | string | `"jnorwood/postgresq"` | Image to use for deploying, must support an entrypoint which creates users/databases from appropriate config files |
| statefulset.image.tag | string | `"29"` |  |
| statefulset.livenessProbe | object | `{"enabled":false}` | Configure the healthcheck for the database |
| statefulset.podLabels | object | `{}` | The labels to be applied to instances of the database |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
