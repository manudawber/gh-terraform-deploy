New Infrastructure Deployment Flow
==================================

GCP project pre-requisites
- service mgmt api enabled
- cloud resource mgr api enabled

Workflows
- Dev deploy
    - Trigger: manual
    - Branches: all
    - Approval: ?
    - Steps
        - plan
        - approve
        - deploy
- Test deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - deploy
- Prod deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - deploy
- Mgmt deploy
    - Trigger: manual
    - Branches: master
    - Approval: yes
    - Steps:
        - plan
        - approve
        - deploy
- PR open
    - Trigger: PR open
    - Branches: master
    - Approval: yes
    - Steps:
        - fmt
        - plan

