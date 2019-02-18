# lambda-versioning-the-hard-way
Pipelines and CloudFormation template for safe-mode Lambda deploys without using SAM. Why? Because CFN child templates 
don't support transforms at present, so that SAM templates can't be used in child stacks.

# Repo Structure
* `ci`: Pipeline template and `buildspec.yml`
* `lambda-versioning-withoutSAM.j2`: Jinja template that is expanded in the build phase. In this specific case the only
reason is to create a new Lambda version resource (`AWS::Lambda:Version`) during deployment.
