# python_singly_linkedlist
![](https://codebuild.us-east-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiS2pCeTZsVEI1b0VhWEY4ZHQ1d3orM0xQdEdhb2hXQnNVRjRKUWIxRDhuMzFKZklYaVZOU2dFU21kekN4dTQ1SUhWWGlZdVV4ZWpsVUtDR2ZScVRtdFNvPSIsIml2UGFyYW1ldGVyU3BlYyI6Im9jT21LbXNGV0tFbXVQeXgiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=main)
- A simple linked list library to test GitHub-Jenkins integration & Python packaging
- Jenkins Server:
  - Setup in local-machine or AWS
  - Uses a [Multibranch](https://www.jenkins.io/doc/book/pipeline/multibranch/) pipeline job, based on [Jenkinsfile](https://github.com/alan-augustine/python_singly_linkedlist/blob/master/Jenkinsfile) in this repo
  - The build uses bash script [build.sh](https://github.com/alan-augustine/python_singly_linkedlist/blob/master/build.sh) and Docker image from [ubuntu_python3](https://hub.docker.com/repository/docker/tech7/ubuntu_python3)
  - The Jenkins job uses a Github personal access token with full repo access, to update the build status in PRs and commits
 - Main build steps(`build.sh`) :
   - setup a python virtual environment
   - start a local [PyPi](https://github.com/pypiserver/pypiserver#quickstart-installation-and-usage) server to test package publish and install
   - code linting using [flake8](https://pypi.org/project/flake8/) and [pylint](https://github.com/PyCQA/pylint)
   - run unit tests written using [pytest](https://docs.pytest.org/en/6.2.x/)
   - build and generate package
   - upload the packages generated as part of build, to local Pypi server using [twine](https://twine.readthedocs.io/en/latest/)
   - install the package from local PyPi server



