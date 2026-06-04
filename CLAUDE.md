# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

AI Architect Journey is a structured learning path from cloud infrastructure to advanced agentic AI systems. It is organized into 5 tiers:

| Tier | Directory | Focus |
|------|-----------|-------|
| 1 | tier_01_cloud_prod | AWS Lambda, API Gateway, S3, Bedrock, CI/CD |
| 2 | tier_02_core_ai | Prompt Engineering, RAG, Embeddings, Vector DBs |
| 3 | tier_03_agentic | LangGraph, Agents, MCP, Orchestration |
| 4 | tier_04_ops | Evaluation frameworks, Langfuse, Observability |
| 5 | tier_05_architecture | System design documents |

## Current State

The repository is in early stages. The only populated module is `tier_01_cloud_prod/lambda_bedrock_v1/`, which follows a standard `infra/`, `src/`, `tests/` structure but contains no implementation files yet.

## Working Directory

All tier directories are siblings at the repository root. When working on a specific tier, operate within that tier's subdirectory.

## Commands

No build, lint, or test commands are defined yet as the codebase is empty. Commands will be defined as tiers are populated.
