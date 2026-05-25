# NeoMundi — Runtime Signal Layer for AI Agents

Add runtime AI signals to your agents in minutes.

→ Get free API access:
https://controltower.neomundi.io/pricing

- 100 free requests
- No credit card required
- Win 1000 requests for feedback
→ Pilot access & feedback
Early testers may receive up to 1000 free requests.
contact@neomundi.io

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

→ Get your `X-API-Key` at [controltower.neomundi.io/pricing](https://controltower.neomundi.io/pricing) — 100 free requests, no card.

→ Pilot access & feedback
Early testers may receive up to 1000 free requests.
contact@neomundi.io

---

## Architecture

- BYOK (Bring Your Own Key)
- No provider key retention
- No prompt retention
- No response storage
- Runtime-only processing

---

## NeoMundi Runtime Governance Framework

NeoMundi is evolving from thermometer to spectrometer: from a runtime stability signal toward a multidimensional measurement layer for AI system behavior during execution.

A runtime governance signal must meet three minimal requirements: it must be observable, interpretable and interoperable.

The NeoMundi Runtime Governance Framework organizes these requirements across several public methodological repositories dedicated to observability, informational metrics, interpretation, interoperability and runtime governance for AI systems.

Together, these repositories form the minimal foundations of an industrializable AI governance infrastructure: measure, interpret, transmit, decide, trace.

### Main repositories - Core repositories

- [`neomundi-signal-adaptation-framework`](https://github.com/neomundi-io/neomundi-signal-adaptation-framework/blob/main/README_EN.md)  
  SAL layer: conceptual entry point of the framework, where heterogeneous sources are adapted into a canonical state measurable by NeoMundi.

- [`runtime-telemetry-signals`](https://github.com/neomundi-io/runtime-telemetry-signals)  
  Public definitions of runtime telemetry signals, including G, ΔG and governance states.

- [`informational-metrics`](https://github.com/neomundi-io/informational-metrics)  
  Public methodological notes on volumetry, volumetric density, informational energy and informational density.

- [`energy-stability-index`](https://github.com/neomundi-io/energy-stability-index)  
  Conceptual documentation of the Energy Stability Index as a composite governance indicator.

- [`validity-and-grounding`](https://github.com/neomundi-io/validity-and-grounding)  
  Public methodological documentation on validity, grounding, hallucination detection and the limits of proof-related signals.

- [`runtime-interoperability-contract`](https://github.com/neomundi-io/runtime-interoperability-contract)  
  Minimal interoperability semantics between measurement, orchestration and proof-anchoring layers.

- [`interpretation-contract`](https://github.com/neomundi-io/interpretation-contract)  
  Methodological boundaries for interpreting signals, metrics and governance decisions.

- [`neomundi-obs`](https://github.com/neomundi-io/neomundi-obs)  
  OBS layer: post-hoc observability, without runtime orchestration.

- [`neomundi-gov`](https://github.com/neomundi-io/neomundi-gov)  
  GOV layer: runtime governance and orchestration during generation.

- [`Boundary Tension contract`](https://github.com/neomundi-io/Boundary_Tension_contract)  
  Conceptual research repository dedicated to boundary tension signals in runtime AI systems.
The objective is not to establish absolute truth.

The objective is to make AI generation behavior observable, interpretable, interoperable, auditable and governable at runtime.
