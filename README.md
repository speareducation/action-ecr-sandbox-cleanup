# action-ecr-sandbox-cleanup
Removes merged deployments from AWS ECR

Example:
```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0

      - uses: speareducation/action-ecr-sandbox-cleanup
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.myKeyId }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.myKeySecret }}
          AWS_REGION: us-east-1
        with:
          ecr-image: my-image
          ecr-domain: 000000000000.dkr.ecr.us-east-1.amazonaws.com
```

