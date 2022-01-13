# phrase/actions

Collection of common GitHub Actions for Phrase.

## lawa

License checks for Elixir, Ruby, JS.

### Setup

Create `.github/workflows/lawa-(js|ruby|elixir)-ci.yml` in your repo.

Example:

```yml
name: CI
on: [ push ]

jobs:
  lawa-ruby-ci:
    uses: phrase/actions/.github/workflows/lawa-ruby-ci.yml@main
    with:
      decisions-file: license-decisions.yml
    secrets:
      github-token: ${{ secrets.GH_ACCESS_TOKEN }}
```

Create `license-decisions.yml` in your repo.

Example:

```yml
---
- - :inherit_from
  - url: https://raw.githubusercontent.com/phrase/lawa/master/config/license-decisions.yml
    authorization: token $GITHUB_TOKEN

```

---

### Secrets (common for every stack)

##### `github-token`

**Required** Pass GitHub token. Needs access to repos and packages.

---

### Elixir

#### Inputs

##### `otp-version`

**Optional** OTP version, defaults to `24.2`.

##### `elixir-version`

**Optional** Elixir version, defaults to `1.13.1`.

##### `ruby-version`

**Optional** Ruby version for installing `lawa` gem, defaults to `3.0.3`.

##### `ruby-bundler-version`

**Optional** Ruby bundler version for installing `lawa` gem, defaults to `2.1.4`.

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
