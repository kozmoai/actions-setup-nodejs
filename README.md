# actions-setup-nodejs
## Details
A Github Action that sets up a NodeJS environment, checks out the repository, and installs dependencies.

## Requirements
- [Checkout](https://github.com/actions/checkout) - to clone the repo

## Inputs
- N/A

## Usage
```yaml
name: Testing
on: [ pull_request ]
jobs:
  test_ts:
    name: Type Validation
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2
        with:
          persist-credentials: false

      - name: Setup
        id: setup
        uses: kozmoai/actions-setup-nodejs@main

      - name: Run tests
        run: npm run test
```