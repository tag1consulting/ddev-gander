[![tests](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml/badge.svg)](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml)
[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/tag1consulting/ddev-gander)](https://github.com/tag1consulting/ddev-gander/commits)
[![release](https://img.shields.io/github/v/release/tag1consulting/ddev-gander)](https://github.com/tag1consulting/ddev-gander/releases/latest)

# ddev-gander <!-- omit in toc -->

* [What is gander?](#what-is-ddev-gander)
* [Prerequisites?](#prerequisites)
* [Getting started?](#getting-started)

## What is Gander?

[Gander](https://www.tag1consulting.com/gander) is a preconfigured Open Telemetry stack relying on Prometheus, Grafana, and Grafana Tempo.

For DDEV v1.23.5 or above run

```sh
ddev add-on get tag1consulting/ddev-gander
```

Then run Drupal core's OpenTelemetry phpunit tests, and immediately see performance metrics and traces in a Grafana dashboard. Or add PerformanceTestBase coverage to an existing project with a few lines of code if you already have phpunit functional test coverage of your project.

For more information on the phpunit side of things, see [the Drupal core change record](https://www.drupal.org/node/3366904).

## Prerequisites:
* [Install ddev](https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/) if you haven't already.
* Enable ddev on your local Drupal project.
* `ddev addon-get get ddev/ddev-selenium-standalone-chrome` to enable functional Javascript tests for DDEV. (`ddev/ddev-selenium-standalone-chrome` is a dependency of this add-on.)

## Getting started
For more information and a quickstart guide, [check the documentation on Drupal.org](https://www.drupal.org/docs/develop/automated-testing/performance-tests).
=======
Add Gander and run Drupal's performance tests via a git clone of Drupal core (assuming [composer is 
used](https://www.drupal.org/docs/develop/using-composer/manage-dependencies)):
* `ddev add-on get tag1consulting/ddev-gander`
* `ddev restart`
* `ddev ssh`
* `cd web/`
* To run a single test: `phpunit -c core profiles/demo_umami/tests/src/FunctionalJavascript/OpenTelemetryNodePagePerformanceTest.php`
* To run all Gander tests: `phpunit -c core --group OpenTelemetry`
* Check the Grafana dashboard via: _http://\<projectname\>.ddev.site:3000/_
