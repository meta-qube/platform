# Media processing

**Category:** Data & storage  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Transform stored media (resize, transcode, thumbnail, extract metadata, optional malware scan) via async jobs bound to file storage objects.

## Scope

- Image / video / audio transform pipelines
- Metadata extraction
- Optional content safety / malware scanning hooks
- Job status and output object references

## Out of scope

- Durable blob storage — File and media storage
- User-facing CDN — Infrastructure / cdn

## Inputs

| Input | Description |
|---|---|
| Source object ref | From file and media storage |
| Pipeline recipe | Transforms and outputs |
| Priority / deadline | Queue hints |

## Outputs

| Output | Description |
|---|---|
| Derived objects | Thumbnails, variants, transcripts |
| Job result | Success, failure, skip reasons |

## Compatibility

Heavy jobs must run in workers, not request path. Respect tenant quotas and compliance (no processing in disallowed regions).

## Verification

- Failed jobs retry per policy then surface error
- Output objects inherit tenant and residency of source
- No unauthenticated access to derived media
