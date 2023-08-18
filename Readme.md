# Delete image tag action

Allows to delete a Docker image tag from a Docker registry.
For now, only renaming is supported.

## Inputs
- registry:
  - description: 'Registry url'
  - required: true
- namespace:
  - description: 'Namespace'
  - required: true
- password:
  - description: 'Password'
  - required: true
- username:
  - description: 'Username'
  - required: false
  - default: "userdoesnotmatter"
- image_name:
  - description: 'Image name'
  - required: true
- tag:
  - description: 'Image tags'
  - required: true
- outdated_tag:
  - description: 'Outdated image tags'
  - default: "outdated"

## Usage 
```yaml
- name: Build and push Docker image
  uses: OpenSourcePolitics/delete-images-action@v1
  with:
    registry: ${{ secrets.REGISTRY_URL }}
    namespace: ${{ secrets.REGISTRY_NAMESPACE }}
    password: ${{ secrets.REGISTRY_PASSWORD }}
    username: ${{ secrets.REGISTRY_USERNAME }}
    image_name: ${{ secrets.REGISTRY_IMAGE_NAME }}
    tag: ${{ github.ref }}
```