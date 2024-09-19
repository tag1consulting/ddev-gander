[![tests](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml/badge.svg)](https://github.com/tag1consulting/ddev-gander/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2024.svg)

# ddev-gander <!-- omit in toc -->

* [What is gander?](#what-is-ddev-gander)
* [Prerequisites?](#prerequisites)
* [Getting started?](#getting-started)

## What is Gander?

[Gander](https://www.tag1consulting.com/gander) is a preconfigured Open Telemetry stack relying on Prometheus, Grafana, and Grafana Tempo.

`ddev get tag1consulting/ddev-gander`, run Drupal core's OpenTelemetry phpunit tests, and immediately see performance metrics and traces in a Grafana dashboard. Or add PerformanceTestBase coverage to an existing project with a few lines of code if you already have phpunit functional test coverage of your project.

For more information on the phpunit side of things, see [the Drupal core change record](https://www.drupal.org/node/3366904).

## Getting started
For more information and a quickstart guide, [check the documentation on Drupal.org](https://www.drupal.org/docs/develop/automated-testing/performance-tests).
