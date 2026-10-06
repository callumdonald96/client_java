# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-06T10:34:27Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 7763 64-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 555.33M | ± 8333.62K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 334.75M | ± 320.69K | ops/s |
| prometheusLabelValuesInc | 116.53M | ± 512.30K | ops/s |
| prometheusLabelValuesIncSingleThread | 58.70M | ± 604.96K | ops/s |
| prometheusInc | 66.03K | ± 448.71 | ops/s |
| prometheusNoLabelsInc | 55.53K | ± 2.02K | ops/s |
| prometheusAdd | 51.51K | ± 142.83 | ops/s |
| codahaleIncNoLabels | 47.88K | ± 911.31 | ops/s |
| openTelemetryBoundInc | 38.10K | ± 348.03 | ops/s |
| openTelemetryBoundAdd | 31.53K | ± 438.41 | ops/s |
| openTelemetryIncNoLabels | 24.14K | ± 75.45 | ops/s |
| openTelemetryInc | 18.02K | ± 229.77 | ops/s |
| openTelemetryAdd | 15.51K | ± 75.52 | ops/s |
| simpleclientInc | 6.62K | ± 70.48 | ops/s |
| simpleclientNoLabelsInc | 6.45K | ± 99.15 | ops/s |
| simpleclientAdd | 6.44K | ± 45.68 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 12.07K | ± 42.56 | ops/s |
| openTelemetryBoundClassic | 6.21K | ± 1.95K | ops/s |
| prometheusClassic | 5.86K | ± 1.90K | ops/s |
| openTelemetryClassic | 4.92K | ± 654.17 | ops/s |
| prometheusClassicSingleThread | 4.54K | ± 23.22 | ops/s |
| simpleclient | 4.41K | ± 76.04 | ops/s |
| prometheusNative | 3.13K | ± 145.20 | ops/s |
| openTelemetryBoundExponential | 980.02 | ± 76.02 | ops/s |
| openTelemetryExponential | 863.78 | ± 5.47 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| openMetricsWriteToNull | 24.10K | ± 232.31 | ops/s |
| prometheusWriteToNull | 24.10K | ± 844.88 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 541.79K | ± 10.48K | ops/s |
| prometheusWriteToByteArray | 535.75K | ± 4.59K | ops/s |
| openMetricsWriteToByteArray | 522.28K | ± 6.70K | ops/s |
| openMetricsWriteToNull | 516.76K | ± 7.07K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.020 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.060 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.029 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.024 | — | — |
| CounterBenchmark.openTelemetryInc | 0.051 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.038 | — | — |
| CounterBenchmark.prometheusAdd | 0.071 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.056 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.066 | — | — |
| CounterBenchmark.simpleclientAdd | 0.144 | — | — |
| CounterBenchmark.simpleclientInc | 0.141 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.144 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.163 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 0.950 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.192 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.074 | — | — |
| HistogramBenchmark.prometheusClassic | 0.676 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.665 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.641 | — | — |
| HistogramBenchmark.prometheusNative | 417713.183 | — | — |
| HistogramBenchmark.simpleclient | 0.213 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.145 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.145 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      47878.832    ± 911.309  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15505.924     ± 75.518  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      31528.081    ± 438.410  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      38098.392    ± 348.026  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      18015.225    ± 229.766  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      24136.036     ± 75.450  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      51512.805    ± 142.825  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  555329416.571 ± 8333622.140  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  334750446.150 ± 320688.170  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      66030.256    ± 448.709  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  116529012.345 ± 512300.668  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   58696292.911 ± 604962.261  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      55528.473   ± 2019.980  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6444.713     ± 45.681  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6624.082     ± 70.484  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6449.711     ± 99.153  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       6213.826   ± 1954.914  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        980.020     ± 76.020  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       4922.564    ± 654.168  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        863.776      ± 5.467  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       5856.561   ± 1903.661  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      12072.316     ± 42.556  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       4538.142     ± 23.218  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3130.579    ± 145.204  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4410.735     ± 76.043  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      24103.669    ± 232.310  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      24099.742    ± 844.877  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     522281.812   ± 6703.505  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     516759.526   ± 7072.760  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     535745.232   ± 4585.336  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     541794.937  ± 10483.538  ops/s
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
