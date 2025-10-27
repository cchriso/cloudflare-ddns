# cloudflare-ddns helm chart
Here you find a Helm chart for deploying the cloudflare-ddns application to a Kubernetes cluster.

## Prerequisites
- A Kubernetes cluster
- Helm installed
- A Docker image of cloudflare-ddns available in a container registry

## Installation
1. Clone this repository or copy the Helm chart files to your local machine.
2. Navigate to the directory containing the Helm chart.
3. Customize the `values.yaml` file to set your desired configuration, such as the Docker image repository and tag.
4. Customize the `config.json` file with your desired cloudflare-ddns settings.
    - ⚠️ Make sure to not override the environment variables `${CF_DDNS_ZONE_ID}` and `${CF_DDNS_API_TOKEN}` as they are expected to be provided via Kubernetes secret.
5. Install the Helm chart using the following command:
    ```bash
    helm install cloudflare-ddns ./cloudflare-ddns
    ```

## Infos
- The deployment will create a single replica of the cloudflare-ddns application, as there is no need for multiple instances + it would just interfere with each other.
- Currently there is no plan to publish this Helm chart to a public Helm repository. You can use it locally or host it in your own Helm repository if needed.