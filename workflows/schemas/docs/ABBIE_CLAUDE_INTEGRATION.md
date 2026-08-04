# Interoperability & Integration Guide (Abbie's System Bridge)

## Overview
This system exposes standardized Webhook payloads and JSON specs. It operates independently to generate RevOps assets while allowing external Claude systems to seamlessly ingest outputs.

## Integration Contract
- **Data Format:** JSON (see `schemas/content_payload_spec.json`)
- **Delivery Method:** Webhook POST or REST endpoint
- **Primary Asset Key:** `content.markdown_body`
