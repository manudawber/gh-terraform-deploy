# MLOps Infrastructure

## GCP Pre-Requisites

### Management project

Services
- Service Management API
- Cloud Resource Manager API

Service accounts
- terraform-plan
- terraform-mgmt
- terraform-dev
- terraform-test
- terraform-prod

IAM
- terraform-plan
    - Viewer
- terraform-mgmt
    - (Management deployment roles)


### UAT project

Services
- Service Management API
- Cloud Resource Manager API

IAM
- terraform-plan
    - Viewer
- terraform-uat
    - (MLOps deployment roles)


### Development project

Services
- Service Management API
- Cloud Resource Manager API

IAM
- terraform-plan
    - Viewer
- terraform-dev
    - (MLOps deployment roles)


### Test project

Services
- Service Management API
- Cloud Resource Manager API

IAM
- terraform-plan
    - Viewer
- terraform-dev
    - (MLOps deployment roles)


### Production project

Services
- Service Management API
- Cloud Resource Manager API

IAM
- terraform-plan
    - Viewer
- terraform-dev
    - (MLOps deployment roles)


### Deployment roles

Management project
- Service Account Admin
- Project IAM Admin
- Secret Manager Secret Accessor
- Storage Admin 

MLOps projects
- Vertex AI administrator
- App Engine Creator
- BigQuery Admin
- Compute Network Admin
- Service Account Admin
- Project IAM Admin
- Secret Manager Secret Accessor
- Storage Admin 


## Workflows

- Dev deploy
    - Trigger: manual
    - Branches: all
    - Approval: yes
    - Steps
        - plan
        - approve
        - apply
- Test deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - apply
- Prod deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - apply
- Mgmt deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - apply
- PR open
    - Trigger: PR open
    - Branches: master
    - Approval: yes
    - Steps:
        - fmt
        - plan
