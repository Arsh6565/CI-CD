yaml
name: Animal Farm NodeJS CI
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repository
      uses: actions/checkout@v2
    - name: Use Node.js
      uses: actions/setup-node@v1
      with:
        node-version: '18.x'
    - name: Run Yarn 
      run: yarn
    - name: Run tests
      run: yarn test
