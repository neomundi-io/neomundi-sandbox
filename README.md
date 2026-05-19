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

## Install

```bash
pip install neomundi

# Runtime signal example

from neomundi import ControlTower

tower = ControlTower(
    api_key="ct_live_xxx"
)

result = tower.govern(
    model="gpt-4o",
    prompt="Analyze this contract",
    stream=True
)

print(result)
```

# Example output

```
{
  "decision": "FLAG",
  "stability_score": 0.67,
  "delta_g": 0.13,
  "regime": "SIGNAL"
}
```

# Runtime Actions
```
if decision == "FLAG":
    retry()

if delta_g > threshold:
    escalate_to_human()

if stability_score < 0.60:
    reroute()
```
# Architecture

- BYOK (Bring Your Own Key)
- No provider key retention
- No prompt retention
- No response storage
- Runtime-only processing

## Specifications

### GOV Runtime Orchestration
https://github.com/neomundi-io/neomundi-gov

### Full API Quickstart
docs/QUICKSTART
