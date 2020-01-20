# `docker logs`

Fetch the logs of a container.

The docker logs command batch-retrieves logs present at the time of execution.

> Note: this command is only functional for containers that are started with the json-file or journald logging driver.

The `docker logs --follow` command will continue streaming the new output from the container’s STDOUT and STDERR.

The `--since` option shows only the container logs generated after a given date. Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)

The `--until` show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)

Examples

Retrieve logs until a specific point in time.

In order to retrieve logs before a specific point in time, run:

```
$ docker run -d alpine sh -c 'while true; do $(echo date); sleep 1; done'

$ docker logs <container-id> -f --until=2s

Sat Jan 11 17:20:45 UTC 2020
Sat Jan 11 17:20:46 UTC 2020
Sat Jan 11 17:20:47 UTC 2020
```
