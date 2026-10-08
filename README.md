# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-08T10:25:35Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 7763 64-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 549.80M | ± 5121.97K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 335.04M | ± 169.73K | ops/s |
| prometheusLabelValuesInc | 116.56M | ± 789.68K | ops/s |
| prometheusLabelValuesIncSingleThread | 58.50M | ± 139.68K | ops/s |
| prometheusInc | 64.48K | ± 1.97K | ops/s |
| prometheusNoLabelsInc | 56.85K | ± 337.67 | ops/s |
| prometheusAdd | 51.40K | ± 268.75 | ops/s |
| codahaleIncNoLabels | 39.76K | ± 13.29K | ops/s |
| openTelemetryBoundInc | 38.09K | ± 111.05 | ops/s |
| openTelemetryBoundAdd | 31.91K | ± 209.42 | ops/s |
| openTelemetryIncNoLabels | 22.63K | ± 1.24K | ops/s |
| openTelemetryInc | 18.01K | ± 343.76 | ops/s |
| openTelemetryAdd | 15.63K | ± 128.61 | ops/s |
| simpleclientInc | 6.62K | ± 62.00 | ops/s |
| simpleclientNoLabelsInc | 6.34K | ± 29.61 | ops/s |
| simpleclientAdd | 6.29K | ± 287.73 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 12.06K | ± 65.42 | ops/s |
| prometheusClassic | 6.64K | ± 524.10 | ops/s |
| openTelemetryBoundClassic | 5.39K | ± 1.51K | ops/s |
| prometheusClassicSingleThread | 4.54K | ± 17.52 | ops/s |
| openTelemetryClassic | 4.47K | ± 790.46 | ops/s |
| simpleclient | 4.37K | ± 22.58 | ops/s |
| prometheusNative | 3.13K | ± 90.50 | ops/s |
| openTelemetryBoundExponential | 1.10K | ± 34.16 | ops/s |
| openTelemetryExponential | 841.92 | ± 23.48 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| openMetricsWriteToNull | 23.89K | ± 364.66 | ops/s |
| prometheusWriteToNull | 23.27K | ± 178.91 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 553.64K | ± 12.73K | ops/s |
| prometheusWriteToByteArray | 552.51K | ± 5.02K | ops/s |
| openMetricsWriteToNull | 526.03K | ± 6.86K | ops/s |
| openMetricsWriteToByteArray | 521.94K | ± 4.45K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.026 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.059 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.029 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.024 | — | — |
| CounterBenchmark.openTelemetryInc | 0.051 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.041 | — | — |
| CounterBenchmark.prometheusAdd | 0.072 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.057 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.065 | — | — |
| CounterBenchmark.simpleclientAdd | 0.147 | — | — |
| CounterBenchmark.simpleclientInc | 0.140 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.146 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.187 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 0.849 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.213 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.101 | — | — |
| HistogramBenchmark.prometheusClassic | 0.556 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.666 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.641 | — | — |
| HistogramBenchmark.prometheusNative | 335793.190 | — | — |
| HistogramBenchmark.simpleclient | 0.214 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.146 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.150 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      39757.643  ± 13286.634  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15629.604    ± 128.610  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      31914.021    ± 209.416  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      38089.917    ± 111.048  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      18006.230    ± 343.759  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      22626.971   ± 1236.392  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      51400.354    ± 268.746  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  549798236.888 ± 5121971.381  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  335037234.293 ± 169730.061  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      64475.749   ± 1974.273  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  116559853.933 ± 789676.221  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   58496792.896 ± 139680.716  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      56850.561    ± 337.671  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6291.645    ± 287.730  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6620.258     ± 62.000  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6337.093     ± 29.607  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       5386.193   ± 1514.404  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15       1095.971     ± 34.161  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       4474.938    ± 790.460  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        841.917     ± 23.482  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       6635.957    ± 524.097  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      12057.829     ± 65.416  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       4543.822     ± 17.515  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3132.303     ± 90.497  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4365.657     ± 22.583  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      23892.043    ± 364.656  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      23271.358    ± 178.910  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     521942.288   ± 4445.862  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     526028.742   ± 6856.467  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     552514.827   ± 5019.741  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     553642.341  ± 12732.721  ops/s
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
