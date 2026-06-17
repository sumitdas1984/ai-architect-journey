# Plan: AWS Lambda + Bedrock Module Implementation

## Context

User wants to build Module 1 of Tier 1 (Cloud & Production AI) in the ai-architect-journey repository. The goal is a working Python Lambda function that connects to Amazon Bedrock. Based on the existing `infra/`, `src/`, `tests/` structure, I'll create a complete working module.

## Approach

Create a minimal but functional Lambda function that:
1. Responds to API Gateway events
2. Calls Amazon Bedrock (Claude model via Converse API)
3. Returns structured JSON responses
4. Follows the existing Python + AWS SAM patterns

## Files to Create

### `tier_01_cloud_prod/lambda_bedrock_v1/src/`
- `__init__.py` - Package marker
- `handler.py` - Lambda entry point, handles API Gateway proxy events
- `bedrock_client.py` - Client wrapper for Bedrock Converse API
- `exceptions.py` - Custom exceptions for error handling

### `tier_01_cloud_prod/lambda_bedrock_v1/tests/`
- `__init__.py` - Package marker
- `test_handler.py` - Unit tests for handler
- `test_bedrock_client.py` - Unit tests for Bedrock client (mocked)

### `tier_01_cloud_prod/lambda_bedrock_v1/infra/`
- `template.yaml` - AWS SAM template for deployment
- `config.json` - Environment-specific configuration

### `tier_01_cloud_prod/lambda_bedrock_v1/requirements.txt`
- Python dependencies (boto3, pytest, pytest-mock)

### `tier_01_cloud_prod/lambda_bedrock_v1/README.md`
- Module-specific documentation

## Key Implementation Details

- **Runtime**: Python 3.12
- **Bedrock API**: Use `boto3.client('bedrock-runtime')` with `converse()` API (not older invoke_model)
- **Model**: Anthropic Claude 3 Haiku (`anthropic.claude-3-haiku-20240307-v1:0`)
- **Error handling**: Graceful fallback if Bedrock call fails, returns proper HTTP status codes
- **CORS**: Enabled for API Gateway integration

## Verification

1. Run `python -m pytest tests/` to execute unit tests
2. Deploy via `sam deploy` (requires AWS credentials)
3. Test via API Gateway endpoint or `sam local invoke`
