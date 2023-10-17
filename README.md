# Push folders
**Author**: RamPrin
## Description
This action is created to:
- Log into chosen container registry.
- Iterate through the directories of root repository (means non-recursively).
- Build the images and push them into container registry.
## Inputs
- **directories**: Which directories to search in. By default searches in any directory which was changed from the previous commit.
    - "*/" for all top-level directories
- **registry**: Which registry to push into:
    - ecr
    - cr.yandex
    - ghcr
- **registry_url**: The url of the registry:
    - public.ecr.aws
    - cr.yandex
    - ghcr.io
- **registry_id**: The ID of registry:
    - _ECR:_ registry-alias
    - _Yandex:_ registry-id
    - _ghcr:_ namespace
- **username**: String to enter into `docker login --username`
    - _ECR:_ ACCESS_KEY_ID
    - _Yandex:_ [ iam, oauth, json_key ]
    - _ghcr:_ USERNAME
- **password**: String to enter into `docker login --password`
    - _ECR:_ SECRET_ACCESS_KEY
    - _Yandex:_ [\<Identity and Access Management token\>, \<OAuth token\>, key.json]
    - _ghcr:_ ACCESS_TOKEN
## Note
On version 0.1.0 this action works only with public.ecr and searches only in top-level folders <br>
On version 0.2.0 directories changed from "*/" to 'changed from the previous commit'. Added input `directories` <br>
