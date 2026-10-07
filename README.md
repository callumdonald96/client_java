# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-07T10:09:26Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 286.58M | ± 515.17K | ops/s |
| prometheusLabelValuesInc | 94.09M | ± 1318.35K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 93.24M | ± 87.65K | ops/s |
| prometheusLabelValuesIncSingleThread | 58.61M | ± 943.71K | ops/s |
| prometheusInc | 31.17K | ± 503.33 | ops/s |
| prometheusNoLabelsInc | 29.79K | ± 1.28K | ops/s |
| openTelemetryBoundInc | 29.14K | ± 54.55 | ops/s |
| codahaleIncNoLabels | 29.10K | ± 251.03 | ops/s |
| openTelemetryBoundAdd | 27.59K | ± 180.14 | ops/s |
| prometheusAdd | 27.59K | ± 1.22K | ops/s |
| openTelemetryIncNoLabels | 22.54K | ± 54.14 | ops/s |
| openTelemetryInc | 17.24K | ± 58.63 | ops/s |
| openTelemetryAdd | 15.19K | ± 161.48 | ops/s |
| simpleclientInc | 6.73K | ± 166.06 | ops/s |
| simpleclientNoLabelsInc | 6.57K | ± 268.74 | ops/s |
| simpleclientAdd | 6.55K | ± 184.01 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 7.89K | ± 27.47 | ops/s |
| simpleclient | 4.48K | ± 23.69 | ops/s |
| prometheusClassic | 3.69K | ± 384.36 | ops/s |
| prometheusClassicSingleThread | 3.23K | ± 74.92 | ops/s |
| openTelemetryBoundClassic | 3.22K | ± 1.25K | ops/s |
| openTelemetryClassic | 2.69K | ± 123.66 | ops/s |
| prometheusNative | 1.97K | ± 136.47 | ops/s |
| openTelemetryBoundExponential | 656.53 | ± 107.40 | ops/s |
| openTelemetryExponential | 518.42 | ± 42.47 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 18.18K | ± 179.92 | ops/s |
| openMetricsWriteToNull | 18.12K | ± 143.97 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 332.77K | ± 4.38K | ops/s |
| prometheusWriteToByteArray | 328.76K | ± 2.95K | ops/s |
| openMetricsWriteToNull | 308.66K | ± 2.01K | ops/s |
| openMetricsWriteToByteArray | 306.50K | ± 1.65K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.032 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.061 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.034 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.032 | — | — |
| CounterBenchmark.openTelemetryInc | 0.054 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.042 | — | — |
| CounterBenchmark.prometheusAdd | 0.134 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.118 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.124 | — | — |
| CounterBenchmark.simpleclientAdd | 0.142 | — | — |
| CounterBenchmark.simpleclientInc | 0.138 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.142 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.312 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.452 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.348 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.817 | — | — |
| HistogramBenchmark.prometheusClassic | 1.006 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 1.020 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.872 | — | — |
| HistogramBenchmark.prometheusNative | 417713.924 | — | — |
| HistogramBenchmark.simpleclient | 0.211 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.193 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43658.859 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.002 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18461.336 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18466.669 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.002 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      29097.886    ± 251.033  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15187.853    ± 161.483  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      27591.891    ± 180.145  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      29142.192     ± 54.548  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      17243.021     ± 58.626  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      22540.180     ± 54.138  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      27590.714   ± 1223.732  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  286576485.552 ± 515166.286  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15   93244427.987  ± 87651.593  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      31171.328    ± 503.328  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15   94094878.097 ± 1318348.989  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   58608936.876 ± 943708.966  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      29793.842   ± 1275.751  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6548.795    ± 184.011  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6725.379    ± 166.059  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6569.842    ± 268.744  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       3220.408   ± 1254.963  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        656.534    ± 107.405  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       2688.769    ± 123.662  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        518.422     ± 42.474  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       3688.312    ± 384.361  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15       7885.634     ± 27.474  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       3231.331     ± 74.922  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       1966.061    ± 136.467  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4476.209     ± 23.685  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      18121.668    ± 143.971  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      18177.184    ± 179.915  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     306495.781   ± 1649.289  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     308660.707   ± 2010.064  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     328756.582   ± 2945.615  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     332774.419   ± 4382.945  ops/s
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
