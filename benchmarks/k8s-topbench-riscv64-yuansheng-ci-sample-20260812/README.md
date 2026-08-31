# Kubernetes Topbench RISC-V Yuansheng CI Sample

This directory contains a small sample of Kubernetes top-level benchmark results
collected on a RISC-V host through Yuansheng CI.

## Scope

- Date: 2026-08-12
- Target architecture: `riscv64`
- Runner: Yuansheng CI
- Benchmark mode: `perf stat`
- Top-level case format: one `BenchmarkXXX` regex per row

This is a compact sample for reviewing result shape only. It is not the full
artifact set.

## Files

- `sample_success_summary.tsv`: selected successful top-level benchmark rows.
- `status_counts.tsv`: status counts from the successful-result source runs.
- `perf_stat_txt/`: selected raw `perf stat` text files for successful cases.

The full local artifact directories used to produce this sample were:

- `artifacts/runs/3`: 218-case Yuansheng CI rerun, 217 PASS / 1 STAT_FAIL.
- `artifacts/runs/4`: 20-case rerun of previously missing-testdata cases,
  20 PASS.

## TSV Columns

`sample_success_summary.tsv` uses:

- `case_id`: stable case identifier derived from package and benchmark name
- `status`: benchmark result status
- `pkg`: Go package path
- `regex`: benchmark regex passed to `go test`
- `elapsed_sec`: elapsed wall time for the case
- `benchmarks`: number of benchmark output lines produced by the top-level case
- `notes`: runner notes, empty for successful rows
