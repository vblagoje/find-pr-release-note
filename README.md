# find-pr-release-note

## Description
The `find-pr-release-note` GitHub Action automates the process of identifying a single Reno release note in pull requests. This action is particularly useful in workflows where PR release notes need to be tracked or handled distinctively.

## Usage
To incorporate this action in your workflow, include the following step:

```yaml
- name: Identify Single Reno Note in PR
  uses: find-pr-release-note@v1
  with:
    base-branch: 'main' # Default is 'main', change if your base branch differs
```

## Inputs
- `base-branch`: **Optional** The base branch against which changes are compared. Defaults to `'main'`.

## Example Workflow
Below is an example showcasing how to use `find-pr-release-note` in a GitHub Actions workflow:

```yaml
name: Handle Release Note in PR
on: [pull_request]

jobs:
  handle-release-note:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Identify and Handle Single Reno Note
        id: reno-note-finder
        uses: find-pr-release-note@v1
        with:
          base-branch: 'main'

      # Additional steps can use the output from find-pr-release-note
```

In this example, the action identifies a single changed Reno release note file in the pull request and handles it accordingly.

## Output
- `note_name`: The name of the identified single release note.

## Contributing
Contributions to `find-pr-release-note` are encouraged and appreciated!

## License
This project is distributed under [MIT](LICENSE). 
