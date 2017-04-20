# seamless
seamless is a tool to easily setup continuous integration for Salesforce.com

## Setup

### Environment Variables
set your environment variables inside your CI tool:
```
CI_USERNAME (required)
CI_PASSWORD (required)
CI_SERVERURL (default="https://test.salesforce.com")
CI_MAXPOLL (default="600")
CI_POLLWAITMILLIS (default="3000")
CI_TESTLEVEL (default="RunLocalTests")
CI_CHECKONLY (default="true")
```

### Travis-CI
copy this into your .travis.yml:
```yaml
language: java
branches:
  only: 
    - master
script: 
  - git submodule add --force https://github.com/florianhoehn/seamless.git
  - ant -lib seamless/lib/ -f seamless/build.xml build
```

### CircleCI
copy this into your circle.yml:
```yaml
machine:
  java:
    version: oraclejdk8
test:
  override:
    - git submodule add --force https://github.com/florianhoehn/seamless.git
    - ant -lib seamless/lib/ -f seamless/build.xml build
```

## Contributing
Let's create issues and pull requests to enhance what seamless can do.

### Roadmap
- get more CI tools examples
- add to build.xml
