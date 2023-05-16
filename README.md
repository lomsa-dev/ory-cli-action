# ORY CLI GitHub Action

This repository hosts a reusable GitHub Action that enables you to run any command with the [ORY CLI](https://www.ory.sh/cli/) within your workflows. The action authenticates with the ORY CLI using the provided username and password, and then executes the specified ORY CLI command. This action is particularly useful for CI/CD pipelines that involve ORY operations.

This action is designed to be flexible and easy to use. Simply provide your ORY username and password, and the ORY CLI command you wish to run. The action will handle the authentication and command execution for you, making it easier than ever to include ORY operations in your GitHub workflows.


## Usage
To use the ORY CLI GitHub Action, you need to include it as a step in your workflow file.

Here's a basic example:


```yaml
steps:
  - uses: actions/checkout@v3

  - name: Run ORY CLI Command
    uses: lomsa-dev/ory-action@v1
    with:
      username: ${{ secrets.ORY_USERNAME }}
      password: ${{ secrets.ORY_PASSWORD }}
      command: 'update opl --file ./path/to/file.yaml --project your_ory_project'
```

Replace `${{ secrets.ORY_USERNAME }}` and `${{ secrets.ORY_PASSWORD }}` with your ORY username and password, respectively. **It's highly recommended to store sensitive information like passwords as encrypted secrets in your repository or organization.**

## Contribution
Contributions to improve this GitHub Action are welcome. Please feel free to open an issue or submit a pull request.