# Fine-tune BERT classifier example

This is an example of how you can set up a basic training pipeline on Databricks
using distributed parallelism for the various tasks involved.

It demonstrates distributed parallelism over four distinct stages:

1. **Data preparation**: We use Spark UDF's as usual here over a CPU based cluster.
2. **Training**: We use Ray on Databricks to launch a DDP training run over one or more GPU's on one or more nodes.
3. **Batch inference**: We use MLflow's `spark_udf` to generate predictions over the entire dataset.
4. **Serving endpoint**: You can optionally use the UI to deploy the model to a real-time serving endpoint.

Along the way, we use MLflow to track the run and system metrics, as well as to manage the model lifecycle.
We also use Databricks asset bundles.

## Getting Started

To deploy and manage this asset bundle, follow these steps:

### 1. Configuration

- Open the databricks.yml file and configure the settings for your environment.

### 2. Deployment

- Click the **deployment rocket** 🚀 in the left sidebar to open the **Deployments** panel, then click **Deploy**.

### 3. Running Jobs

- To run the deployed job, hover over the resource in the **Deployments** panel and click the **Run** button.

### 4. Managing Resources

- Use the **Create** dropdown to add resources to the asset bundle.
- Click **Schedule** on a notebook within the asset bundle to create a **job definition** that schedules the notebook.

## Documentation

- For information on using **Databricks Asset Bundles in the workspace**, see: [Databricks Asset Bundles in the workspace](https://docs.databricks.com/aws/en/dev-tools/bundles/workspace-bundles)
- For details on the **Databricks Asset Bundles format** used in this asset bundle, see: [Databricks Asset Bundles Configuration reference](https://docs.databricks.com/aws/en/dev-tools/bundles/reference)
