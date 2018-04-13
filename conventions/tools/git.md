# About GIT conventions

## Repositories prefixes

| Prefix     | Description                                    |
|------------|------------------------------------------------|
| app-       | Autonomous application (example: monolith app) |
| service-   | Back-end service application(s)                |
| func-      | Function (example: lambda)                     |
| frontend-  | Front-end application(s)                       |
| gfx-       | Graphics tool(s) and asset(s)                  |
| mobile-    | Mobile application(s)                          |
| docker-    | Docker images                                  |
| infra-     | Infrastructure as code                         |
|       tf-  |     For Terraform files                        |
|       pkr- |     For Packer files                           |
| test-      | Only POC, not used in production               |
| misc-      | Misc informations                              |
| build-     | Build System tools                             |
| go-        | Go packages                                    |


## Workflow

Applications development follow the **GitHub Flow** workflow.

[Understanding the GitHub Flow](https://guides.github.com/introduction/flow/) gives you more informations about its principles and how use it.

Below articles explains some useful details:

* [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html)
* [Git Flow vs Github Flow](https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/)
