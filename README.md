# test-tf-cost-estimator-for-AWS

### Purpose of the repsoitory
- Example of cost estimator in TF Cloud by creating Ubuntu 18 machine in AWS. 

### List of files in the respository.
- main.tf - file with terraform configuration code.

### How to use this repository
- Install `terraform` by following this [instructions](https://www.terraform.io/intro/getting-started/install.html).
- Assuming you have TF Cloud account you need to create new workspace and link it to this repo.
- Next you need to declare variables in the workspace you just created and assign values to those variables
- For variables `access_key` and `secret_key` use sensitive optioinfrastructurn, for the rest you can leave as default.
- Also make sure your variables in TF Cloud workspace are defined in your `main.tf` code and the names are the same. 
- Clone the repository to your local computer: `git clone git@github.com:nikcbg/test-tf-cost-estimator-for-AWS.git`.
- Go into the cloned repo on your computer: `cd test-tf-cost-estimator-for-AWS.git`.
- Next commit some changes to this repository to create a pull request.
- Next merge the pull request, after merging:
  - this will trigger a plan run in TF Cloud which you can watch in TF workspace that is link to this repo unders runs
  - if no issues you can apply the changes by clicking the apply button under the plan window.
  - after it is done you can check your AWS console to see if the EC2 instance was created.
  - check this link [tf-cost.png](tf-cost.png) to see a screenshot of the cost estimation in TF Cloud.

### How to destroy resources from TFE UI
- To destroy the EC2 instance you just created in AWS, you need to do the following:
   - declare environment varible in your workspace that you linked to this repo.
   - environment varibles are located under Terraform Variables in the workspace.
   - the name of the variable has to be `CONFIRM_DESTROY` and the value set to `1`.
 - Next go to `Settings` and choose `Destruction and Delition` on the bottom of the drop-down menu.
 - Next click on `Queueing a destroy Plan ` and you can watch how the EC2 instance it's been destroyed.
 
