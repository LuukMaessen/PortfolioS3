# CI/CD
*You design and implement a (semi)automated software release process that matches the needs of the project context.*

# What is CI/CD?
> In software engineering, CI/CD or CICD is the combined practices of continuous integration (CI) and (more often) continuous delivery or (less often) continuous deployment (CD). [Wikipedia CI/CD](https://en.wikipedia.org/wiki/CI/CD)


# Implementation Individual Project

## CI
To Continuously Integrate new code into my project, I use different branches. When I want to add a new feature, or fix a problem, I create a new branch. Once I have finished the new feature or fixed the problem, I can merge the branch into the "Main Branch".

Because I don't wany any problems on the main branch, the CI pipeline made with github actions automatically builds the project, to see if it can sucessfully run.

Additionaly I use SonarCloud douring development for static code analasys.
SonarCloud is a tool that gives a static code analysis over the code you've written, and it can also show your code coverage over a project. Read more about [SonarCloud here](https://docs.sonarcloud.io/).

<details>
  <summary>Example CI workflow (used in User-Preferences-API)</summary>
  
  ``` yml
  # This workflow will build a .NET project
# For more information see: https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net

name: .NET

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Setup .NET
      uses: actions/setup-dotnet@v3
      with:
        dotnet-version: 6.0.x
    - name: Restore dependencies
      run: dotnet restore
    - name: Build
      run: dotnet build --no-restore
    - name: Test
      run: dotnet test --no-build --verbosity normal
  ```


</details>


## CD
To continuously deliver our projects I use [Docker](https://docs.docker.com/get-started/). After a successful merge into main, the CD pipeline creates a docker image from the main branch.


<details>
  <summary>Example CD workflow (used in User-Preferences-API)</summary>
  
  ``` yml
name: Docker Image CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:

  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Build the Docker image
      run: docker build . --file Dockerfile --tag employee-api-image:$(date +%s)
  ```
</details>


# Implementation Group Project
The group project also has a relatively similar CI/CD.
