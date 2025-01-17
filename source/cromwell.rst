Cromwell Advanced
==================

Use the scalability of AWS Batch to run Cromwell workflows. This is ideal for large workloads and larger data-sets.

Parameters
-----------

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. Eg: MedicalResearch 
   * - Cromwell Configuration
     -
   * - PipelineName
     - Search and select the pipeline git repository URL. If not found please enter the custom pipeline URL.
   * - InputDataLocation
     - An S3 bucket path which holds input data for the Cromwell pipeline. Eg: bucket-name/prefix
   * - OutputDataLocation
     - An S3 bucket path which holds input data for the Cromwell pipeline. Eg: bucket-name/prefix
   * - Head Node Configuration
     -
   * - InstanceType
     - Head Node EC2 instance type. Eg: t2.micro
   * - HeadNodeEBSVolumeSize
     - The initial size of the volume (in GBs) Head Node EBS will use for storage. Eg: 16 
   * - KeyPair
     - Name of an existing EC2 KeyPair to enable SSH access to the Head Node. If no key pairs exist, please create one from the button next to the dropdown. Please contact your Administrator if you are unable to create one.
   * - AllowedSSHLocation
     - The IP address range that can be used to SSH to the Head Node. For the security of your instance, we recommend you allow connections only from your own location. You can find your IP using https://whatismyipaddress.com/ Eg: 0.0.0.0/0
   * - Batch Configuration
     - 
   * - VPCId
     - Choose VPC Id in the drop-down list. The VPC to create security groups and deploy AWS Batch to. NOTE: Must be the same VPC as the provided subnet IDs.
   * - WorkerNodeSubnetId
     - Choose Subnet Id in the drop-down list. Subnet you want your batch compute environment to launch in. We recommend public subnets.
   * - ComputeEnvMinvCpus
     - The minimum number of CPUs to be kept in running state for the Batch Worker Nodes. If you give a non-zero value, some worker nodes may stay in running state always and you may incur higher cost. Eg: 0
   * - ComputeEnvMaxvCpus
     - The maximum number of CPUs for the default Batch Compute Environment. Eg: 100
   * - SpotBidPercentage
     - The maximum percentage of On-Demand pricing you want to pay for Spot resources. You will always pay the lowest Spot market price and never more than your maximum percentage. Eg: 100
   * - WorkerNodeInstanceType
     - Specify the instance types to be used to carry out the computation. You can specify one or more family or instance type. The option 'optimal' chooses the best fit of M4, C4, and R4 instance types available in the region. Eg: Optimal 
   * - WorkerNodeEBSVolumeSize
     - The initial size of the volume (in GBs) Worker Node EBS will use for storage.  Eg: 100

Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab.
3. Click the “Launch Now” button on the  “Cromwell Advanced” product card. A product order form will open. Fill the details in the form .

**Note**:

	* PipelineName 
		a.  You can see the drop down option which is on the right side of the PipelineName field.
		b.  You can search the pipeline. If you type the correct pipeline you can see the info (ie.,”i”) icon which is at the right side of the field. If you click  the info icon it will be routed to the `gatk-workflows/seq-format-validation <https://github.com/gatk-workflows/seq-format-validation>`_ repository. If you type the wrong characters it will throw an error message accordingly.

	* InputDataLocation
		a.  You can see the filter options like All/Studies/Shared/ProjectStorage/Study in the Second part of the InputDataLocation field.
		b.  You can see the default option like “**All**“ in the filter.
		c.  You can see the product names with  realted paths when you search in the InputDataLocation field. You need to select the S3 bucket name from the available list.
		d.  If you type the invalid characters it will throw an error message accordingly.
		
	* OutputDataLocation
		a.  Defaultly you can see the output path in the field.
		b.  You can see the product names with  realted paths when you search in  the OutputDataLocation field. 
		c.  You can see the filter options like All/Studies/Shared/ProjectStorage/Study.
		d.  You can see the default option like “**All**” in the filter.
		e.  If you type the invaliad characters it will throw an error message accordingly.
  
4. Click on the “Launch Now” button. You will see a  “Cromwell Advanced” being created. In a few minutes, that product should appear in the “Active” state.

Estimated time to provision -  10 minutes

Steps to connect
----------------

1. Click on the “SSH to Server” button under the “Connect” list on the right side of the page. This will open the SSH Window in a new browser tab. 
2. Enter “ec2-user” as the username. Select “Pem file” as the Authentication type. Upload the pem file in the “Pem file” field and click on the "Submit" button. You should now be connected to the EC2 instance via SSH. To submit the workflow via curl use the following command:
  
   $ curl -X POST "http://localhost:8000/api/workflows/v1" \ -H "accept: application/json" \ -F "workflowSource=@filename.wdl" \ -F "workflowInputs=@filename.json"
	  
   Note: You will receive a response accordingly
	
3. Scroll to the top of the Terminal screen and click the “Terminate” button to end the session. Alternatively, type exit and hit enter in the terminal.
4. You can view the outputs through “View Outputs” option.
5. You can de-provision the product through the “Terminate” option.

Other considerations   
---------------------

You can stop your instance using the “Stop” button in the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.

