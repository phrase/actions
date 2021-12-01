# phrase/actions

Collection of common GitHub Actions for Phrase.

## lawa

License checks for Elixir, Ruby, JS.

### Example

Create `.github/workflows/lawa-elixir-ci.yml` in your repo.

```yml
name: CI
on: [ push ]

jobs:
  yarn-lawa-check:
    uses: phrase/actions/.github/workflows/lawa/yarn.yml@main
    with:
      node-version: 12.13.0
      decisions-file: license-decisions.yml
      yarn-cwd: ./assets
    secrets:
      github-token: ${{ secrets.GH_ACCESS_TOKEN }}
```
---

### Secrets (common for every stack)

##### `github-token`

**Required** Pass GitHub token. Needs access to repos and packages.

---

### Elixir

#### Inputs

##### `otp-version`

**Optional** OTP version, defaults to `24.1.7`.

##### `elixir-version`

**Optional** Elixir version, defaults to `1.12.3`.

##### `ruby-version`

**Optional** Ruby version for installing `lawa` gem, defaults to `2.7.3`.

##### `decisions-file`

**Optional** Path to decisions file, defaults to `license-decisions.yml`.

---

### Ruby

#### Inputs

##### `ruby-version`

**Optional** Ruby version for installing `lawa` gem and gems from `Gemfile` in the project, defaults to `2.7.3`.

##### `decisions-file`

**Optional** Path to decisions file, defaults to `license-decisions.yml`.

---

### JS

#### Inputs

##### `node-version`

**Optional** Node version. Defaults to `12.13.0`

##### `yarn-cwd`

**Optional** Path to folder with `package.json`. Defaults to `.`.

##### `ruby-version`

**Optional** Ruby version for installing `lawa` gem and gems from `Gemfile` in the project, defaults to `2.7.3`.

##### `decisions-file`

**Optional** Path to decisions file, defaults to `license-decisions.yml`.
