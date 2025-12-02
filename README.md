# ta-mon Webhook Test Repository

This repository is used to test the webhook-based auto-update system for the ta-mon monitoring application.

## Purpose

- Validate GitHub webhook delivery
- Test YAML configuration validation
- Verify automatic git pull and Gatus restart
- Test Teams alert notifications

## Test Configuration

The `config/test.yml` file contains a minimal valid Gatus configuration for testing purposes.

## Webhook Flow

1. Push changes to this repository (master branch)
2. GitHub sends webhook to ta-mon server
3. Webhook service validates YAML files
4. If valid: git pull, restart Gatus, send success alert
5. If invalid: send error alert with details (no update)

## Testing

To test the webhook:

```bash
# Make a change to config/test.yml
git add config/test.yml
git commit -m "test: update endpoint interval"
git push origin master
```

Check Teams channel for webhook notifications.
Test repository for ta-mon webhook validation with YAML config files
