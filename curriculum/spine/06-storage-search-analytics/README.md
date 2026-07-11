# Storage, Search & Analytics

Files, documents, and turning operational data into questions you can answer.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Object Storage & Uploads](01-object-storage-and-uploads.md) | 🔴 must | ~2 wknds | presigned URLs, multipart, checksums, lifecycle policies — SlipCheck photos already live here |
| [File Processing Pipelines](02-file-processing-pipelines.md) | 🟡 should | ~2 wknds | async image processing, thumbnails, EXIF/GPS extraction, virus scanning |
| [Document Generation](03-document-generation.md) | 🟡 should | ~1 wknd | PDF reports, templating, async generation — SlipCheck compliance reports |
| [Data Formats & Serialization](04-data-formats-and-serialization.md) | 🟡 should | ~1 wknd | JSON vs Protobuf vs Avro, schema evolution, compression |
| [Search](05-search.md) | 🟡 should | ~2 wknds | inverted indexes, tokenization, relevance, Postgres FTS before dedicated engines |
| [Analytics Pipelines](06-analytics-pipelines.md) | 🟡 should | ~2 wknds | event collection, ETL/ELT, columnar storage, reading off the event stream not prod DB |
| [Stream Processing](07-stream-processing.md) | ⚪ nice | ~2 wknds | windows, watermarks, stateful processing |
