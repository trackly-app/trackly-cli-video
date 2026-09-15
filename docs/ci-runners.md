# Linux CI runners

Same-repository pull requests and non-PR events use the reviewed ephemeral
RunsOn pool: runs-on=trackly-fallback/runner=2cpu-linux-x64.
Fork pull requests retain their original GitHub-hosted Ubuntu runner.

Routing is literal: repository variables cannot select persistent runners or
production infrastructure. Returning to GitHub-hosted CI requires a reviewed
workflow change. There is no new token, variable, or cloud permission to install.
The RunsOn GitHub App must have access to this repository; a queued label alone
is not proof that a worker launched. Verify job logs and completion after merging.
