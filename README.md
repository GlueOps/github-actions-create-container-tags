# Custom Action to Create the Default GlueOps Image Tags

The GlueOps platform relies upon specific tags for CI/CD automation. This Action automates the creation of those tags.

## Tags Created

* `Target Reference:` Either Branch Name or Tag, depending upon the trigger context.
* `Short SHA`
* `SHA`

## Usage

Can be implemented as a stand alone action, or coupled with the action [GlueOps/github-actions-build-push-containers](https://github.com/GlueOps/github-actions-build-push-containers).

### Output Values

* `tags_csv`: comma-separated string of generated tags.
* `clean_target_ref`: the target reference (e.g. branch name or tag) with invalid characters for a container tag removed.
* `target_ref_type`: the type of target reference, one of ["branch", "pull_request", "tag", "unknown"].

### Example Configuration

```yaml
- name: Create GlueOps Tags
    if: inputs.tags == ''
    uses: Glueops/github-actions-create-container-tags@v0.1.1
    id: create-tags
```
