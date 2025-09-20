# Session Workflow Template

To create a new session workflow (e.g., Session 3), copy this template:

```yaml
name: Create Session X Branch
on:
  workflow_dispatch:

permissions:
  contents: write
  actions: write
  issues: write
  pull-requests: write

jobs:
  create_session:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout main branch
        uses: actions/checkout@v5
        with:
          fetch-depth: 0

      - name: Create Session X
        uses: ./.github/actions/create-session
        with:
          session_number: 'X'
          session_topic: 'Your Session Topic Here'
```

Replace:
- `X` with the session number (3, 4, 5, 6)
- `'Your Session Topic Here'` with the actual session topic
- Save as `.github/workflows/create-session-X.yml`

Then update the README.md table to include the new session button.
