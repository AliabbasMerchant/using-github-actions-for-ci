Now that we've got our job created, let's add the step.

```yaml
on: pull_request_review
name: Label approved pull requests
jobs:
  labelWhenApproved:
    name: Label when approved
    runs-on: ubuntu-latest
    steps:
    - name: Label when approved
      uses: pullreminders/label-when-approved-action@master
      env:
        APPROVALS: "1"
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        ADD_LABEL: "approved"
        REMOVE_LABEL: "awaiting review"
```

Here we're using the action with `uses`. You can find out more about it by going directly to [its repo](https://github.com/pullreminders/label-when-approved-action).

I'll respond when you commit.