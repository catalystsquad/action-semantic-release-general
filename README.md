<!-- start title -->

# GitHub Action:General Release

<!-- end title -->
<!-- start description -->

A simple action that has an option to toggle `include administrators` on branch protection, and then run semantic-release with a given release config

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystsquad/action-semantic-release-general@undefined
  with:
    # git token to use for the run
    token: ""

    # If true, this action will disable the `include administrators` setting in branch
    # protection for this branch, and re-enable it after release. Re-enabling is run
    # using always()
    # Default: false
    toggle-admins: ""

    # The release configuration to use for the release.
    # Default: @catalystsquad/release-config-general
    release-config: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**            | **Description**                                                                                                                                                                |               **Default**               | **Required** |
| :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------: | :----------: |
| **`token`**          | git token to use for the run                                                                                                                                                   |                                         |   **true**   |
| **`toggle-admins`**  | If true, this action will disable the `include administrators` setting in branch protection for this branch, and re-enable it after release. Re-enabling is run using always() |                                         |  **false**   |
| **`release-config`** | The release configuration to use for the release.                                                                                                                              | `@catalystsquad/release-config-general` |  **false**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v2
      - id: foo
        uses: actions/hello-world-composite-action@v1
        with:
          who-to-greet: "Mona the Octocat"
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
