# AppCD Generative IAC

This repository contains the reusable action for the AppCD Generative IAC.

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
    ## Cleanup: true, false: Cleanup the appcd mothership after the action
    ## Default: true
    cleanup: 'true'
```

## License

The scripts and documentation in this project are released under the [MIT License](./LICENSE)
