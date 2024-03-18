## Usage

```
name: Clean the working directory

on:
  push:
    branches-ignore:
      - [main, master]
jobs:
  build:
    runs-on: self-hosted
    steps:
      - uses: clean-workdir
```
