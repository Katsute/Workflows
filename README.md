# Workflows

### 📄 All Workflows

#### OS

The operating system, accepts any [GitHub runner OS](https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources).

```yml
os:
    type: string
    default: ubuntu-latest
    required: false
    description: The operating system
```

#### Timeout

The workflow timeout in minutes.

```yml
timeout:
    type: number
    default: 30
    required: false
    description: Job timeout in minutes
```

### 📦 Artifact Workflows

Uses arguments from [actions/upload-artifact](https://github.com/actions/upload-artifact).

#### Artifact

The name of the artifact.

```yml
artifact-name:
    type: string
    default: artifact
    required: false
    description: Artifact name
```

The file or lines of files to save.

```yml
artifact-path:
    type: string
    required: true
    description: Artifact path
```

### 📥 Commit Workflows

#### Git Login

The commiter username.

```yml
git-name:
    type: string
    required: false
    default: github-actions[bot]
    description: The username to commit with
```

The commiter email.

```yml
git-email:
    type: string
    required: false
    default: github-actions[bot]@users.noreply.github.com
    description: The email to commit with
```

#### Files

The file or list of files to commit.

```yml
commit-files:
    type: string
    required: true
    description: The file or list of files to commit
```

##### Example inputs:

```yml
with:
  ...
  commit-files: "'cache'"
```

```yml
with:
  ...
  commit-files: "'cache', 'dist'"
```

#### Message

The commit message.

```yml
commit-message:
    type: string
    default: Commit files
    required: false
    description: Commit message
```

### ⌨ Command Workflows

The shell command to run.

```yml
command:
    type: string
    required: false
    description: Commands to run
```

### 🚀 Deployment Workflows

#### Environment

The GitHub environment name.

```yml
environment:
    type: string
    required: false
    description: GitHub environment
```

### ☕ Java Workflows

Only supports [Adoptium](https://adoptium.net/archive.html) versions.

#### CI Version

The Java version matrix, comma separated.

```yml
java-version:
    type: string
    default: 8, 11, 17
    required: false
    description: The Java version to use
```

#### Other Version

The Java version.

```yml
java-version:
    type: number
    default: 17
    required: false
    description: The Java version to use
```

#### Compile

Compiler arguments.

```yml
compile-args:
    type: string
    required: false
    description: Arguments for `mvn compile`
```

#### Package

Enable/disable the packaging job.

```yml
package:
    type: boolean
    default: false
    required: false
    description: Run `mvn package`
```

Packaging arguments.

```yml
package-args:
    type: string
    required: false
    description: Arguments for `mvn package`
```

#### CodeQL

Enable/disable the CodeQL job.

```yml
codeql:
    type: boolean
    default: true
    required: false
    description: Run CodeQL analysis
```

The Java version to use for CodeQL.

```yml
codeql-java-version:
    type: number
    default: 17
    required: false
    description: The Java version to use on CodeQL
```

#### Test

Enable/disable the test job.

```yml
test:
    type: boolean
    default: true
    description: Run `mvn test`
```

Testing arguments.

```yml
test-args:
    type: string
    required: false
    description: Arguments for `mvn test`
```

#### Exec

Java arguments.

```yml
exec-args:
    type: string
    required: false
    description: Arguments for `mvn exec`
```

### 🌐 Node Workflows

#### CI Version

The Node version matrix, comma separated.

```yml
node-version:
    type: string
    default: 14
    required: false
    description: The NodeJS version to use
```

#### Other Version

The Node version.

```yml
node-version:
    type: number
    default: 14
    required: false
    description: The NodeJS version to use
```

#### Rebuild

Enable/disable rebuild.

``` yml
rebuild:
    type: boolean
    default: false
    required: false
    description: Run `npm run rebuild`
```

#### CodeQL

Enable/disable the CodeQL job.

```yml
codeql:
    type: boolean
    default: true
    description: Run CodeQL analysis
```

The Node version to use for CodeQL.

```yml
codeql-node-version:
    type: number
    default: 14
    required: false
    description: The NodeJS version to use on CodeQL
```

#### Test

Enable/disable test job.

```yml
test:
    type: boolean
    default: true
    description: Run `npm test`
```