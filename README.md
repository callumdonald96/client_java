# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-03T09:35:33Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 9V74 80-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 659.12M | ± 34481.70K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 370.86M | ± 520.43K | ops/s |
| prometheusLabelValuesInc | 138.46M | ± 2697.61K | ops/s |
| prometheusLabelValuesIncSingleThread | 68.62M | ± 505.75K | ops/s |
| prometheusInc | 75.15K | ± 3.30K | ops/s |
| prometheusNoLabelsInc | 66.39K | ± 1.04K | ops/s |
| prometheusAdd | 62.18K | ± 1.44K | ops/s |
| codahaleIncNoLabels | 52.79K | ± 7.75K | ops/s |
| openTelemetryBoundInc | 45.06K | ± 436.45 | ops/s |
| openTelemetryBoundAdd | 39.18K | ± 548.06 | ops/s |
| openTelemetryIncNoLabels | 25.93K | ± 1.31K | ops/s |
| openTelemetryInc | 21.49K | ± 32.86 | ops/s |
| openTelemetryAdd | 18.61K | ± 380.42 | ops/s |
| simpleclientInc | 7.87K | ± 6.70 | ops/s |
| simpleclientAdd | 7.73K | ± 178.82 | ops/s |
| simpleclientNoLabelsInc | 7.64K | ± 24.93 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 17.40K | ± 198.03 | ops/s |
| prometheusClassic | 9.54K | ± 1.71K | ops/s |
| prometheusClassicSingleThread | 7.22K | ± 18.63 | ops/s |
| openTelemetryClassic | 6.83K | ± 1.30K | ops/s |
| openTelemetryBoundClassic | 6.58K | ± 1.41K | ops/s |
| simpleclient | 5.84K | ± 34.86 | ops/s |
| prometheusNative | 3.65K | ± 358.73 | ops/s |
| openTelemetryBoundExponential | 876.90 | ± 49.09 | ops/s |
| openTelemetryExponential | 829.52 | ± 49.87 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 35.72K | ± 133.12 | ops/s |
| openMetricsWriteToNull | 34.96K | ± 99.22 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 793.69K | ± 22.83K | ops/s |
| prometheusWriteToByteArray | 785.76K | ± 6.98K | ops/s |
| openMetricsWriteToNull | 748.25K | ± 7.81K | ops/s |
| openMetricsWriteToByteArray | 738.54K | ± 3.61K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.018 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.050 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.024 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.021 | — | — |
| CounterBenchmark.openTelemetryInc | 0.043 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.036 | — | — |
| CounterBenchmark.prometheusAdd | 0.059 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.049 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.055 | — | — |
| CounterBenchmark.simpleclientAdd | 0.121 | — | — |
| CounterBenchmark.simpleclientInc | 0.118 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.122 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.147 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.070 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.143 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.130 | — | — |
| HistogramBenchmark.prometheusClassic | 0.395 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.463 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.403 | — | — |
| HistogramBenchmark.prometheusNative | 417713.033 | — | — |
| HistogramBenchmark.simpleclient | 0.160 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.100 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.098 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      52788.822   ± 7752.680  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      18614.441    ± 380.417  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      39177.907    ± 548.062  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      45059.754    ± 436.451  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      21485.585     ± 32.862  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      25930.664   ± 1309.829  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      62184.564   ± 1444.332  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  659119644.228 ± 34481703.961  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  370855498.394 ± 520431.279  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      75150.254   ± 3302.072  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  138461862.785 ± 2697610.118  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   68615881.706 ± 505754.129  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      66386.192   ± 1044.006  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       7728.192    ± 178.820  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       7868.636      ± 6.700  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       7641.083     ± 24.926  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       6581.416   ± 1405.415  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        876.904     ± 49.090  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       6834.792   ± 1304.530  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        829.522     ± 49.865  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       9540.683   ± 1713.839  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      17395.352    ± 198.029  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       7217.624     ± 18.627  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3648.461    ± 358.733  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       5835.500     ± 34.862  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      34963.969     ± 99.218  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      35716.447    ± 133.119  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     738544.685   ± 3614.211  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     748247.519   ± 7805.559  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     785762.918   ± 6982.746  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     793690.214  ± 22827.465  ops/s
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
