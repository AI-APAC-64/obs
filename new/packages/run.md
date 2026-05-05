# wd-otel packages

Three pip-installable packages that abstract OpenTelemetry instrumentation behind decorators, base classes, and helpers.

| Package | Purpose |
|---|---|
| `wd-otel-core` | Config loader, OTel setup (traces / metrics / logs), shared helpers |
| `wd-otel-mcp` | `@traced_tool` decorator for FastMCP tool servers |
| `wd-otel-orchestrator` | `TracedOrchestrator` base class for multi-agent flows |

`wd-otel-mcp` and `wd-otel-orchestrator` both depend on `wd-otel-core`.

## Install

From the repo root, in editable mode:

```bash
pip install -e packages/wd-otel-core
pip install -e packages/wd-otel-mcp
pip install -e packages/wd-otel-orchestrator
```

Install `wd-otel-core` first so the other two can resolve it.

## Verify

```bash
python -c "import wd_otel, wd_otel_mcp, wd_otel_orchestrator; print('ok')"
```

## Run tests

Each package ships its own pytest suite:

```bash
pip install pytest pytest-asyncio
pytest packages/wd-otel-core/tests
pytest packages/wd-otel-mcp/tests
pytest packages/wd-otel-orchestrator/tests
```
