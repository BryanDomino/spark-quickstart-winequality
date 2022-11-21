### Welcome to your very own Spark on Domino quick-start project!

Domino supports fully containerized execution of Spark workloads on the Domino Kubernetes cluster. You can interact with Spark through a Domino workspace or in batch mode through a Domino job, as well as directly with spark-submit.

When you start a workspace or a job that uses an on-demand cluster, Domino orchestrates a cluster in standalone mode. The master and workers are newly deployed containers and the driver is your Domino workspace or job.

This quick-start project has examples for connecting to Spark, processing data, and creating a simple model. 

_Before you get started, you might want to check out [our product tour video](https://www.dominodatalab.com/p/weekly-live-demo-ungated/)._

### Data for Domino's On-Demand Spark

Note that when using a Domino on-demand Spark cluster any data that will be used, created, or modified as part of the interaction must go into an 
external data store. Domino Datasets are an easy way to get started, and what we will be using in this project. 

## Step 0: Setup the environments for workspace base and compute cluster

To start a Spark workspace you will need two environments.  The first is an environment that will be used for the workspace.  This environment should have PySpark installed, preferably the latest version. The second environment is the spark workers environment, which should also have the identical version of Spark installed.  These should be available by default in your Domino instance, and more information on these environments can be found [here](https://docs.dominodatalab.com/en/latest/user_guide/1962f3/configure-prerequisites/).

See for more information on starting and using workspaces see: [Domino Documentation on Workspaces](https://docs.dominodatalab.com/en/latest/get_started/3-start_workspace.html?highlight=workspace)

## Step 1: Create the project and download the files 

1. Create a new Project named "Spark-QuickStart" (or whatever name you like), hosted by Domino File System.
2. Download the files from this repo, then upload them to the Files section of your project.
    - `WineQualityModel-PySpark.ipynb`
    - `wine_quality.csv`
    - `README.md`

If you are reading this README in a Domino project that has been shared with you, simply Copy the project.

## Step 2: Launch a workspace with attached On-Demand Spark cluster

- Navigate to the "Workspaces" section of your project
- Create a new workspace by pressing the "+ Create New Workspace" on the top right side of the window and give the following configuration:
  1. In "Environment & Hardware" 
      - (optional) Specify a name to the workspace
      - Choose a Spark environment such as `5.3 Spark Compute Environment` from the "Workspace Environment" dropdown (refer to step 0 in this README)
      - Select Jupyterlab under "Workspace IDE"
      - (optional) Choose a Hardware Tier - we recommend staying with the default, typically 1 core and 4GiB RAM
      - Click on the "Next" button
  2. In "Data"
      - No need to modify anything here; click on the "Next" button
  3. In "Compute Cluster"
      - Select Spark
      - Set the min number of workers to "3" (do not select Auto-scale workers if it is available)
      - (optional) Choose a Hardware Tier for the Worker and Scheduler - again we recommend staying with the default
      - Choose an environment from the "Cluster Compute Environment" dropdown that matches the Spark version referenced in your Workspace Environment (refer to step 0 in this README)
      - (optional) Select the checkbox of dedicated storage (we will not make use of this in the example notebooks)
- Now hit the green "Launch" button

## Step 3: Check the Spark Web UI for cluster readiness and run the sample notebooks

- On the top right within the domino page tab there should be an icon indicating: "Spark Web UI [Status]"
- Note: if Domino needs to provision new nodes to accommodate your cluster, the Status may not read "Ready" immediately.
- This tab provides all the details about the logs of the scheduler, worker nodes, and other Spark features.

### Connect to Your Cluster

When provisioning your on-demand Spark cluster, Domino sets up key default cluster configuration parameters (for example, spark.master, spark.driver.host) to the appropriate cluster URLs so that creating SparkSession or SparkContext with default context will properly connect the cluster to your workspace or job. This will be demonstrated in the `WineQualityModel-PySpark.ipynb` notebook. 

### Knowledge Management and Sharing

Right now, you're reading the `README.md` file which is a great place to explain what your project is all about.  We suggest every project have a README file -- it helps others onboard onto your project quickly and helps you remember what the point of your project was in the first place.

README files get shown on a project's overview page and, like all files, get automatically versioned for your convenience and time traveling needs. 

Want to share this project with others? Domino makes it easy for multiple people to collaborate on a project, or to share your projects publicly. [You can add collaborators to this project or adjust its visibility here.](https://docs.dominodatalab.com/en/latest/reference/projects/Sharing_and_collaboration.html)
_____

**Need some extra help?**

* Simply email [support@dominodatalab.com](mailto:support@dominodatalab.com) or click the blue circular help icon to ask for help without leaving Domino.
* We've also got a ton of great content on [docs.dominodatalab.com](https://docs.dominodatalab.com)
