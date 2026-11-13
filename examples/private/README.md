# kv-probe

测 vLLM 前缀缓存在多轮对话里的实际命中率，判断值不值得给 agent 场景单独调缓存策略。

> 虚构项目，用来演示私有模板填好后的样子。

## 状态

已完成。8 轮对话以内命中率稳定在 70% 以上，结论是默认策略够用，不再继续调。

| 设置 | 前缀命中率 | 备注 |
|---|---|---|
| 单轮问答 | 12% | 基线 |
| 多轮对话（8 轮） | 74% | 系统提示 + 历史 |
| 多轮对话（32 轮） | 61% | 超过显存后开始淘汰 |

## 快速开始

```sh
uv sync
uv run probe.py --turns 8 --model Qwen2.5-7B-Instruct
```

## 目录

```text
probe.py        # 发请求、读 /metrics、算命中率
traces/         # 录下来的多轮对话样本
results/        # 每次运行一个 CSV
```

## 笔记

- 决策：命中率直接读 vLLM 的 Prometheus 指标，不自己在客户端估算，两者差了 8 个百分点。
- 坑：两轮请求之间要等上一轮完全返回，否则缓存还没写入，命中率会偏低。
- 链接：[vLLM Automatic Prefix Caching](https://docs.vllm.ai/en/latest/features/automatic_prefix_caching.html)
