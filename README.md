# generate_tags_from_github

githubの情報を元に正規表現を利用してgaugeで実行するためのtagを生成する

## Composite Action

```yaml
- name: Run custom action
  id: run-action
  uses: Pianoopera/generate_tags_from_github@main
  with:
    # featureを含んだブランチ名を指定
    github_branch: feature/branch

- name: Outputs
  # outputs.tagsに値を格納
  run: ${{ steps.run-action.outputs.tags != 'branch' }}
```

## Develop

[act](https://github.com/nektos/act)でローカル環境でもActionsを実行可能

```shell
act pull_request
```