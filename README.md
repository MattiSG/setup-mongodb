# setup-mongodb

The missing action for MongoDB :tada:

- Faster and simpler than containers
- Works on Linux, Mac, and Windows
- Supports different versions

[![Build Status](https://github.com/ankane/setup-mongodb/workflows/build/badge.svg?branch=v1)](https://github.com/ankane/setup-mongodb/actions)

## Getting Started

Add it as a step to your workflow

```yml
    - uses: ankane/setup-mongodb@v1
```

## Versions

Specify a version

```yml
    steps:
    - uses: ankane/setup-mongodb@v1
      with:
        mongodb-version: 6.0
```

Currently supports

Version | `6.0` | `5.0` | `4.4` | `4.2`
--- | --- | --- | --- | ---
`ubuntu-22.04` | | | |
`ubuntu-20.04` | ✓ | default | ✓ |
`ubuntu-18.04` | ✓ | default | ✓ | ✓ |
`macos-12` | ✓ | default | ✓ | ✓ |
`macos-11` | ✓ | default | ✓ | ✓ |
`macos-10.15` | ✓ | default | ✓ | ✓ |
`windows-2022` | | default | |
`windows-2019` | | default | |

Test against multiple versions

```yml
    strategy:
      matrix:
        mongodb-version: [6.0, 5.0, 4.4, 4.2]
    steps:
    - uses: ankane/setup-mongodb@v1
      with:
        mongodb-version: ${{ matrix.mongodb-version }}
```

## Extra Steps

Run queries

```yml
    - run: mongosh --eval "db.version()"
```

Use `mongo` for MongoDB < 6

## Related Actions

- [setup-postgres](https://github.com/ankane/setup-postgres)
- [setup-mysql](https://github.com/ankane/setup-mysql)
- [setup-mariadb](https://github.com/ankane/setup-mariadb)
- [setup-elasticsearch](https://github.com/ankane/setup-elasticsearch)
- [setup-opensearch](https://github.com/ankane/setup-opensearch)
- [setup-sqlserver](https://github.com/ankane/setup-sqlserver)

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/setup-mongodb/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/setup-mongodb/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features
