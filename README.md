# Prometheus Java Client Benchmarks

## Run Information

- **Date:** 2026-10-01T10:19:16Z
- **Commit:** [`cce26b8`](https://github.com/callumdonald96/client_java/commit/cce26b87ccc0d8dbb83e8532ce7adba8f26c5372)
- **JDK:** 25.0.3 (OpenJDK 64-Bit Server VM)
- **Benchmark config:** 3 fork(s), 3 warmup, 5 measurement, 1/4 threads
- **Hardware:** AMD EPYC 9V74 80-Core Processor, 4 cores, 16 GB RAM
- **OS:** Linux 6.17.0-1022-azure

## Results for PR head

### CounterBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusCachedLabelValuesInc | 677.06M | ± 6935.57K | ops/s |
| prometheusCachedLabelValuesIncSingleThread | 370.91M | ± 428.11K | ops/s |
| prometheusLabelValuesInc | 138.69M | ± 2742.80K | ops/s |
| prometheusLabelValuesIncSingleThread | 68.70M | ± 542.17K | ops/s |
| prometheusInc | 76.96K | ± 600.05 | ops/s |
| prometheusNoLabelsInc | 66.51K | ± 589.37 | ops/s |
| prometheusAdd | 62.41K | ± 561.24 | ops/s |
| codahaleIncNoLabels | 57.02K | ± 354.59 | ops/s |
| openTelemetryBoundInc | 45.38K | ± 473.81 | ops/s |
| openTelemetryBoundAdd | 38.86K | ± 393.65 | ops/s |
| openTelemetryIncNoLabels | 27.73K | ± 606.21 | ops/s |
| openTelemetryInc | 21.58K | ± 17.29 | ops/s |
| openTelemetryAdd | 18.78K | ± 24.19 | ops/s |
| simpleclientInc | 8.00K | ± 125.96 | ops/s |
| simpleclientNoLabelsInc | 7.57K | ± 38.63 | ops/s |
| simpleclientAdd | 7.34K | ± 279.35 | ops/s |

### HistogramBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusClassicPerThread | 17.42K | ± 92.19 | ops/s |
| prometheusClassic | 10.50K | ± 2.57K | ops/s |
| prometheusClassicSingleThread | 6.93K | ± 357.79 | ops/s |
| openTelemetryBoundClassic | 6.91K | ± 1.96K | ops/s |
| simpleclient | 5.79K | ± 88.74 | ops/s |
| openTelemetryClassic | 5.40K | ± 415.62 | ops/s |
| prometheusNative | 3.52K | ± 307.99 | ops/s |
| openTelemetryBoundExponential | 922.61 | ± 45.20 | ops/s |
| openTelemetryExponential | 794.53 | ± 42.89 | ops/s |

### HistogramTextFormatBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| openMetricsWriteToNull | 35.57K | ± 251.91 | ops/s |
| prometheusWriteToNull | 35.19K | ± 145.05 | ops/s |

### TextFormatUtilBenchmark

| Benchmark | Score | Error | Units |
|:----------|------:|------:|:------|
| prometheusWriteToNull | 800.97K | ± 5.11K | ops/s |
| prometheusWriteToByteArray | 784.11K | ± 4.84K | ops/s |
| openMetricsWriteToNull | 745.49K | ± 10.29K | ops/s |
| openMetricsWriteToByteArray | 728.74K | ± 5.87K | ops/s |

## Allocation per operation

JMH GC profiler `gc.alloc.rate.norm`, in bytes per benchmark operation (lower is better).
Delta is PR minus base, shown only for matching benchmark configurations. Values are descriptive, not statistical regression verdicts; — means unavailable or not comparable. Each benchmark defines its own operation.

| Benchmark | PR B/op | Base B/op | Delta B/op |
|:----------|--------:|----------:|-----------:|
| CounterBenchmark.codahaleIncNoLabels | 0.016 | — | — |
| CounterBenchmark.openTelemetryAdd | 0.050 | — | — |
| CounterBenchmark.openTelemetryBoundAdd | 0.024 | — | — |
| CounterBenchmark.openTelemetryBoundInc | 0.021 | — | — |
| CounterBenchmark.openTelemetryInc | 0.043 | — | — |
| CounterBenchmark.openTelemetryIncNoLabels | 0.034 | — | — |
| CounterBenchmark.prometheusAdd | 0.059 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesInc | 0.000 | — | — |
| CounterBenchmark.prometheusCachedLabelValuesIncSingleThread | 0.000 | — | — |
| CounterBenchmark.prometheusInc | 0.048 | — | — |
| CounterBenchmark.prometheusLabelValuesInc | 48.000 | — | — |
| CounterBenchmark.prometheusLabelValuesIncSingleThread | 48.000 | — | — |
| CounterBenchmark.prometheusNoLabelsInc | 0.055 | — | — |
| CounterBenchmark.simpleclientAdd | 0.127 | — | — |
| CounterBenchmark.simpleclientInc | 0.117 | — | — |
| CounterBenchmark.simpleclientNoLabelsInc | 0.123 | — | — |
| HistogramBenchmark.openTelemetryBoundClassic | 0.145 | — | — |
| HistogramBenchmark.openTelemetryBoundExponential | 1.014 | — | — |
| HistogramBenchmark.openTelemetryClassic | 0.176 | — | — |
| HistogramBenchmark.openTelemetryExponential | 1.180 | — | — |
| HistogramBenchmark.prometheusClassic | 0.370 | — | — |
| HistogramBenchmark.prometheusClassicPerThread | 0.470 | — | — |
| HistogramBenchmark.prometheusClassicSingleThread | 0.421 | — | — |
| HistogramBenchmark.prometheusNative | 417713.065 | — | — |
| HistogramBenchmark.simpleclient | 0.163 | — | — |
| HistogramTextFormatBenchmark.openMetricsWriteToNull | 43648.098 | — | — |
| HistogramTextFormatBenchmark.prometheusWriteToNull | 43648.099 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToByteArray | 18424.001 | — | — |
| TextFormatUtilBenchmark.openMetricsWriteToNull | 18424.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToByteArray | 18448.001 | — | — |
| TextFormatUtilBenchmark.prometheusWriteToNull | 18448.001 | — | — |

### Raw Results

```text
Benchmark                                            Mode  Cnt          Score        Error  Units
CounterBenchmark.codahaleIncNoLabels                thrpt   15      57016.343    ± 354.590  ops/s
CounterBenchmark.openTelemetryAdd                   thrpt   15      18777.291     ± 24.190  ops/s
CounterBenchmark.openTelemetryBoundAdd              thrpt   15      38864.472    ± 393.646  ops/s
CounterBenchmark.openTelemetryBoundInc              thrpt   15      45383.812    ± 473.812  ops/s
CounterBenchmark.openTelemetryInc                   thrpt   15      21577.115     ± 17.293  ops/s
CounterBenchmark.openTelemetryIncNoLabels           thrpt   15      27734.538    ± 606.208  ops/s
CounterBenchmark.prometheusAdd                      thrpt   15      62408.370    ± 561.237  ops/s
CounterBenchmark.prometheusCachedLabelValuesInc     thrpt   15  677059191.707 ± 6935569.033  ops/s
CounterBenchmark.prometheusCachedLabelValuesIncSingleThread  thrpt   15  370913997.150 ± 428112.611  ops/s
CounterBenchmark.prometheusInc                      thrpt   15      76959.950    ± 600.051  ops/s
CounterBenchmark.prometheusLabelValuesInc           thrpt   15  138689998.992 ± 2742795.097  ops/s
CounterBenchmark.prometheusLabelValuesIncSingleThread  thrpt   15   68701715.456 ± 542173.750  ops/s
CounterBenchmark.prometheusNoLabelsInc              thrpt   15      66515.000    ± 589.367  ops/s
CounterBenchmark.simpleclientAdd                    thrpt   15       7341.519    ± 279.354  ops/s
CounterBenchmark.simpleclientInc                    thrpt   15       7996.599    ± 125.955  ops/s
CounterBenchmark.simpleclientNoLabelsInc            thrpt   15       7573.389     ± 38.625  ops/s
HistogramBenchmark.openTelemetryBoundClassic        thrpt   15       6906.456   ± 1956.939  ops/s
HistogramBenchmark.openTelemetryBoundExponential    thrpt   15        922.611     ± 45.201  ops/s
HistogramBenchmark.openTelemetryClassic             thrpt   15       5403.205    ± 415.624  ops/s
HistogramBenchmark.openTelemetryExponential         thrpt   15        794.528     ± 42.888  ops/s
HistogramBenchmark.prometheusClassic                thrpt   15      10502.812   ± 2569.828  ops/s
HistogramBenchmark.prometheusClassicPerThread       thrpt   15      17424.524     ± 92.189  ops/s
HistogramBenchmark.prometheusClassicSingleThread    thrpt   15       6932.141    ± 357.790  ops/s
HistogramBenchmark.prometheusNative                 thrpt   15       3522.034    ± 307.990  ops/s
HistogramBenchmark.simpleclient                     thrpt   15       5793.752     ± 88.737  ops/s
HistogramTextFormatBenchmark.openMetricsWriteToNull  thrpt   15      35573.683    ± 251.913  ops/s
HistogramTextFormatBenchmark.prometheusWriteToNull  thrpt   15      35188.810    ± 145.051  ops/s
TextFormatUtilBenchmark.openMetricsWriteToByteArray  thrpt   15     728735.555   ± 5870.195  ops/s
TextFormatUtilBenchmark.openMetricsWriteToNull      thrpt   15     745488.768  ± 10294.057  ops/s
TextFormatUtilBenchmark.prometheusWriteToByteArray  thrpt   15     784112.494   ± 4844.315  ops/s
TextFormatUtilBenchmark.prometheusWriteToNull       thrpt   15     800968.938   ± 5108.050  ops/s
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
