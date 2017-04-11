# seamless
seamless is a tool to create easily setup continuous integration for Salesforce.com

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
```

### Travis-CI
copy this into your .travis.yml:
```
language: java
branches:
  only: 
    - master
script: 
  - git submodule add --force https://github.com/florianhoehn/seamless.git
  - ant -lib seamless/lib/ -f seamless/build.xml validate
```

## Contributing
Let's create issues and pull requests to enhance what seamless can do.

### Roadmap
- get more CI tools examples
- add to build.xml