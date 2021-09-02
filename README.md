MLOps Infrastructure
====================

GCP Pre-Requisites
----------------------

- Management project
    - Services
        - Service Management API
        - Cloud Resource Manager API
    - Service accounts
        - terraform-plan
        - terraform-mgmt
        - terraform-dev
        - terraform-test
        - terraform-prod
    - IAM
        - terraform-plan
            - Viewer
        - terraform-mgmt
            - All required deployment roles
                - Service Account Admin
                - Project IAM Admin
                - Secret Manager Secret Accessor
                - Storage Admin 
- Development project
    - Services
        - Service Management API
        - Cloud Resource Manager APIw
    - IAM
        - terraform-plan
            - Viewer
        - terraform-dev
            - All required deployment roles
                - Vertex AI administrator
                - App Engine Creator
                - BigQuery Admin
                - Compute Network Admin
                - Service Account Admin
                - Organisation Administrator
                - Secret Manager Secret Accessor
                - Storage Admin 
- Test project
    - Services
        - Service Management API
        - Cloud Resource Manager API
    - IAM
        - terraform-plan
            - Viewer
        - terraform-dev
            - All required deployment roles
- Production project
    - Services
        - Service Management API
        - Cloud Resource Manager API
    - IAM
        - terraform-plan
            - Viewer
        - terraform-dev
            - All required deployment roles

Workflows
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
