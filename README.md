# inclusion

Welcome to the public home for the ongoing efforts at Airbnb to build an engineering culture where all engineers feel like they can belong.

## Infractions

We are publicly sharing `infractions.yml`. `infractions.yml` is a data file of terms that we consider legacy in Airbnb code and systems. These terms are considered legacy since they do not promote belonging and inclusion.

## Getting started

The data file format is agnostic to any particular tool and is meant to be general enough to be adapted to any tool.

At Airbnb we use the [woke](https://github.com/get-woke/woke) source code scanning tool. `generate_woke_config` converts infractions.yml to a format that woke understands.

```shell
./generate-woke-config "infractions.yml" > woke.yml
woke -c woke.yml source_code/
```

## Contributing
Please open an issue on this GitHub repository. Contributors are expected to follow the [Code of Conduct](https://github.com/airbnb/.github/blob/main/CODE_OF_CONDUCT.md).

## About this repository

The list of non-inclusive terms in this repository was created by and will evolve in close collaboration with Airbnb employees who are members of the affected communities.
