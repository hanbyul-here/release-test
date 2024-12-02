# release-test

## Pre
 
 Run this command before
 
 ```
 git push --set-upstream origin main
 export GITHUB_TOKEN=${YOUR_GITHUB_TOKEN}
 ```

##

### GitHub Action related

- Give write access to GITHUB_TOKEN

- Bypass Branch protection rule with deploy key: https://github.com/orgs/community/discussions/25305#discussioncomment-10728028
  - Create a deploy key with write permissions (GitHub asks when saving a deploy key)
  - Save the private SSH key in a DEPLOY_KEY secret
  - Add Deploy keys to the Bypass list of the rulesets (Bypass list > Add bypass > Deploy keys)
  - Make your action checkouts the repo using the SSH key from the secret

### GitHub App Related

Create GitHub App with  `contents: write, read`, `metadata: read` permissions
Install the app to the repos