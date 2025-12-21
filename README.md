[![tests](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml/badge.svg)](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2024.svg)

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

For earlier versions of DDEV run

```sh
ddev get tag1consulting/ddev-gander
```

Then run Drupal core's OpenTelemetry phpunit tests, and immediately see performance metrics and traces in a Grafana dashboard. Or add PerformanceTestBase coverage to an existing project with a few lines of code if you already have phpunit functional test coverage of your project.

For more information on the phpunit side of things, see [the Drupal core change record](https://www.drupal.org/node/3366904).

## Prerequisites:
* [Install ddev](https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/) if you haven't already.
* Enable ddev on your local Drupal project.
* `composer require --dev drupal/core-dev` to install phpunit if isn't already
* `ddev get ddev/ddev-selenium-standalone-chrome` to enable functional Javascript tests for DDEV. (`ddev/ddev-selenium-standalone-chrome` is a dependency of this add-on.)


## Getting started
For more information and a quickstart guide, [check the documentation on Drupal.org](https://www.drupal.org/docs/develop/automated-testing/performance-tests).
=======
Add Gander and run Drupal's performance tests via a git clone of Drupal core (assuming [composer is 
used](https://www.drupal.org/docs/develop/using-composer/manage-dependencies)):
* `ddev get tag1consulting/ddev-gander`
* `ddev restart`
* `ddev ssh`
* `cd web/`
* To run a single test: `phpunit -c core core/profiles/demo_umami/tests/src/FunctionalJavascript/OpenTelemetryNodePagePerformanceTest.php`
* To run all Gander tests: `phpunit -c core --group OpenTelemetry`
* Check the Grafana dashboard via: _http://\<projectname\>.ddev.site:3000/_ (Note: Use http not https)
