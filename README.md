# DIKWP-SAIL v1.0.0

**DIKWP Semantic Accountability & Interoperability Layer**

DIKWP-SAIL deploys the D/I/K/W/P constraints of DIKWP-MESH8.0 between models, agents, tools, memory stores, workflows and governance systems. It is not a replacement for transport protocols. MCP may continue to connect models to tools; A2A may continue to connect independent agents; model APIs may continue to carry responses. SAIL adds a protocol-neutral semantic control plane: machine-readable Semantic Passports, W/P responsibility gates, cross-protocol handoffs, replayable receipts and a conformance kit.

## Core invariants

- Only D, I, K, W and P have semantic-generative authority.
- Every packet explicitly contains all five positions; unavailable content is retained as `given:false`.
- All 25 directed core routes are available. A route writes only when the source is given and the target is explicitly supplied.
- Concept aliases are registered after a packet exists; aliases have semantic authority 0.
- Carrier fields, JSON, timestamps, digests, logs, receipts and telemetry have semantic authority 0.

## Capabilities

1. Semantic Passport for model, tool, agent and memory events.
2. W/P Responsibility Gate for actions and persistence, without automatic execution.
3. MCP, A2A, OpenAI-Responses-shaped and generic JSON adapters.
4. Handoff preservation with no automatic W/P inheritance.
5. Hash-chain receipts, deterministic replay and optional HMAC.
6. `dikwp.sail.*` observability attributes and W3C PROV-O-shaped JSON-LD.
7. A 35-obligation, non-weighted conformance TCK.
8. A dependency-free local HTTP gateway.

## Quick start

```bash
python -m pip install dist/dikwp_sail-1.0.0-py3-none-any.whl
dikwp-sail core
dikwp-sail conformance --out outputs/CONFORMANCE.json
dikwp-sail demo-all --out-dir outputs/reference
dikwp-sail serve --host 127.0.0.1 --port 8780
```

Without installation:

```bash
python dist/DIKWP_SAIL.pyz core
python dist/DIKWP_SAIL.pyz demo mcp_ready --out outputs/mcp_ready.json --dashboard outputs/mcp_ready.html
```

## Boundary

SAIL does not determine external truth, replace user authorization, execute tools, write memory, certify consciousness, or promote carrier fields into D/I/K/W/P. `READY_FOR_CALLER_EXECUTION` only means that the declared semantic obligations are explicit in the supplied objects. The host remains responsible for execution.

Code license: Apache-2.0. Cite the documentation under the recommended CC BY 4.0 terms. See `NOTICE` and `CITATION.cff`.
