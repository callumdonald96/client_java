# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-09-29T09:53:24Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 7763 64-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 557.06M | ± 5057.43K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 334.93M | ± 293.07K | ops/s |
| prometheusLabelValuesInc | 116.44M | ± 1257.67K | ops/s |
| prometheusLabelValuesIncSingleThread | 58.80M | ± 224.18K | ops/s |
| prometheusInc | 65.86K | ± 126.10 | ops/s |
| prometheusNoLabelsInc | 56.76K | ± 275.45 | ops/s |
| prometheusAdd | 50.96K | ± 532.50 | ops/s |
| codahaleIncNoLabels | 49.81K | ± 651.91 | ops/s |
| openTelemetryBoundInc | 37.90K | ± 145.09 | ops/s |
| openTelemetryBoundAdd | 31.60K | ± 569.23 | ops/s |
| openTelemetryIncNoLabels | 20.86K | ± 1.91K | ops/s |
| openTelemetryInc | 18.11K | ± 94.21 | ops/s |
| openTelemetryAdd | 15.54K | ± 86.11 | ops/s |
| simpleclientInc | 6.56K | ± 38.76 | ops/s |
| simpleclientNoLabelsInc | 6.34K | ± 14.58 | ops/s |
| simpleclientAdd | 6.30K | ± 456.90 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 12.09K | ± 41.88 | ops/s |
| openTelemetryBoundClassic | 6.98K | ± 1.78K | ops/s |
| openTelemetryClassic | 5.27K | ± 878.53 | ops/s |
| prometheusClassic | 4.94K | ± 1.76K | ops/s |
| prometheusClassicSingleThread | 4.53K | ± 17.10 | ops/s |
| simpleclient | 4.42K | ± 11.83 | ops/s |
| prometheusNative | 3.15K | ± 63.57 | ops/s |
| openTelemetryBoundExponential | 1.16K | ± 18.80 | ops/s |
| openTelemetryExponential | 794.39 | ± 76.00 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| openMetricsWriteToNull | 24.11K | ± 819.41 | ops/s |
| prometheusWriteToNull | 23.81K | ± 729.56 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 568.26K | ± 4.00K | ops/s |
| prometheusWriteToByteArray | 555.07K | ± 3.88K | ops/s |
| openMetricsWriteToNull | 534.46K | ± 2.20K | ops/s |
| openMetricsWriteToByteArray | 521.13K | ± 3.17K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.019 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.060 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.029 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.024 | — | — |
| CounterBenchmark.openTelemetryInc | 0.051 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.045 | — | — |
| CounterBenchmark.prometheusAdd | 0.072 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.056 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.065 | — | — |
| CounterBenchmark.simpleclientAdd | 0.148 | — | — |
| CounterBenchmark.simpleclientInc | 0.141 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.146 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.142 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 0.802 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.182 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.171 | — | — |
| HistogramBenchmark.prometheusClassic | 0.803 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.660 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.642 | — | — |
| HistogramBenchmark.prometheusNative | 253875.705 | — | — |
| HistogramBenchmark.simpleclient | 0.212 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.145 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.147 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18429.335 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      49808.897    ± 651.914  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15540.280     ± 86.110  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      31596.766    ± 569.230  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      37904.550    ± 145.088  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      18108.370     ± 94.209  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      20855.129   ± 1909.346  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      50956.892    ± 532.495  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  557055388.748 ± 5057434.734  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  334932345.606 ± 293073.669  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      65855.127    ± 126.096  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  116436486.687 ± 1257671.503  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   58797242.405 ± 224180.240  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      56764.787    ± 275.453  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6295.828    ± 456.899  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6560.824     ± 38.763  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6343.729     ± 14.582  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       6977.518   ± 1781.559  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15       1157.339     ± 18.797  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       5265.762    ± 878.526  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        794.394     ± 75.998  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       4941.076   ± 1761.895  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      12094.052     ± 41.878  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       4534.931     ± 17.096  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3146.198     ± 63.572  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4420.625     ± 11.826  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      24107.625    ± 819.410  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      23807.308    ± 729.560  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     521128.423   ± 3169.736  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     534459.289   ± 2198.356  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     555067.729   ± 3880.151  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     568256.910   ± 3998.060  ops/s
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
