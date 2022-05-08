# Key Features
1. Able to use custom variables for each workflow run
```yaml
jobs:
  example-job:
      steps:
        - name: Connect to PostgreSQL
          run: node client.js
          env:
            # Custom variables
            POSTGRES_HOST: postgres
            POSTGRES_PORT: 5432
```

2. Run scripts or shell commands
```yaml
jobs:
  example-job:
    steps:
      - run: npm install -g bats
      - name: Run build script
        run: ./.github/scripts/build.sh
        shell: bash
```

# Sharing data between jobs
- **To share data between jobs, use of artifacts**
- Artifacts are the files created when building and testing code
    - Contains result of build & test of code

# Finding and Customizing actions