# NeoMundi — Runtime Signal Layer for AI Agents

Add runtime AI signals to your agents in minutes.

→ Get free API access:
https://controltower.neomundi.io/pricing

- 100 free requests
- No credit card required
- Win 1000 requests for feedback

---

NeoMundi adds a real-time runtime signal layer to AI agents and LLM systems.

Detect drift, expose actionable runtime telemetry, and trigger decisions while your agents run.

Use the signal to:

- stop
- retry
- reroute
- escalate to humans
- govern agent behavior in real time

For LLM systems, runtime signals may reveal the point of maximum useful information before drift, noise, and token inflation begin.

---

# Quickstart

## GOV Mode · runtime orchestration during generation

**Bring Your Own Key. Full privacy.** Your provider key remains under your control. NeoMundi processes the generative runtime stream to produce governance and orchestration signals, without prompt or response retention.

```bash
curl -N -X POST https://api.neomundi.io/v1/govern/stream \
  -H "X-API-Key: ct_live_xxx" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "Your prompt here",
    "model": "gpt-4o",
    "provider_api_key": "sk-xxx"
  }'
```

**You receive a stream of signal events:**

```json
{
  "decision": "FLAG",
  "stability_score": 0.67,
  "delta_g": 0.13,
  "regime": "SIGNAL"
}
```

**Then your code decides:**

```python
if decision == "FLAG":
    retry()

if delta_g > threshold:
    escalate_to_human()

if stability_score < 0.60:
    reroute()
```

→ Get your `X-API-Key` at [controltower.neomundi.io](https://controltower.neomundi.io) — 100 free requests, no card.

```
# Architecture

- BYOK (Bring Your Own Key)
- No provider key retention
- No prompt retention
- No response storage
- Runtime-only processing

## Specifications

- [GOV Runtime Orchestration](https://github.com/neomundi-io/neomundi-gov)
- [Full API Quickstart](https://github.com/neomundi-io/neomundi-sandbox/blob/main/docs/QUICKSTART)
