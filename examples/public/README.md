<div align="center">

# tokmeter

*Measure tokens per second of any OpenAI-compatible endpoint from your terminal.*

[![Version](https://img.shields.io/badge/version-0.3.0-blue)](#)
[![License](https://img.shields.io/badge/license-MIT-green)](#license)
[![CI](https://img.shields.io/badge/CI-passing-brightgreen)](#)

</div>

> [!NOTE]
> Fictional project. It shows what the public template looks like once filled in.

## Why tokmeter?

Provider dashboards report averages. When you tune a serving stack you need the distribution, on your own prompts, in one command.

- **Full latency distribution**: TTFT, inter-token latency and end-to-end time, reported as p50 / p90 / p99.
- **Your prompts, not synthetic ones**: point it at a JSONL file of real requests.
- **One binary, no server**: results print as a table and save as CSV.

## Quick start

### Install

```sh
pip install tokmeter
```

### Run

```sh
tokmeter run --url http://localhost:8000/v1 --model qwen2.5-7b --requests 50
```

### See the result

A table with one row per concurrency level, and `tokmeter-results.csv` in the current directory.

```text
concurrency  ttft_p50  ttft_p99  itl_p50  tok/s
1            48 ms     71 ms     11 ms    88
8            63 ms     140 ms    14 ms    512
```

## Usage

### Replay real traffic

```sh
tokmeter run --url $URL --model $MODEL --prompts traces.jsonl
```

### Compare two deployments

```sh
tokmeter compare before.csv after.csv
```

## License

[MIT](LICENSE)
