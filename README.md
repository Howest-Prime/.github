# Howest Prime

Howest Prime is a cinema experience platform with an Android app, movie and ticketing services, and web clients. The services exchange events through an AMQP message broker. Terraform and Docker Compose configurations support production infrastructure and a local test environment.

## Architecture

- The **Android app** displays tickets, QR codes, and movie reminders; supports snack browsing and orders; and includes a cinema map and sensor features.
- The **Movies service** manages the movie catalog, rooms, showtimes, and booking capacity. It publishes movie and booking events and handles payment outcome events from Ticketing.
- The **Ticketing service** manages orders, customer details, payment outcomes, and ticket release. It exchanges booking and payment events with Movies through LavinMQ.
- The **web app and backoffice** are included in the infrastructure configuration and test environment.
- The **production infrastructure** is defined with Terraform for Azure resources, CloudAMQP messaging, and GitHub Actions configuration. A separate Docker Compose setup brings up the test services and dependencies.

## Repositories

| Repository | Description |
| --- | --- |
| [st-client-mobile](https://github.com/Howest-Prime/st-client-mobile) | Kotlin Android app for tickets, reminders, snacks, maps, and device sensors. |
| [st-microservice-movies](https://github.com/Howest-Prime/st-microservice-movies) | .NET service for the movie catalog, showtimes, and booking events. |
| [st-microservice-ticketing](https://github.com/Howest-Prime/st-microservice-ticketing) | Deno and TypeScript service for orders, payments, and ticket release. |
| [st-infrastructure-prod](https://github.com/Howest-Prime/st-infrastructure-prod) | Terraform definitions for production infrastructure. |
| [st-infrastructure-test](https://github.com/Howest-Prime/st-infrastructure-test) | Docker Compose test environment for services and dependencies. |

## Technology

Kotlin, Jetpack Compose, .NET 10, Deno, TypeScript, PostgreSQL, MongoDB API on Azure Cosmos DB, Entity Framework Core, AMQP/LavinMQ, Docker Compose, Terraform, and Microsoft Azure.
