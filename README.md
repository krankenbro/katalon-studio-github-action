# Katalon Studio action test

This action to run KS test and with your test cases source codes. 

## Inputs

### `your katalon command `

**Required** the katalon commands and test cases files 

## Outputs

### `status`

done

## Example usage
```yaml
on: [push]

jobs:
  katalon_test_job:
    runs-on: ubuntu-latest
    name: Run katalon Studio Test CLI
    steps:
    # To use this repository's private action, you must check out the repository
    - name: Checkout
      uses: actions/checkout@v1
    - uses: ./ # Uses an action in the root directory
    - name: Get and run action
      uses: katalon-studio/katalon-studio-github-action@master
      with:
        katalon_api: 'b279faef-0a5a-4aa5-8cff-ebc81466ac8c'
        Katalon-command: 'katalon-execute.sh -browserType="Chrome" -retry=0 -statusDelay=15 -testSuitePath="Test Suites/TS_RegressionTest"'
```