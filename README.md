# Ory CLI GitHub Action

This repository hosts a reusable GitHub Action that enables you to run any command with the [Ory CLI](https://www.ory.sh/cli/) within your workflows. The action authenticates with the Ory CLI using the provided username and password, and then executes the specified Ory CLI command. This action is particularly useful for CI/CD pipelines that involve Ory operations.

This action is designed to be flexible and easy to use. Simply provide your Ory username and password, and the Ory CLI command you wish to run. The action will handle the authentication and command execution for you, making it easier than ever to include Ory operations in your GitHub workflows.


## Usage
To use the Ory CLI GitHub Action, you need to include it as a step in your workflow file.

Here's a basic example:


```yaml
steps:
  - uses: actions/checkout@v3

  - name: Run Ory CLI Command
    uses: lomsa-dev/ory-action@v1
    with:
      username: ${{ secrets.ORY_USERNAME }}
      password: ${{ secrets.ORY_PASSWORD }}
      commands: |
        update opl --file ./path/to/file.yaml --project your_ory_project
        command 2
        command 3
        ...
```

Replace `${{ secrets.ORY_USERNAME }}` and `${{ secrets.ORY_PASSWORD }}` with your Ory username and password, respectively. **It's highly recommended to store sensitive information like passwords as encrypted secrets in your repository or organization.**

## Contribution
Contributions to improve this GitHub Action are welcome. Please feel free to open an issue or submit a pull request.