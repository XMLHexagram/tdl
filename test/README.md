# E2E Testing

End-to-end tests for tdl using exported credentials.

## Usage

```bash
# 1. Export credentials
cd tools
go run export_credentials.go -namespace default -output ../test/test.json

# 2. Run tests
cd ../test
TDL_TEST_CREDENTIALS_FILE=test.json go test ./... -v
```

Or from project root:

```bash
TDL_TEST_CREDENTIALS_FILE=$(pwd)/test/test.json go test ./test/... -v
```

## Security

- `test.json` is in `.gitignore`
- Never commit credentials to version control
