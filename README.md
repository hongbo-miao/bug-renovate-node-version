# bug-renovate-node-version

## Introduction

This is a mono repo.

- The sub module `/web` expects using Node.js 18 which defined at `/web/.nvmrc`.
- The sub module `/grafana/hm-panel-plugin` expects using Node.js 16 which defined at `/grafana/hm-panel-plugin/.nvmrc`.

### Observed behavior

Renovate is using Node.js 18 from `/web/.nvmrc` for both sub modules.

Here is the Renovate pull request: https://github.com/Hongbo-Miao/bug-renovate-node-version/pull/1

### Expected behavior

Renovate should use Node.js 18 which defined at `/web/.nvmrc` for `/web`.
Renovate should use Node.js 16 which defined at `/grafana/hm-panel-plugin/.nvmrc` for `/grafana/hm-panel-plugin`.

## Ticket

Opened the ticket at https://github.com/renovatebot/renovate/issues/18885

## Renovate Log

<details>
  <summary>Click to expand</summary>
  
  ```shell
DEBUG: No dangling containers to remove
INFO: Repository started
{
  "renovateVersion": "34.23.1"
}
DEBUG: Using localDir: /mnt/renovate/gh/Hongbo-Miao/bug-renovate-node-version
DEBUG: PackageFiles.clear() - Package files deleted
DEBUG: initRepo("Hongbo-Miao/bug-renovate-node-version")
DEBUG: Using queue: host=api.github.com, concurrency=10
DEBUG: Hongbo-Miao/bug-renovate-node-version default branch = main
DEBUG: Using app token for git init
DEBUG: Repository cache is restored from revision 13
DEBUG: Resetting npmrc
DEBUG: detectSemanticCommits()
DEBUG: checkOnboarding()
DEBUG: isOnboarded()
DEBUG: Checking cached config file name
DEBUG: Existing config file confirmed
DEBUG: Repository config
{
  "fileName": "renovate.json5",
  "config": {
    "extends": [
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "branchTopic": "lock-file-maintenance-{{packageFile}}",
      "commitMessageExtra": "({{packageFile}})"
    }
  }
}
DEBUG: Repo is onboarded
DEBUG: migrateAndValidate()
DEBUG: No config migration necessary
DEBUG: massaged config
{
  "config": {
    "extends": [
      "github>whitesource/merge-confidence:beta",
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "branchTopic": "lock-file-maintenance-{{packageFile}}",
      "commitMessageExtra": "({{packageFile}})"
    }
  }
}
DEBUG: migrated config
{
  "config": {
    "extends": [
      "github>whitesource/merge-confidence:beta",
      "config:base"
    ],
    "lockFileMaintenance": {
      "enabled": true,
      "branchTopic": "lock-file-maintenance-{{packageFile}}",
      "commitMessageExtra": "({{packageFile}})"
    }
  }
}
DEBUG: Setting hostRules from config
DEBUG: Found repo ignorePaths
{
  "ignorePaths": [
    "**/node_modules/**",
    "**/bower_components/**",
    "**/vendor/**",
    "**/examples/**",
    "**/__tests__/**",
    "**/test/**",
    "**/tests/**",
    "**/__fixtures__/**"
  ]
}
DEBUG: Using queue: host=api.github.com, concurrency=10
DEBUG: No vulnerability alerts found
DEBUG: No vulnerability alerts found
DEBUG: findIssue(Dependency Dashboard)
DEBUG: Retrieving issueList
DEBUG: Retrieved 1 issues
DEBUG: Found issue 3
DEBUG: No baseBranches
DEBUG: extract()
DEBUG: Setting current branch to main
DEBUG: Initializing git repository into /mnt/renovate/gh/Hongbo-Miao/bug-renovate-node-version
DEBUG: Performing blobless clone
DEBUG: git clone completed
{
  "durationMs": 1232
}
DEBUG: latest repository commit
{
  "latestCommit": {
    "hash": "e3643a20287fa3a865709ba0d00e3ae38123441e",
    "date": "2022-11-14T11:53:43-08:00",
    "message": "docs",
    "refs": "HEAD -> main, origin/main, origin/HEAD",
    "body": "",
    "author_name": "Hongbo Miao",
    "author_email": "Hongbo.Miao@outlook.com"
  }
}
DEBUG: latest commit
{
  "branchName": "main",
  "latestCommitDate": "2022-11-14T11:53:43-08:00"
}
DEBUG: Using file match: (^|/)tasks/[^/]+\.ya?ml$ for manager ansible
DEBUG: Using file match: (^|/)requirements\.ya?ml$ for manager ansible-galaxy
DEBUG: Using file match: (^|/)galaxy\.ya?ml$ for manager ansible-galaxy
DEBUG: Using file match: (^|/)\.tool-versions$ for manager asdf
DEBUG: Using file match: azure.*pipelines?.*\.ya?ml$ for manager azure-pipelines
DEBUG: Using file match: (^|/)batect(-bundle)?\.yml$ for manager batect
DEBUG: Using file match: (^|/)batect$ for manager batect-wrapper
DEBUG: Using file match: (^|/)WORKSPACE(|\.bazel)$ for manager bazel
DEBUG: Using file match: \.bzl$ for manager bazel
DEBUG: Using file match: (^|\/)\.bazelversion$ for manager bazelisk
DEBUG: Using file match: (^|/)\.?bitbucket-pipelines\.ya?ml$ for manager bitbucket-pipelines
DEBUG: Using file match: buildkite\.ya?ml for manager buildkite
DEBUG: Using file match: \.buildkite/.+\.ya?ml$ for manager buildkite
DEBUG: Using file match: (^|/)Gemfile$ for manager bundler
DEBUG: Using file match: \.cake$ for manager cake
DEBUG: Using file match: (^|/)Cargo\.toml$ for manager cargo
DEBUG: Using file match: (^|/)\.circleci/config\.yml$ for manager circleci
DEBUG: Using file match: (^|/)cloudbuild\.ya?ml for manager cloudbuild
DEBUG: Using file match: (^|/)Podfile$ for manager cocoapods
DEBUG: Using file match: (^|/)([\w-]*)composer\.json$ for manager composer
DEBUG: Using file match: (^|/)conanfile\.(txt|py)$ for manager conan
DEBUG: Using file match: (^|/)(?:deps|bb)\.edn$ for manager deps-edn
DEBUG: Using file match: (^|/)(?:docker-)?compose[^/]*\.ya?ml$ for manager docker-compose
DEBUG: Using file match: (^|/|\.)Dockerfile$ for manager dockerfile
DEBUG: Using file match: (^|/)Dockerfile[^/]*$ for manager dockerfile
DEBUG: Using file match: (^|/)\.drone\.yml$ for manager droneci
DEBUG: Using file match: (^|/)fleet\.ya?ml for manager fleet
DEBUG: Using file match: (^|\/)flux-system\/(?:.+\/)?gotk-components\.yaml$ for manager flux
DEBUG: Using file match: (^|\/)\.fvm\/fvm_config\.json$ for manager fvm
DEBUG: Using file match: (^|/)\.gitmodules$ for manager git-submodules
DEBUG: Using file match: ^(workflow-templates|\.github\/workflows)\/[^/]+\.ya?ml$ for manager github-actions
DEBUG: Using file match: (^|\/)action\.ya?ml$ for manager github-actions
DEBUG: Using file match: \.gitlab-ci\.yml$ for manager gitlabci
DEBUG: Using file match: \.gitlab-ci\.yml$ for manager gitlabci-include
DEBUG: Using file match: (^|/)go\.mod$ for manager gomod
DEBUG: Using file match: \.gradle(\.kts)?$ for manager gradle
DEBUG: Using file match: (^|\/)gradle\.properties$ for manager gradle
DEBUG: Using file match: (^|\/)gradle\/.+\.toml$ for manager gradle
DEBUG: Using file match: \.versions\.toml$ for manager gradle
DEBUG: Using file match: (^|/)gradle/wrapper/gradle-wrapper\.properties$ for manager gradle-wrapper
DEBUG: Using file match: (^|/)requirements\.yaml$ for manager helm-requirements
DEBUG: Using file match: (^|/)values\.yaml$ for manager helm-values
DEBUG: Using file match: (^|/)helmfile\.yaml$ for manager helmfile
DEBUG: Using file match: (^|/)Chart\.yaml$ for manager helmv3
DEBUG: Using file match: (^|/)bin/hermit$ for manager hermit
DEBUG: Using file match: ^Formula/[^/]+[.]rb$ for manager homebrew
DEBUG: Using file match: \.html?$ for manager html
DEBUG: Using file match: (^|/)plugins\.(txt|ya?ml)$ for manager jenkins
DEBUG: Using file match: (^|/)jsonnetfile\.json$ for manager jsonnet-bundler
DEBUG: Using file match: ^.+\.main\.kts$ for manager kotlin-script
DEBUG: Using file match: (^|/)kustomization\.ya?ml$ for manager kustomize
DEBUG: Using file match: (^|/)project\.clj$ for manager leiningen
DEBUG: Using file match: (^|/|\.)pom\.xml$ for manager maven
DEBUG: Using file match: ^(((\.mvn)|(\.m2))/)?settings\.xml$ for manager maven
DEBUG: Using file match: (^|/)package\.js$ for manager meteor
DEBUG: Using file match: (^|\/)Mintfile$ for manager mint
DEBUG: Using file match: (^|/)mix\.exs$ for manager mix
DEBUG: Using file match: (^|\/)flake\.nix$ for manager nix
DEBUG: Using file match: (^|/)\.node-version$ for manager nodenv
DEBUG: Using file match: (^|/)package\.json$ for manager npm
DEBUG: Using file match: \.(?:cs|fs|vb)proj$ for manager nuget
DEBUG: Using file match: \.(?:props|targets)$ for manager nuget
DEBUG: Using file match: (^|\/)dotnet-tools\.json$ for manager nuget
DEBUG: Using file match: (^|\/)global\.json$ for manager nuget
DEBUG: Using file match: (^|/)\.nvmrc$ for manager nvm
DEBUG: Using file match: (^|/)([\w-]*)requirements\.(txt|pip)$ for manager pip_requirements
DEBUG: Using file match: (^|/)setup\.py$ for manager pip_setup
DEBUG: Using file match: (^|/)Pipfile$ for manager pipenv
DEBUG: Using file match: (^|/)pyproject\.toml$ for manager poetry
DEBUG: Using file match: (^|/)\.pre-commit-config\.yaml$ for manager pre-commit
DEBUG: Using file match: (^|/)pubspec\.ya?ml$ for manager pub
DEBUG: Using file match: (^|\/)Puppetfile$ for manager puppet
DEBUG: Using file match: (^|/)\.python-version$ for manager pyenv
DEBUG: Using file match: (^|/)\.ruby-version$ for manager ruby-version
DEBUG: Using file match: \.sbt$ for manager sbt
DEBUG: Using file match: project/[^/]*.scala$ for manager sbt
DEBUG: Using file match: (^|/)setup\.cfg$ for manager setup-cfg
DEBUG: Using file match: (^|/)Package\.swift for manager swift
DEBUG: Using file match: \.tf$ for manager terraform
DEBUG: Using file match: (^|/)\.terraform-version$ for manager terraform-version
DEBUG: Using file match: (^|/)terragrunt\.hcl$ for manager terragrunt
DEBUG: Using file match: (^|/)\.terragrunt-version$ for manager terragrunt-version
DEBUG: Using file match: \.tflint\.hcl$ for manager tflint-plugin
DEBUG: Using file match: ^\.travis\.yml$ for manager travis
DEBUG: Using file match: (^|/)\.vela\.ya?ml$ for manager velaci
DEBUG: Using file match: (^|\/)\.woodpecker[^/]*\.ya?ml$ for manager woodpecker
DEBUG: Matched 2 file(s) for manager npm: grafana/hm-panel-plugin/package.json, web/package.json
DEBUG: Matched 2 file(s) for manager nvm: grafana/hm-panel-plugin/.nvmrc, web/.nvmrc
DEBUG: npm file grafana/hm-panel-plugin/package.json has name "hm-panel-plugin"
DEBUG: npm file web/package.json has name "hm-web"
DEBUG: Detecting pnpm Workspaces
DEBUG: Detecting Lerna and Yarn Workspaces
DEBUG: Finding locked versions
DEBUG: Found grafana/hm-panel-plugin/package-lock.json for grafana/hm-panel-plugin/package.json
DEBUG: Found web/package-lock.json for web/package.json
DEBUG: Found npm package files
DEBUG: Found nvm package files
DEBUG: Found 4 package file(s)
INFO: Dependency extraction complete
{
  "baseBranch": "main",
  "stats": {
    "managers": {
      "npm": {
        "fileCount": 2,
        "depCount": 6
      },
      "nvm": {
        "fileCount": 2,
        "depCount": 2
      }
    },
    "total": {
      "fileCount": 4,
      "depCount": 8
    }
  }
}
DEBUG: Setting npmrc
DEBUG: Using queue: host=registry.npmjs.org, concurrency=10
DEBUG: PackageFiles.add() - Package file saved for base branch
{
  "baseBranch": "main"
}
DEBUG: Package releases lookups complete
{
  "baseBranch": "main"
}
DEBUG: branchifyUpgrades
DEBUG: Using group branchName template
DEBUG: Dependency @tanstack/react-query is part of group tanstack-query monorepo
DEBUG: Using group branchName template
DEBUG: Dependency @tanstack/react-query is part of group tanstack-query monorepo
DEBUG: 8 flattened updates found: @tanstack/react-query, node, npm, @tanstack/react-query, npm, node
DEBUG: Returning 5 branch(es)
DEBUG: config.repoIsOnboarded=true
DEBUG: packageFiles with updates
{
  "baseBranch": "main",
  "config": {
    "npm": [
      {
        "packageFile": "grafana/hm-panel-plugin/package.json",
        "deps": [
          {
            "depType": "dependencies",
            "depName": "@tanstack/react-query",
            "currentValue": "4.14.6",
            "datasource": "npm",
            "prettyDepType": "dependency",
            "lockedVersion": "4.14.6",
            "depIndex": 0,
            "updates": [
              {
                "bucket": "non-major",
                "newVersion": "4.16.1",
                "newValue": "4.16.1",
                "releaseTimestamp": "2022-11-13T19:04:14.994Z",
                "newMajor": 4,
                "newMinor": 16,
                "updateType": "minor",
                "branchName": "renovate/tanstack-query-monorepo"
              }
            ],
            "warnings": [],
            "versioning": "npm",
            "sourceUrl": "https://github.com/tanstack/query",
            "homepage": "https://tanstack.com/query",
            "currentVersion": "4.14.6",
            "isSingleVersion": true,
            "fixedVersion": "4.14.6"
          },
          {
            "depType": "engines",
            "depName": "node",
            "currentValue": "16.x",
            "datasource": "github-tags",
            "packageName": "nodejs/node",
            "versioning": "node",
            "commitMessageTopic": "Node.js",
            "prettyDepType": "engine",
            "lockedVersion": null,
            "depIndex": 1,
            "updates": [
              {
                "bucket": "major",
                "newVersion": "v18.12.1",
                "newValue": "18.x",
                "releaseTimestamp": "2022-11-04T19:36:14.000Z",
                "newMajor": 18,
                "newMinor": 12,
                "updateType": "major",
                "isRange": true,
                "branchName": "renovate/node-18.x"
              }
            ],
            "warnings": [],
            "sourceUrl": "https://github.com/nodejs/node",
            "currentVersion": "v16.18.1",
            "isSingleVersion": false
          },
          {
            "depType": "engines",
            "depName": "npm",
            "currentValue": "8.x",
            "datasource": "npm",
            "commitMessageTopic": "npm",
            "prettyDepType": "engine",
            "lockedVersion": null,
            "depIndex": 2,
            "updates": [
              {
                "bucket": "major",
                "newVersion": "9.1.1",
                "newValue": "9.x",
                "releaseTimestamp": "2022-11-09T21:32:28.791Z",
                "newMajor": 9,
                "newMinor": 1,
                "updateType": "major",
                "isRange": true,
                "branchName": "renovate/npm-9.x"
              }
            ],
            "warnings": [],
            "versioning": "npm",
            "sourceUrl": "https://github.com/npm/cli",
            "homepage": "https://docs.npmjs.com/",
            "currentVersion": "8.19.3",
            "isSingleVersion": false
          }
        ],
        "packageJsonName": "hm-panel-plugin",
        "npmrc": "***********",
        "npmLock": "grafana/hm-panel-plugin/package-lock.json",
        "managerData": {
          "yarnZeroInstall": false,
          "hasPackageManager": false
        },
        "skipInstalls": true,
        "constraints": {
          "node": "16.x",
          "npm": "8.x"
        },
        "lockFiles": [
          "grafana/hm-panel-plugin/package-lock.json"
        ]
      },
      {
        "packageFile": "web/package.json",
        "deps": [
          {
            "depType": "dependencies",
            "depName": "@tanstack/react-query",
            "currentValue": "4.14.6",
            "datasource": "npm",
            "prettyDepType": "dependency",
            "lockedVersion": "4.14.6",
            "depIndex": 0,
            "updates": [
              {
                "bucket": "non-major",
                "newVersion": "4.16.1",
                "newValue": "4.16.1",
                "releaseTimestamp": "2022-11-13T19:04:14.994Z",
                "newMajor": 4,
                "newMinor": 16,
                "updateType": "minor",
                "branchName": "renovate/tanstack-query-monorepo"
              }
            ],
            "warnings": [],
            "versioning": "npm",
            "sourceUrl": "https://github.com/tanstack/query",
            "homepage": "https://tanstack.com/query",
            "currentVersion": "4.14.6",
            "isSingleVersion": true,
            "fixedVersion": "4.14.6"
          },
          {
            "depType": "engines",
            "depName": "node",
            "currentValue": "18.x",
            "datasource": "github-tags",
            "packageName": "nodejs/node",
            "versioning": "node",
            "commitMessageTopic": "Node.js",
            "prettyDepType": "engine",
            "lockedVersion": null,
            "depIndex": 1,
            "updates": [],
            "warnings": [],
            "sourceUrl": "https://github.com/nodejs/node",
            "currentVersion": "v18.12.1"
          },
          {
            "depType": "engines",
            "depName": "npm",
            "currentValue": "8.x",
            "datasource": "npm",
            "commitMessageTopic": "npm",
            "prettyDepType": "engine",
            "lockedVersion": null,
            "depIndex": 2,
            "updates": [
              {
                "bucket": "major",
                "newVersion": "9.1.1",
                "newValue": "9.x",
                "releaseTimestamp": "2022-11-09T21:32:28.791Z",
                "newMajor": 9,
                "newMinor": 1,
                "updateType": "major",
                "isRange": true,
                "branchName": "renovate/npm-9.x"
              }
            ],
            "warnings": [],
            "versioning": "npm",
            "sourceUrl": "https://github.com/npm/cli",
            "homepage": "https://docs.npmjs.com/",
            "currentVersion": "8.19.3",
            "isSingleVersion": false
          }
        ],
        "packageJsonName": "hm-web",
        "npmrc": "***********",
        "npmLock": "web/package-lock.json",
        "managerData": {
          "yarnZeroInstall": false,
          "hasPackageManager": false
        },
        "skipInstalls": true,
        "constraints": {
          "node": "18.x",
          "npm": "8.x"
        },
        "lockFiles": [
          "web/package-lock.json"
        ]
      }
    ],
    "nvm": [
      {
        "packageFile": "grafana/hm-panel-plugin/.nvmrc",
        "deps": [
          {
            "depName": "node",
            "currentValue": "16.18.1",
            "datasource": "github-tags",
            "packageName": "nodejs/node",
            "depIndex": 0,
            "updates": [
              {
                "bucket": "major",
                "newVersion": "v18.12.1",
                "newValue": "18.12.1",
                "releaseTimestamp": "2022-11-04T19:36:14.000Z",
                "newMajor": 18,
                "newMinor": 12,
                "updateType": "major",
                "branchName": "renovate/node-18.x"
              }
            ],
            "warnings": [],
            "versioning": "node",
            "sourceUrl": "https://github.com/nodejs/node",
            "currentVersion": "16.18.1",
            "isSingleVersion": true,
            "fixedVersion": "16.18.1"
          }
        ]
      },
      {
        "packageFile": "web/.nvmrc",
        "deps": [
          {
            "depName": "node",
            "currentValue": "18.12.1",
            "datasource": "github-tags",
            "packageName": "nodejs/node",
            "depIndex": 0,
            "updates": [],
            "warnings": [],
            "versioning": "node",
            "sourceUrl": "https://github.com/nodejs/node",
            "currentVersion": "18.12.1",
            "fixedVersion": "18.12.1"
          }
        ]
      }
    ]
  }
}
DEBUG: processRepo()
DEBUG: Processing 5 branches: renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json, renovate/lock-file-maintenance-web/package.json, renovate/node-18.x, renovate/npm-9.x, renovate/tanstack-query-monorepo
DEBUG: Calculating hourly PRs remaining
DEBUG: getPrList success
{
  "pullsTotal": 2,
  "requestsTotal": 1,
  "apiQuotaAffected": true
}
DEBUG: currentHourStart=2022-11-14T19:00:00.000+00:00
DEBUG: PR hourly limit remaining: 0
DEBUG: Calculating prConcurrentLimit (10)
DEBUG: getBranchPr(renovate/tanstack-query-monorepo)
DEBUG: findPr(renovate/tanstack-query-monorepo, undefined, open)
DEBUG: Found PR #1
DEBUG: getBranchPr(renovate/node-18.x)
DEBUG: findPr(renovate/node-18.x, undefined, open)
DEBUG: findPr(renovate/node-18.x, undefined, closed)
DEBUG: Found PR #2
DEBUG: getBranchPr(renovate/npm-9.x)
DEBUG: findPr(renovate/npm-9.x, undefined, open)
DEBUG: findPr(renovate/npm-9.x, undefined, closed)
DEBUG: getBranchPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json)
DEBUG: findPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json, undefined, open)
DEBUG: findPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json, undefined, closed)
DEBUG: getBranchPr(renovate/lock-file-maintenance-web/package.json)
DEBUG: findPr(renovate/lock-file-maintenance-web/package.json, undefined, open)
DEBUG: findPr(renovate/lock-file-maintenance-web/package.json, undefined, closed)
DEBUG: 1 PRs are currently open
DEBUG: PR concurrent limit remaining: 9
DEBUG: Calculated maximum PRs remaining this run: 0
DEBUG: PullRequests limit = 0
DEBUG: Calculating hourly PRs remaining
DEBUG: currentHourStart=2022-11-14T19:00:00.000+00:00
DEBUG: PR hourly limit remaining: 0
DEBUG: Calculating branchConcurrentLimit (10)
DEBUG: 2 already existing branches found: renovate/tanstack-query-monorepo,renovate/node-18.x
DEBUG: Branch concurrent limit remaining: 8
DEBUG: Calculated maximum branches remaining this run: 0
DEBUG: Branches limit = 0
DEBUG: syncBranchState()(branch="renovate/tanstack-query-monorepo")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/tanstack-query-monorepo")
DEBUG: branch.isUpToDate(): using cached result "true"(branch="renovate/tanstack-query-monorepo")
DEBUG: getBranchPr(renovate/tanstack-query-monorepo)(branch="renovate/tanstack-query-monorepo")
DEBUG: findPr(renovate/tanstack-query-monorepo, undefined, open)(branch="renovate/tanstack-query-monorepo")
DEBUG: Found PR #1(branch="renovate/tanstack-query-monorepo")
DEBUG: branchExists=true(branch="renovate/tanstack-query-monorepo")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/tanstack-query-monorepo")
DEBUG: PR rebase requested=false(branch="renovate/tanstack-query-monorepo")
DEBUG: Checking if PR has been edited(branch="renovate/tanstack-query-monorepo")
DEBUG: branch.isModified(): using cached result "false"(branch="renovate/tanstack-query-monorepo")
DEBUG: Found existing branch PR(branch="renovate/tanstack-query-monorepo")
DEBUG: Checking schedule(at any time, null)(branch="renovate/tanstack-query-monorepo")
DEBUG: No schedule defined(branch="renovate/tanstack-query-monorepo")
DEBUG: Branch already exists(branch="renovate/tanstack-query-monorepo")
DEBUG: getBranchPr(renovate/tanstack-query-monorepo)(branch="renovate/tanstack-query-monorepo")
DEBUG: findPr(renovate/tanstack-query-monorepo, undefined, open)(branch="renovate/tanstack-query-monorepo")
DEBUG: Found PR #1(branch="renovate/tanstack-query-monorepo")
DEBUG: GET https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/branches/main/protection = (code=ERR_NON_2XX_3XX_RESPONSE, statusCode=404 retryCount=0, duration=194)(branch="renovate/tanstack-query-monorepo")
DEBUG: No branch protection found(branch="renovate/tanstack-query-monorepo")
DEBUG: Skipping behind base branch check due to rebaseWhen=auto(branch="renovate/tanstack-query-monorepo")
DEBUG: isBranchConflicted(main, renovate/tanstack-query-monorepo)(branch="renovate/tanstack-query-monorepo")
DEBUG: branch.isConflicted(): using git to calculate(branch="renovate/tanstack-query-monorepo")
DEBUG: Setting git author name: Renovate Bot(branch="renovate/tanstack-query-monorepo")
DEBUG: Setting git author email: bot@renovateapp.com(branch="renovate/tanstack-query-monorepo")
DEBUG: branch.isConflicted(): false(branch="renovate/tanstack-query-monorepo")
DEBUG: Branch does not need rebasing(branch="renovate/tanstack-query-monorepo")
DEBUG: Using reuseExistingBranch: true(branch="renovate/tanstack-query-monorepo")
DEBUG: Checking if we can automerge branch(branch="renovate/tanstack-query-monorepo")
DEBUG: mergeStatus=no automerge(branch="renovate/tanstack-query-monorepo")
DEBUG: Ensuring PR(branch="renovate/tanstack-query-monorepo")
DEBUG: There are 0 errors and 0 warnings(branch="renovate/tanstack-query-monorepo")
DEBUG: getBranchPr(renovate/tanstack-query-monorepo)(branch="renovate/tanstack-query-monorepo")
DEBUG: findPr(renovate/tanstack-query-monorepo, undefined, open)(branch="renovate/tanstack-query-monorepo")
DEBUG: Found PR #1(branch="renovate/tanstack-query-monorepo")
DEBUG: Found existing PR(branch="renovate/tanstack-query-monorepo")
DEBUG: Fetching changelog: https://github.com/tanstack/query (4.14.6 -> 4.16.1)(branch="renovate/tanstack-query-monorepo")
DEBUG: Fetching changelog: https://github.com/tanstack/query (4.14.6 -> 4.16.1)(branch="renovate/tanstack-query-monorepo")
DEBUG: Processing existing PR(branch="renovate/tanstack-query-monorepo")
DEBUG: Pull Request #1 does not need updating(branch="renovate/tanstack-query-monorepo")
DEBUG: PR is not configured for automerge(branch="renovate/tanstack-query-monorepo")
DEBUG: syncBranchState()(branch="renovate/node-18.x")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/node-18.x")
DEBUG: branch.isUpToDate(): using cached result "true"(branch="renovate/node-18.x")
DEBUG: getBranchPr(renovate/node-18.x)(branch="renovate/node-18.x")
DEBUG: findPr(renovate/node-18.x, undefined, open)(branch="renovate/node-18.x")
DEBUG: findPr(renovate/node-18.x, undefined, closed)(branch="renovate/node-18.x")
DEBUG: Found PR #2(branch="renovate/node-18.x")
DEBUG: branchExists=true(branch="renovate/node-18.x")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/node-18.x")
DEBUG: recreateClosed is false(branch="renovate/node-18.x")
DEBUG: findPr(renovate/node-18.x, Update Node.js to v18, !open)(branch="renovate/node-18.x")
DEBUG: Found PR #2(branch="renovate/node-18.x")
DEBUG: Found closed PR with current title(branch="renovate/node-18.x")
DEBUG: Returning PR from cache(branch="renovate/node-18.x")
DEBUG: Closed PR already exists. Skipping branch.(branch="renovate/node-18.x")
{
  "prTitle": "Update Node.js to v18"
}
DEBUG: Getting comments for #2(branch="renovate/node-18.x")
DEBUG: Found 0 comments(branch="renovate/node-18.x")
DEBUG: Ensuring comment "Renovate Ignore Notification" in #2(branch="renovate/node-18.x")
INFO: Comment added(branch="renovate/node-18.x")
{
  "issueNo": 2,
  "topic": "Renovate Ignore Notification"
}
DEBUG: Git function thrown(branch="renovate/node-18.x")
{
  "err": {
    "task": {
      "commands": [
        "push",
        "--delete",
        "origin",
        "renovate/node-18.x"
      ],
      "format": "utf-8",
      "parser": "[function]"
    },
    "message": "error: unable to delete 'renovate/node-18.x': remote ref does not exist\nerror: failed to push some refs to 'https://github.com/Hongbo-Miao/bug-renovate-node-version.git'\n",
    "stack": "Error: error: unable to delete 'renovate/node-18.x': remote ref does not exist\nerror: failed to push some refs to 'https://github.com/Hongbo-Miao/bug-renovate-node-version.git'\n\n    at Object.action (/home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:1228:25)\n    at PluginStore.exec (/home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:1263:29)\n    at /home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:1627:43\n    at new Promise (<anonymous>)\n    at GitExecutorChain.handleTaskData (/home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:1625:16)\n    at GitExecutorChain.<anonymous> (/home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:1609:44)\n    at Generator.next (<anonymous>)\n    at fulfilled (/home/ubuntu/renovateapp/node_modules/simple-git/dist/cjs/index.js:55:24)\n    at runMicrotasks (<anonymous>)\n    at processTicksAndRejections (node:internal/process/task_queues:96:5)"
  }
}
DEBUG: No remote branch to delete with name: renovate/node-18.x(branch="renovate/node-18.x")
DEBUG: No local branch to delete with name: renovate/node-18.x(branch="renovate/node-18.x")
DEBUG: syncBranchState()(branch="renovate/npm-9.x")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/npm-9.x")
DEBUG: getBranchPr(renovate/npm-9.x)(branch="renovate/npm-9.x")
DEBUG: findPr(renovate/npm-9.x, undefined, open)(branch="renovate/npm-9.x")
DEBUG: findPr(renovate/npm-9.x, undefined, closed)(branch="renovate/npm-9.x")
DEBUG: branchExists=false(branch="renovate/npm-9.x")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/npm-9.x")
DEBUG: recreateClosed is false(branch="renovate/npm-9.x")
DEBUG: findPr(renovate/npm-9.x, Update npm to v9, !open)(branch="renovate/npm-9.x")
DEBUG: prAlreadyExisted=false(branch="renovate/npm-9.x")
DEBUG: Reached branch limit - skipping branch creation(branch="renovate/npm-9.x")
DEBUG: syncBranchState()(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: getBranchPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json)(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: findPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json, undefined, open)(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: findPr(renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json, undefined, closed)(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: branchExists=false(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: recreateClosed is true(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: Reached branch limit - skipping branch creation(branch="renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json")
DEBUG: syncBranchState()(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: syncBranchState(): update baseBranchSha(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: getBranchPr(renovate/lock-file-maintenance-web/package.json)(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: findPr(renovate/lock-file-maintenance-web/package.json, undefined, open)(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: findPr(renovate/lock-file-maintenance-web/package.json, undefined, closed)(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: branchExists=false(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: dependencyDashboardCheck=undefined(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: recreateClosed is true(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: Reached branch limit - skipping branch creation(branch="renovate/lock-file-maintenance-web/package.json")
DEBUG: getBranchPr(renovate/tanstack-query-monorepo)
DEBUG: findPr(renovate/tanstack-query-monorepo, undefined, open)
DEBUG: Found PR #1
DEBUG: branch.isBehindBase(): using git to calculate
DEBUG: branch.isBehindBase(): true
{
  "currentBranch": "main",
  "currentBranchSha": "e3643a20287fa3a865709ba0d00e3ae38123441e"
}
DEBUG: isBranchConflicted(main, renovate/tanstack-query-monorepo)
DEBUG: branch.isConflicted(): using cached result "false"
DEBUG: Ensuring Dependency Dashboard
DEBUG: ensureIssue(Dependency Dashboard)
DEBUG: Patching issue
DEBUG: Issue updated
DEBUG: Removing any stale branches
DEBUG: config.repoIsOnboarded=true
DEBUG: Branch lists
{
  "branchList": [
    "renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json",
    "renovate/lock-file-maintenance-web/package.json",
    "renovate/node-18.x",
    "renovate/npm-9.x",
    "renovate/tanstack-query-monorepo"
  ],
  "renovateBranches": [
    "renovate/tanstack-query-monorepo"
  ]
}
DEBUG: remainingBranches=
DEBUG: No branches to clean up
DEBUG: PackageFiles.clear() - Package files deleted
DEBUG: Branch summary
{
  "cacheModified": true,
  "baseBranches": [
    {
      "branchName": "main",
      "sha": "e3643a20287fa3a865709ba0d00e3ae38123441e"
    }
  ],
  "branches": [
    {
      "branchName": "renovate/tanstack-query-monorepo",
      "branchSha": "24a325580b15b3052136b4deb1108cce606a92fa",
      "baseBranch": "main",
      "baseBranchSha": "f830d5445305474418555fe087ae266169331b44",
      "automerge": false,
      "isModified": false
    }
  ],
  "inactiveBranches": [
    "renovate/node-18.x",
    "renovate/npm-9.x",
    "renovate/lock-file-maintenance-grafana/hm-panel-plugin/package.json",
    "renovate/lock-file-maintenance-web/package.json"
  ]
}
DEBUG: Renovate repository PR statistics
{
  "stats": {
    "total": 2,
    "open": 1,
    "closed": 1,
    "merged": 0
  }
}
DEBUG: Repository result: done, status: onboarded, enabled: true, onboarded: true
DEBUG: Repository timing splits (milliseconds)
{
  "splits": {
    "init": 2961,
    "extract": 3078,
    "lookup": 6517,
    "onboarding": 0,
    "update": 3534
  },
  "total": 17280
}
DEBUG: Package cache statistics
{
  "get": {
    "count": 8,
    "avgMs": 27,
    "medianMs": 1,
    "maxMs": 112
  },
  "set": {
    "count": 0
  }
}
DEBUG: http statistics
{
  "urls": {
    "https://api.github.com/graphql (POST,200)": 10,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/branches/main/protection (GET,404)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/contents/renovate.json5 (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/issues/2/comments (GET,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/issues/2/comments (POST,201)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/issues/3 (GET,200)": 2,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/issues/3 (PATCH,200)": 1,
    "https://api.github.com/repos/Hongbo-Miao/bug-renovate-node-version/pulls (GET,200)": 1,
    "https://api.github.com/repos/whitesource/merge-confidence/contents/beta.json (GET,200)": 1,
    "https://registry.npmjs.org/@tanstack%2Freact-query (GET,200)": 1
  },
  "hostStats": {
    "api.github.com": {
      "requestCount": 19,
      "requestAvgMs": 481,
      "queueAvgMs": 1
    },
    "registry.npmjs.org": {
      "requestCount": 1,
      "requestAvgMs": 773,
      "queueAvgMs": 1
    }
  },
  "totalRequests": 20
}
DEBUG: dns cache
{
  "hosts": [
    "api.github.com",
    "registry.npmjs.org"
  ]
}
INFO: Repository finished
{
  "cloned": true,
  "durationMs": 17280
}
  ```
</details>
