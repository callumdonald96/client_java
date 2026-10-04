# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-04T09:46:00Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 9V74 80-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 681.40M | ± 2001.38K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 371.07M | ± 212.95K | ops/s |
| prometheusLabelValuesInc | 142.14M | ± 672.39K | ops/s |
| prometheusLabelValuesIncSingleThread | 68.38M | ± 312.95K | ops/s |
| prometheusInc | 76.99K | ± 625.40 | ops/s |
| prometheusNoLabelsInc | 66.73K | ± 999.54 | ops/s |
| prometheusAdd | 62.32K | ± 118.19 | ops/s |
| codahaleIncNoLabels | 56.81K | ± 2.84K | ops/s |
| openTelemetryBoundInc | 45.04K | ± 569.54 | ops/s |
| openTelemetryBoundAdd | 38.88K | ± 924.83 | ops/s |
| openTelemetryIncNoLabels | 26.77K | ± 108.31 | ops/s |
| openTelemetryInc | 21.31K | ± 221.96 | ops/s |
| openTelemetryAdd | 18.97K | ± 117.34 | ops/s |
| simpleclientAdd | 7.88K | ± 36.90 | ops/s |
| simpleclientInc | 7.86K | ± 9.00 | ops/s |
| simpleclientNoLabelsInc | 7.54K | ± 70.92 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 17.46K | ± 69.35 | ops/s |
| prometheusClassic | 9.26K | ± 922.80 | ops/s |
| openTelemetryBoundClassic | 8.02K | ± 1.95K | ops/s |
| prometheusClassicSingleThread | 7.23K | ± 23.50 | ops/s |
| openTelemetryClassic | 6.05K | ± 929.41 | ops/s |
| simpleclient | 5.82K | ± 36.47 | ops/s |
| prometheusNative | 3.90K | ± 46.03 | ops/s |
| openTelemetryBoundExponential | 989.34 | ± 16.76 | ops/s |
| openTelemetryExponential | 847.76 | ± 22.69 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| openMetricsWriteToNull | 35.38K | ± 99.79 | ops/s |
| prometheusWriteToNull | 35.34K | ± 401.16 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 793.22K | ± 6.87K | ops/s |
| prometheusWriteToByteArray | 789.46K | ± 6.47K | ops/s |
| openMetricsWriteToNull | 744.25K | ± 3.20K | ops/s |
| openMetricsWriteToByteArray | 727.20K | ± 7.22K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.016 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.049 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.024 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.021 | — | — |
| CounterBenchmark.openTelemetryInc | 0.044 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.035 | — | — |
| CounterBenchmark.prometheusAdd | 0.059 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.048 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.055 | — | — |
| CounterBenchmark.simpleclientAdd | 0.118 | — | — |
| CounterBenchmark.simpleclientInc | 0.119 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.123 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.123 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 0.948 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.157 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.106 | — | — |
| HistogramBenchmark.prometheusClassic | 0.402 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.464 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.403 | — | — |
| HistogramBenchmark.prometheusNative | 417705.980 | — | — |
| HistogramBenchmark.simpleclient | 0.161 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.099 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.099 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      56810.792   ± 2843.621  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      18967.027    ± 117.338  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      38879.922    ± 924.831  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      45041.672    ± 569.538  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      21310.452    ± 221.955  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      26771.362    ± 108.313  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      62316.904    ± 118.188  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  681402663.302 ± 2001380.406  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  371067910.056 ± 212945.113  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      76990.415    ± 625.397  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  142137314.998 ± 672389.472  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   68382405.396 ± 312954.814  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      66730.184    ± 999.539  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       7876.424     ± 36.900  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       7859.021      ± 9.003  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       7535.172     ± 70.919  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       8019.398   ± 1954.701  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        989.339     ± 16.757  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       6049.864    ± 929.409  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        847.759     ± 22.690  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15       9263.683    ± 922.801  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      17460.618     ± 69.348  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       7226.814     ± 23.498  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3904.423     ± 46.032  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       5819.331     ± 36.468  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      35383.660     ± 99.789  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      35342.028    ± 401.161  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     727197.543   ± 7221.956  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     744253.511   ± 3198.147  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     789459.260   ± 6465.674  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     793223.748   ± 6868.125  ops/s
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
