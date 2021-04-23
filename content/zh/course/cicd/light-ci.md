# Lighthouse-ci

lighthouse-ci 工具持续用来获取Lighthouse结果的.
- [lighthouse-CI](https://github.com/GoogleChrome/lighthouse-ci)

## 如何操作

使用Github仓库，设置，```.github/workflows/ci.yml```

```sh
name: CI
on: [push]
jobs:
  lighthouseci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v1
      - run: npm install && npm install -g @lhci/cli@0.7.x
      - run: npm run build
      - run: lhci autorun
```

