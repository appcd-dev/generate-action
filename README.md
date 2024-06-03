# appCD Generative IAC

This repository contains the reusable action for the appCD Generative IAC.

## Setup

Please follow the steps below to setup the action:

1. Signup for an account on [appCD](https://cloud.appcd.io/)
2. Setup a Personal Access Token on [appCD](https://cloud.appcd.io/account-settings/pat/)
3. Add the Personal Access Token as a secret in your repository with the name `APPCD_TOKEN`

## Inputs

| Name         | Description                       | Required | Default   |
|--------------|-----------------------------------|----------|-----------|
| `cloud`           | Cloud provider                    | No       | "aws"     |
| `language`        | Programming language              | No       | "Python"  |
| `outputDir`       | Output directory                  | No       | "./iac"   |
| `scanPath`        | Path to scan                      | No       | "."       |
| `targetCompute`   | Target compute                    | No       | "k8s"     |
| `cleanup`         | Cleanup                           | No       | "true"    |

## Usage

```yaml
- name: Generate IAC
  uses: appcd-dev/action@v0
  env:
    APPCD_TOKEN: ${{ secrets.APPCD_TOKEN }}
  with:
    # Required inputs
    ## Cloud provider: aws, azure
    ## Default: aws
    cloud: 'aws'
    ## Programming language: Python, Java
    ## Default: Auto detect based on file extensions
    language: 'Python'
    ## Output directory: Directory to store the generated IAC
    ## Default: current directory
    outputDir: './iac'
    ## Path to scan: Path to scan for the application
    ## Default: current directory
    scanPath: '.'
    ## Target compute: k8s, ecs
    ## Default: k8s
    targetCompute: 'k8s'
    ## Cleanup: true, false: Cleanup the appCD mothership after the action
    ## Default: true
    cleanup: 'true'
```

## License

The scripts and documentation in this project are released under the [MIT License](./LICENSE)
