### Welcome to your very own Spark on Domino quick-start project!

Domino supports fully containerized execution of Spark workloads on the Domino Kubernetes cluster. You can interact with Spark through a Domino workspace or in batch mode through a Domino job, as well as directly with spark-submit.

When you start a workspace or a job that uses an on-demand cluster, Domino orchestrates a cluster in standalone mode. The master and workers are newly deployed containers and the driver is your Domino workspace or job.

This quick-start project has examples for connecting to Spark, processing data, and creating a simple model. 

_Before you get started, you might want to check out [our product tour video](https://www.dominodatalab.com/p/weekly-live-demo-ungated/)._

### Data for Domino's On-Demand Spark

When using a Domino on-demand Spark cluster any data that will be used, created, or modified as part of the interaction must go into an 
external data store. Domino Datasets are an easy way to get started, and what we will be using in this project. 

When you create a Spark cluster attached to a Domino workspace or job, any Domino dataset accessible from the workspace or job will also be accessible from all components of the cluster under the same dataset mount path.

### Starting a Spark Workspace

To start a Spark workspace you will need two environments.  The first is an environment that will be used for the workspace.  This environment should have PySpark installed, preferably the latest version. The second environment is the spark workers environment, which should also have the identical version of Spark installed.  These should be available by default in your Domino instance, and more information on these environments can be found [here](https://docs.dominodatalab.com/en/latest/user_guide/1962f3/configure-prerequisites/).

Then when starting a workspace you will go through the following steps

1. Choose create new workspace
2. Choose the workspace environment for Spark, for example `5.3 Spark Compute Environment` as well as the appropriate hardware tiers.
3. Review the datasets associated with the project.  In general this is just a matter of checking through the list.
4. Choose the worker's environment, hardware tier and memory allocated.  

See for more information on starting and using workspaces see: [Domino Documentation on Workspaces](https://docs.dominodatalab.com/en/latest/get_started/3-start_workspace.html?highlight=workspace)

### Connect to Your Cluster

When provisioning your on-demand Spark cluster, Domino sets up key default cluster configuration parameters (for example, spark.master, spark.driver.host) to the appropriate cluster URLs so that creating SparkSession or SparkContext with default context will properly connect the cluster to your workspace or job. 

### Knowledge Management and Sharing

Right now, you're reading the `README.md` file which is a great place to explain what your project is all about.  We suggest every project have a README file -- it helps others onboard onto your project quickly and helps you remember what the point of your project was in the first place.

README files get shown on a project's overview page and, like all files, get automatically versioned for your convenience and time traveling needs. You can even embed images from the web or your project, for example `benefits.png`: ![Benefits](benefits.png)

Want to share this project with others? Domino makes it easy for multiple people to collaborate on a project, or to share your projects publicly. [You can add collaborators to this project or adjust its visibility here.](https://docs.dominodatalab.com/en/latest/reference/projects/Sharing_and_collaboration.html)
_____

**Need some extra help?**

* Simply email [support@dominodatalab.com](mailto:support@dominodatalab.com) or click the blue circular help icon to ask for help without leaving Domino.
* We've also got a ton of great content on [docs.dominodatalab.com](https://docs.dominodatalab.com)
