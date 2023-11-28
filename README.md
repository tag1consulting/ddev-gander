[![tests](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml/badge.svg)](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2024.svg)

# ddev-gander <!-- omit in toc -->

* [What is gander?](#what-is-ddev-gander)
* [Getting started?](#getting-started)

## What is Gander?

Gander is a preconfigured Open Telemetry stack relying on Prometheus, Grafana, and Grafana Tempo.

`ddev add tag1consulting/ddev-gander`, run Drupal core's OpenTelemetry phpunit tests, and immediately see performance metrics and traces in a Grafana dashboard. Or add PerformanceTestBase coverage to an existing project with a few lines of code if you already have phpunit functional test coverage of your project.

For more information on the phpunit side of things, see [the Drupal core change record](https://www.drupal.org/node/3366904).

## Getting started

Prerequisites:
* [Install ddev](https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/) if you haven't already.
* Enable ddev on your local Drupal project.
* Ensure you can already run functional JavaScript tests in the ddev environment.

Add Gander and run Drupal's performance tests via a git clone of Drupal core:
* ddev add tag1consulting/ddev-gander
* ddev restart
* ddev ssh
* To run a single test three times in order to check the Gander installation, ensure you're in the document root first: `for run in 1..3; do vendor/bin/phpunit -c core/phpunit.xml profiles/demo_umami/tests/src/FunctionalJavascript/OpenTelemetryNodePagePerformanceTest.php --filter hot; done;`
* To run all OpenTelemetry tests: `vendor/bin/phpunit -c core/phpunit.xml --group OpenTelemetry`
* Check the Grafana dashboard via: http://localhost:3000/
