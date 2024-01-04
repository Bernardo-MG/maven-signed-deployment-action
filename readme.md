# Maven Signed Deployment Action

Builds, signs and deploys Maven artifacts.

## Inputs

| Input           | Description                                                             | Required                              |
|-----------------|-------------------------------------------------------------------------|---------------------------------------|
| username        | Username for the deployment server.                                     | True                                  |
| password        | Password for the deployment server.                                     | True                                  |
| gpg-private-key | Private key for signing.                                                | True                                  |
| gpg-passphrase  | Passphrase for signing.                                                 | True                                  |
| repository      | Maven repository (distribution management) for deploying the artifacts. | False, defaults to 'ossrh'            |
| profile         | Maven profile for site deployment.                                      | False, defaults to 'deployment-ossrh' |
| jdk             | JDK version to use.                                                     | False, defaults to '11'               |

## Usage

This builds and deploys the Maven site.

```yaml
jobs:
  deploy:
    name: Deployment
    runs-on: ubuntu-latest

    steps:
    - name: Deploy signed
      uses: bernardo-mg/maven-signed-deployment-action@v1
      with:
        username: ${{ secrets.username }}
        password: ${{ secrets.password }}
        gpg-private-key: ${{ secrets.gpg-private-key }}
        gpg-passphrase: ${{ secrets.gpg-passphrase }}
```

## Collaborate

Any kind of help with the project will be well received, and there are two main ways to give such help:

- Reporting errors and asking for extensions through the issues management
- or forking the repository and extending the project

### Issues management

Issues are managed at the GitHub [project issues tracker][issues], where any Github user may report bugs or ask for new features.

### Getting the code

If you wish to fork or modify the code, visit the [GitHub project page][scm], where the latest versions are always kept. Check the 'master' branch for the latest release, and the 'develop' for the current, and stable, development version.

## License
The project has been released under the [MIT License][license].

[issues]: https://github.com/Bernardo-MG/maven-signed-deployment-action/issues
[license]: https://www.opensource.org/licenses/mit-license.php
[scm]: https://github.com/Bernardo-MG/maven-signed-deployment-action
