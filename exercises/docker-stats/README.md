# `docker stats` command

When running containers in production, it's important to monitor there runtime metrics, such as CPU usage and memory, to ensure they're behaving as expected. These metrics can also help diagnose issues if they occur.

In this scenario, we'll explore the built-in metrics provided by Docker to give additional visibility to the running containers. In future, we'll investigate more details about running Docker in production.

## Single Container

In your environment run a container with the name `mad_bear` that will simulate a memory consumption of 512 MB during a period of 20 seconds.

This can be done easily with the image `polinux/stress` which contains the well-known Linux workload simulator.

```
$ docker run --rm --name mad_bear polinux/stress stress --cpu 1 --io 1 --vm 1 --vm-bytes 512M --timeout 20s
```

You can find the stats for the container by using:

```
$ docker stats mad_bear

CONTAINER ID        NAME                CPU %               MEM USAGE / LIMIT     MEM % NET I/O             BLOCK I/O           PIDS
d0db5af92727        mad_bear            180.65%             427.8MiB / 1.952GiB   21.40% 758B / 0B          0B / 344kB          4
```

This launches a terminal window which refreshes itself with live data from the container.

To quit, use CTRL+C to stop the running progress.

## Multiple Containers

You can get an overview of the entire machine's containers too.

To view the stats for all your containers you can run:

```
$ docker stats

CONTAINER ID        NAME                CPU %               MEM USAGE / LIMIT     MEM %               NET I/O             BLOCK I/O           PIDS
30b03aec546a        nginx               99.42%              7.453MiB / 737.6MiB   1.01%               3.88kB / 484B       0B / 8.19kB         23
89b94784c9f7        nostalgic_leavitt   0.00%               1.074MiB / 737.6MiB   0.15%               6.72kB / 90B        0B / 0B             3
c5d3fa3bd96b        epic_mendeleev      0.00%               1.07MiB / 737.6MiB    0.15%               7.06kB / 176B       0B / 0B             3
```

To quit, use CTRL+C to stop the running progress.
