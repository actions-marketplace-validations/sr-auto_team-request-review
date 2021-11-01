# Team-Request-Review-Action

## Usage

### Example Configuration

This belongs in `.github/team-request-review.yml`:

```
when:
  - label:
      nameIs: 
        - App1
    assign:
      teams:
        - ReviewTeam4
      individuals:
        - Reviewer3
  - author:
      nameIs: 
        - Author3
    assign:
      teams:
        - ReviewTeam3
      individuals:
        - Reviewer1
```

### Workflow Configuration

This belongs in `.github/workflows/team-request-review.yml`

```
name: 'Team Request Review Action'
on: pull_request

jobs:
  add-reviews:
    runs-on: ubuntu-latest
    steps:
      - uses: sr-caprx/team-request-review-action@[RELEASE]
        with:
          config: ".github/team-request-review.yml" # Config name
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}   # Github token
```
