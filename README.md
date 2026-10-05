# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-05T10:22:13Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 291.33M | ± 6409.71K | ops/s |
| prometheusLabelValuesInc | 93.54M | ± 198.33K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 93.40M | ± 58.02K | ops/s |
| prometheusLabelValuesIncSingleThread | 57.22M | ± 365.83K | ops/s |
| prometheusInc | 30.78K | ± 1.45K | ops/s |
| prometheusNoLabelsInc | 29.36K | ± 177.05 | ops/s |
| openTelemetryBoundInc | 29.08K | ± 290.00 | ops/s |
| codahaleIncNoLabels | 28.84K | ± 601.28 | ops/s |
| openTelemetryBoundAdd | 27.95K | ± 105.71 | ops/s |
| prometheusAdd | 27.25K | ± 1.21K | ops/s |
| openTelemetryIncNoLabels | 22.77K | ± 731.91 | ops/s |
| openTelemetryInc | 16.73K | ± 961.52 | ops/s |
| openTelemetryAdd | 15.11K | ± 331.16 | ops/s |
| simpleclientInc | 6.89K | ± 98.70 | ops/s |
| simpleclientAdd | 6.62K | ± 176.64 | ops/s |
| simpleclientNoLabelsInc | 6.31K | ± 149.04 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 7.89K | ± 45.57 | ops/s |
| openTelemetryBoundClassic | 5.20K | ± 2.29K | ops/s |
| simpleclient | 4.43K | ± 90.36 | ops/s |
| prometheusClassic | 4.41K | ± 1.85K | ops/s |
| prometheusClassicSingleThread | 3.24K | ± 80.27 | ops/s |
| openTelemetryClassic | 2.81K | ± 225.04 | ops/s |
| prometheusNative | 2.13K | ± 117.46 | ops/s |
| openTelemetryBoundExponential | 601.29 | ± 98.14 | ops/s |
| openTelemetryExponential | 474.73 | ± 37.69 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 17.99K | ± 78.90 | ops/s |
| openMetricsWriteToNull | 17.92K | ± 102.91 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 280.78K | ± 3.86K | ops/s |
| prometheusWriteToByteArray | 276.31K | ± 1.36K | ops/s |
| openMetricsWriteToNull | 261.71K | ± 1.05K | ops/s |
| openMetricsWriteToByteArray | 259.31K | ± 1.72K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.032 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.062 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.033 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.032 | — | — |
| CounterBenchmark.openTelemetryInc | 0.056 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.041 | — | — |
| CounterBenchmark.prometheusAdd | 0.136 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.121 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.126 | — | — |
| CounterBenchmark.simpleclientAdd | 0.141 | — | — |
| CounterBenchmark.simpleclientInc | 0.136 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.149 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.215 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.593 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.338 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.984 | — | — |
| HistogramBenchmark.prometheusClassic | 0.939 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 1.031 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.866 | — | — |
| HistogramBenchmark.prometheusNative | 335793.760 | — | — |
| HistogramBenchmark.simpleclient | 0.214 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.195 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.195 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.003 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.003 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18466.669 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18410.669 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      28838.980    ± 601.275  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      15111.268    ± 331.164  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      27952.591    ± 105.713  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      29082.854    ± 290.000  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      16726.121    ± 961.518  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      22773.534    ± 731.907  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      27252.030   ± 1214.131  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  291332924.522 ± 6409711.286  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15   93400290.951  ± 58017.212  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      30779.523   ± 1448.788  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15   93541169.132 ± 198329.527  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   57215463.887 ± 365830.400  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      29355.169    ± 177.046  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       6622.506    ± 176.638  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       6890.005     ± 98.698  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       6309.367    ± 149.043  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       5196.576   ± 2288.823  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        601.293     ± 98.143  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       2811.218    ± 225.040  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        474.726     ± 37.688  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       4407.758   ± 1850.332  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15       7889.187     ± 45.572  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       3235.841     ± 80.272  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       2129.179    ± 117.459  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       4432.080     ± 90.355  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      17917.280    ± 102.914  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      17986.874     ± 78.901  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     259307.462   ± 1719.848  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     261710.387   ± 1052.019  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     276308.903   ± 1362.615  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     280780.404   ± 3862.420  ops/s
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
