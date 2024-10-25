[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/taskmedia)](https://artifacthub.io/packages/helm/taskmedia/paperlessngx-backup)

# Helm chart: paperless-ngx backup

Kubernetes [Helm](https://helm.sh) chart to create a cronjob to backup the paperless-ngx instance to a remote FTP server.

The script will use the [document exporter](https://docs.paperless-ngx.com/administration/#exporter) to create a backup of your paperless-ngx instance.
If you want the backup also can be gpg encrypted prior to upload the zipped backup to the FTP server.

## Configuration

The configuration of the backup cronjob will be set in the [`values.yaml`](./values.yaml)-file.
Everything is pretty straight forward and should be self-explanatory.
If you think more information should be provided or need help, feel free to open an issue.

## Installation

To deploy the Helm chart first copy the [`values.yaml`](./values.yaml)-file and customize your deployment.
After it was modified you can deploy the chart with the following command.

```bash
$ helm repo add taskmedia https://helm.task.media
$ helm repo update

$ helm show values taskmedia/paperlessngx-backup > ./my-values.yaml
$ vi ./my-values.yaml

$ helm upgrade --install paperlessngx-backup taskmedia/paperlessngx-backup --values ./my-values.yaml
```

You can also use OCI Helm charts from [ghcr.io](https://ghcr.io/):

```bash
$ helm upgrade --install paperlessngx-backup oci://ghcr.io/taskmedia/paperlessngx-backup
```
