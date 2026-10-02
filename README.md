# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-02T09:56:10Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 286.74M | ± 10452.60K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 93.32M | ± 57.02K | ops/s |
| prometheusLabelValuesInc | 92.50M | ± 1140.72K | ops/s |
| prometheusLabelValuesIncSingleThread | 59.92M | ± 1094.70K | ops/s |
| prometheusInc | 31.53K | ± 24.36 | ops/s |
| prometheusNoLabelsInc | 31.52K | ± 16.29 | ops/s |
| openTelemetryBoundInc | 29.18K | ± 67.10 | ops/s |
| codahaleIncNoLabels | 28.94K | ± 625.43 | ops/s |
| prometheusAdd | 27.76K | ± 896.10 | ops/s |
| openTelemetryBoundAdd | 27.04K | ± 1.10K | ops/s |
| openTelemetryIncNoLabels | 22.90K | ± 552.55 | ops/s |
| openTelemetryInc | 17.03K | ± 139.99 | ops/s |
| openTelemetryAdd | 15.33K | ± 52.14 | ops/s |
| simpleclientInc | 6.87K | ± 40.95 | ops/s |
| simpleclientAdd | 6.65K | ± 56.90 | ops/s |
| simpleclientNoLabelsInc | 6.40K | ± 178.15 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 7.91K | ± 28.91 | ops/s |
| prometheusClassic | 4.78K | ± 1.66K | ops/s |
| simpleclient | 4.40K | ± 139.77 | ops/s |
| openTelemetryBoundClassic | 3.88K | ± 1.34K | ops/s |
| prometheusClassicSingleThread | 3.23K | ± 74.68 | ops/s |
| openTelemetryClassic | 2.86K | ± 334.07 | ops/s |
| prometheusNative | 1.95K | ± 49.19 | ops/s |
| openTelemetryBoundExponential | 691.48 | ± 55.84 | ops/s |
| openTelemetryExponential | 550.84 | ± 67.68 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 18.28K | ± 92.63 | ops/s |
| openMetricsWriteToNull | 18.05K | ± 140.01 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 340.33K | ± 2.04K | ops/s |
| prometheusWriteToByteArray | 338.51K | ± 1.92K | ops/s |
| openMetricsWriteToNull | 317.19K | ± 1.92K | ops/s |
| openMetricsWriteToByteArray | 314.08K | ± 1.79K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.032 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.061 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.034 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.032 | — | — |
| CounterBenchmark.openTelemetryInc | 0.055 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.041 | — | — |
| CounterBenchmark.prometheusAdd | 0.133 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.117 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.117 | — | — |
| CounterBenchmark.simpleclientAdd | 0.140 | — | — |
| CounterBenchmark.simpleclientInc | 0.135 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.145 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.261 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.355 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.329 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.712 | — | — |
| HistogramBenchmark.prometheusClassic | 0.844 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 1.028 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.856 | — | — |
| HistogramBenchmark.prometheusNative | 417713.914 | — | — |
| HistogramBenchmark.simpleclient | 0.212 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.194 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.191 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.002 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.002 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18429.335 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18466.669 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      28941.267    ± 625.427  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15328.875     ± 52.138  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      27042.836   ± 1100.009  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      29182.269     ± 67.099  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      17028.539    ± 139.990  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      22900.597    ± 552.546  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      27758.819    ± 896.102  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  286736386.013 ± 10452602.441  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15   93317423.483  ± 57016.551  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      31525.608     ± 24.357  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15   92501052.620 ± 1140721.566  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   59918669.840 ± 1094698.285  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      31515.111     ± 16.287  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6646.400     ± 56.900  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6869.751     ± 40.946  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6395.866    ± 178.151  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       3881.051   ± 1338.089  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        691.483     ± 55.845  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       2855.601    ± 334.066  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        550.843     ± 67.677  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       4784.451   ± 1664.110  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15       7909.273     ± 28.907  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       3233.440     ± 74.685  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       1950.505     ± 49.190  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4396.193    ± 139.769  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      18051.962    ± 140.007  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      18281.672     ± 92.630  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     314082.844   ± 1786.250  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     317192.771   ± 1924.991  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     338505.533   ± 1919.211  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     340328.633   ± 2044.076  ops/s
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
