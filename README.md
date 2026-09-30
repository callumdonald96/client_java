# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-09-30T09:59:54Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 9V74 80-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 657.91M | ± 28782.26K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 348.33M | ± 2139.64K | ops/s |
| prometheusLabelValuesInc | 132.12M | ± 5049.51K | ops/s |
| prometheusLabelValuesIncSingleThread | 66.11M | ± 2534.79K | ops/s |
| prometheusInc | 74.74K | ± 982.33 | ops/s |
| prometheusNoLabelsInc | 65.09K | ± 581.31 | ops/s |
| prometheusAdd | 61.75K | ± 477.46 | ops/s |
| codahaleIncNoLabels | 55.38K | ± 1.08K | ops/s |
| openTelemetryBoundInc | 44.71K | ± 182.25 | ops/s |
| openTelemetryBoundAdd | 38.25K | ± 190.67 | ops/s |
| openTelemetryIncNoLabels | 26.22K | ± 663.20 | ops/s |
| openTelemetryInc | 21.32K | ± 279.42 | ops/s |
| openTelemetryAdd | 18.75K | ± 145.71 | ops/s |
| simpleclientInc | 7.90K | ± 75.82 | ops/s |
| simpleclientAdd | 7.36K | ± 493.91 | ops/s |
| simpleclientNoLabelsInc | 7.18K | ± 289.52 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 17.52K | ± 125.18 | ops/s |
| prometheusClassic | 9.01K | ± 821.12 | ops/s |
| prometheusClassicSingleThread | 7.23K | ± 9.15 | ops/s |
| openTelemetryBoundClassic | 6.97K | ± 381.93 | ops/s |
| simpleclient | 5.94K | ± 102.17 | ops/s |
| openTelemetryClassic | 5.44K | ± 457.90 | ops/s |
| prometheusNative | 3.73K | ± 365.45 | ops/s |
| openTelemetryBoundExponential | 912.30 | ± 67.51 | ops/s |
| openTelemetryExponential | 857.72 | ± 114.66 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 35.32K | ± 109.68 | ops/s |
| openMetricsWriteToNull | 35.02K | ± 311.46 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 779.98K | ± 5.08K | ops/s |
| prometheusWriteToByteArray | 761.89K | ± 10.90K | ops/s |
| openMetricsWriteToNull | 668.99K | ± 51.85K | ops/s |
| openMetricsWriteToByteArray | 623.15K | ± 21.20K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.017 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.050 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.024 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.021 | — | — |
| CounterBenchmark.openTelemetryInc | 0.044 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.036 | — | — |
| CounterBenchmark.prometheusAdd | 0.060 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.049 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.057 | — | — |
| CounterBenchmark.simpleclientAdd | 0.127 | — | — |
| CounterBenchmark.simpleclientInc | 0.119 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.130 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.135 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.032 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.176 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.104 | — | — |
| HistogramBenchmark.prometheusClassic | 0.414 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.461 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.403 | — | — |
| HistogramBenchmark.prometheusNative | 335793.014 | — | — |
| HistogramBenchmark.simpleclient | 0.158 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.100 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.099 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      55380.333   ± 1078.204  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      18752.666    ± 145.712  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      38250.495    ± 190.668  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      44707.211    ± 182.251  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      21324.570    ± 279.424  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      26221.319    ± 663.199  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      61746.555    ± 477.461  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  657909102.478 ± 28782259.352  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  348328594.634 ± 2139639.316  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      74735.569    ± 982.334  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  132115171.908 ± 5049513.841  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   66112185.431 ± 2534791.943  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      65090.585    ± 581.311  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       7360.462    ± 493.907  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       7898.074     ± 75.821  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       7178.437    ± 289.516  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       6970.054    ± 381.928  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        912.299     ± 67.514  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       5436.186    ± 457.904  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        857.724    ± 114.662  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       9010.474    ± 821.124  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      17518.819    ± 125.184  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       7229.014      ± 9.146  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3725.613    ± 365.448  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       5939.300    ± 102.168  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      35018.727    ± 311.461  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      35321.744    ± 109.683  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     623146.075  ± 21198.976  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     668992.528  ± 51851.123  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     761892.627  ± 10903.144  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     779983.581   ± 5077.240  ops/s
```

## Notes

- **Score** = the JMH primary metric; throughput is higher-is-better and latency is lower-is-better.
- **Error** = 99.9% confidence interval
- Scores for different benchmark methods are not ranked against one another; they may measure different workloads.

## Benchmark Descriptions

| Benchmark | Description |
|:----------|:------------|
| **CounterBenchmark** | Counter updates and label-value lookup (selected methods only) |
| **HistogramBenchmark** | Histogram observation performance (classic vs native/exponential) |
| **TextFormatUtilBenchmark** | Metric exposition format writing speed |
