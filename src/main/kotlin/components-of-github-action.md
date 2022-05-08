# Workflows
- Configurable automated process that executes one or more jobs
- Combination of events, jobs, actions and runners
- One project can have multiple workflows
    - One for build, one for test and one for deploy etc

# Events
- Activity that triggers workflow to run
- Activity can derive from GitHub (i.e., push, commit), or it can be from schedule(manual settings)
- <a href="https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#available-events" target="\_blank">All Available Events</a>

# Jobs
- Unit of work that contains what to execute and how to execute with order
- **Set of steps in workflow that execute on the same runner**
- Either a shell script or an action
- Each step **is executed in order, and are dependent of each other**
    - Build application first and test it after
- Jobs can depend on each other with configuration(default: no dependencies on each other)


# Actions
- **Custom application** for GitHub Actions platform that **performs a complex 
  but frequently repeated tasks**
- Can reduce repetitive code you write in workflow.yml
- Can write our own, or find actions in marketplace

# Runners
- Server that runs your workflow when event is triggered
- **One runner for one single job at a time**
- each workflow runs in a fresh, newly-provisioned VM
- Can have self-hosted runners

# Example of workflow.yml
```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

# What's Next
Go to [Essential Features of GitHub Action](essential-features.md)