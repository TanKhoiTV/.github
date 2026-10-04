# .github

The account's shared configuration repository.

Its one load-bearing file is `.github/workflows/ci.yml`, a reusable workflow
(`on: workflow_call`) that repositories generated from
[`repo-template`](https://github.com/TKhoi-labs/repo-template) call through their own thin
`ci.yml`. That caller records this workflow's **commit SHA**, so a change here reaches a
repository only when its `workflow_ref` answer is bumped.

The check it reports is `ci / ci` — the workflow is named `ci` and so is its job — which is the
name to require in branch protection.
