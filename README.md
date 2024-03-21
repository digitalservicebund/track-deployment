# Deployment Frequency Metric

This GHA is used to generate the "Deployment Frequency" metric in our Engineering Dashbaord.

## How to use

```yaml
- name: Report Deployment
  uses: digitalservicebund/track-deployment@LATEST_HASH
  with:
    project: PROJECT_NAME
    environment: ENVIRONMENT
    metrics_deployment_webhook_url: ${{ secrets.METRICS_DEPLOYMENT_WEBHOOK_URL }}
    metrics_webhook_token: ${{ secrets.METRICS_WEBHOOK_TOKEN }}
```

Inputs:

- `project`: **required**. Project name to track deployments for.
- `environment`: **required**. Environment being deployed, e.g. staging, production.
- `metrics_deployment_webhook_url`: **required**.
- `metrics_webhook_token`: **required**.

`metrics_deployment_webhook_url` and `metrics_webhook_token` are organization secrets. Ask the GitHub [organization owners on slack](https://digitalservicebund.slack.com/archives/C05GVAFBPB5) to add your repo to the authorized list.

## Updating this action

After merging a dependabot PR or pushing changes, you need to [cut a new release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository).
