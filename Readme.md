# Delete image tag action

Allows to delete an image tag from a Scaleway image registry.

## Inputs
- namespace:
  - description: 'Namespace'
  - required: true
- scw_access_key:
  - description: 'scw_access_key'
  - required: true
- scw_secret_key:
  - description: 'scw_secret_key'
  - required: true
- scw_default_project_id:
  - description: 'scw_default_project_id'
  - required: true
- scw_default_organization_id:
  - description: 'scw_default_organization_id'
  - required: true
- image_name:
  - description: 'Image name'
  - required: true
- tag:
  - description: 'Image tags'
  - required: true

## Usage 
```yaml
- name: Build and push Docker image
  uses: OpenSourcePolitics/delete-images-action@v1
  with:
    namespace: ${{ vars.REGISTRY_NAMESPACE }}
    scw_access_key: ${{ secrets.ACCESS_TOKEN }}
    scw_secret_key: ${{ secrets.TOKEN }}
    scw_default_project_id: ${{ secrets.SCW_PROJECT_ID }} 
    scw_default_organization_id: ${{ secrets.SCW_ORGANIZATION_ID }}
    image_name: ${{ vars.IMAGE_NAME }}
    tag: "my_tag"
```