# StatsD Server

A fault-tolerant and concurrent StatsD server that follows the [specification](https://github.com/etsy/statsd/blob/master/docs/metric_types.md)

![Supervision Tree](https://raw.githubusercontent.com/joshnuss/elixir-statsd/master/supervision-tree.jpg)

## Installation

```
mix escript.install github joshnuss/elixir-statsd
```

## Running

To run on port 2052

```
./statsd 2052
```

### Running on multiple ports

```
./statsd 2052 2053
```

## Testing


Send a single metric:

```
echo "requests:99|c" | nc -u -w0 127.0.0.1 2052
```

Send multiple metrics in one packet:

```
echo -e "withdrawal:2\ndeposit:3\n" | nc -u -w0 127.0.0.1 2052
```
