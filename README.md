# Seamless
Seamless is a tool to easily setup continuous integration for Salesforce.com. It's using Travis-CI, ApexMetrics and CodeClimate to create an easy and consistent workflow and quality assurance for your project.

All these tools are free for OpenSource projects.

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
COPY this into your .travis.yml:
```yaml
language: java
branches:
  only: 
    - master
script: 
  - git submodule add --force https://github.com/florianhoehn/seamless.git
  - ant -lib seamless/lib/ -f seamless/build.xml build
```

### CodeClimate's ApexMetrics
COPY this into your .codeclimate.yml to use ApexMetric
```yaml
engines:
 apexmetrics:
    enabled: true
ratings:
  paths:
    - "**.cls"
    - "**.trigger"
```

## Contributing
Let's create issues and pull requests to enhance what seamless can do.