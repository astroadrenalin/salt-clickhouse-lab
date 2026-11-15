# Salt ClickHouse Lab

A hands-on lab for learning Salt, ClickHouse, SQL, Kafka, and Git.

## Goal

Build a small request-reporting system, starting with one Salt-managed
ClickHouse instance and expanding it gradually.

Use fictional web-request records to answer questions such as:
- How many requests did each website receive?
- How many requests failed?
- How many bytes were sent?

## Starting infrastructure

Both servers run Debian 12 Bookworm on x86_64 and have private networking enabled.

| Server | Resources | Purpose |
|---|---|---|
| lab-salt-01 | 2 vCPU, 2 GB RAM | Salt master |
| lab-data-01 | 4 vCPU, 8 GB RAM | Salt minion and ClickHouse |

Private connectivity still needs to be verified.
Salt, Docker, ClickHouse, and Kafka have not yet been installed.

## Learning stages

1. Connect a Salt master and minion.
2. Use Salt to manage one ClickHouse container with persistent storage.
3. Create a table, insert fictional requests, and learn basic SQL queries.
4. Introduce pillar and Jinja templates to separate settings from states.
5. Add Kafka and learn to publish and consume events.
6. Connect Kafka to ClickHouse and build reporting summaries.
7. Practice troubleshooting, then explore replication and sharding.

## Working practices

- Make small changes on task-specific branches.
- Inspect changes and verify behavior before committing.
- Use Conventional Commit messages: `type(scope): description`.
- Review changes through GitHub pull requests before merging.
- Use synthetic or public sample data.

## First milestone

Use Salt to start one ClickHouse instance.
Verify that it responds, retains its data across a container restart,
and that a second Salt application makes no unnecessary changes.