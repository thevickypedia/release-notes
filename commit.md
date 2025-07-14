This document provides a baseline for best-practices in terms of commit messages.

| **Prefix**   | **Description**                                                                         |
|--------------|-----------------------------------------------------------------------------------------|
| **feat**     | A new feature                                                                           |
| **fix**      | A bug fix                                                                               |
| **chore**    | Routine tasks like build processes, package updates, etc.                               |
| **docs**     | Documentation-only changes                                                              |
| **style**    | Changes that do not affect meaning (e.g., formatting, white-space, missing semi-colons) |
| **refactor** | Code changes that neither fix a bug nor add a feature                                   |
| **perf**     | A code change that improves performance                                                 |
| **test**     | Adding or correcting tests                                                              |
| **build**    | Changes that affect the build system or external dependencies                           |
| **ci**       | Changes to CI configuration or scripts (e.g., GitHub Actions, CircleCI)                 |
| **revert**   | Reverts a previous commit                                                               |

```shell
git log --pretty=format:"%h %s"
```
