# [ci skip] workaround

```YAML
jobs:
  prepare:
    runs-on: ubuntu-latest
    if: "! contains(github.event.head_commit.message, '[ci skip]')"
    steps:
      - run: echo "${{ github.event.head_commit.message }}"

  build:
    runs-on: ubuntu-latest
    needs: prepare
    steps:
    - name: Check condition
      if: "! contains(github.event.head_commit.message, '[step skip]')"
      env:
        GITHUB_CONTEXT: ${{ toJson(github) }}
      run: |
        echo "$GITHUB_CONTEXT"
```

## if and needs

* [job.if](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idif)
  * [job.steps.if](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idstepsif)
* [job.needs](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idneeds)

Check the skip comment with prepare job and do [ci skip] by setting it to “needs: prepare”.

prepare job でスキップコメントをチェックし、prepare を needs にしておくことで [ci skip] を実現しています。

## Operator and Functions

* [Operators](https://help.github.com/en/articles/contexts-and-expression-syntax-for-github-actions#operators)
* [Functions](https://help.github.com/en/articles/contexts-and-expression-syntax-for-github-actions#functions)

> "! contains(github.event.head_commit.message, '[ci skip]')"

## github context

* [github context](https://help.github.com/en/articles/contexts-and-expression-syntax-for-github-actions#github-context)

The information that can be obtained from github context is not only the table of the above link.
It is what is included can be known by echo the context.

github context から取得できる情報は上記リンクの表だけではありません。
なにが含まれているかは context を echo することで知ることができます。

e.g.

```json
{
  "token": "***",
  "ref": "refs/heads/master",
  "sha": "d4f830561348462caa8f8466088bb921a718061c",
  "repository": "srz-zumix/ci-skip",
  "repositoryUrl": "git://github.com/srz-zumix/ci-skip.git",
  "actor": "srz-zumix",
  "workflow": "CI",
  "head_ref": "",
  "base_ref": "",
  "event_name": "push",
  "event": {
    "after": "d4f830561348462caa8f8466088bb921a718061c",
    "base_ref": null,
    "before": "70c5ef3ba47cc5edc5741ab67121d99f07cc448d",
    "commits": [
      {
        "added": [],
        "author": {
          "email": "[mail address]",
          "name": "srz_zumix",
          "username": "srz-zumix"
        },
        "committer": {
          "email": "noreply@github.com",
          "name": "GitHub",
          "username": "web-flow"
        },
        "distinct": true,
        "id": "d4f830561348462caa8f8466088bb921a718061c",
        "message": "fix [ci skip]",
        "modified": [
          ".github/workflows/main.yml"
        ],
        "removed": [],
        "timestamp": "2019-09-26T10:30:39+09:00",
        "tree_id": "f3fa584ac31aaecd08372b3ba89a4ba958e8a5ed",
        "url": "https://github.com/srz-zumix/ci-skip/commit/d4f830561348462caa8f8466088bb921a718061c"
      }
    ],
    "compare": "https://github.com/srz-zumix/ci-skip/compare/70c5ef3ba47c...d4f830561348",
    "created": false,
    "deleted": false,
    "forced": false,
    "head_commit": {
      "added": [],
      "author": {
        "email": "[mail address]",
        "name": "srz_zumix",
        "username": "srz-zumix"
      },
      "committer": {
        "email": "noreply@github.com",
        "name": "GitHub",
        "username": "web-flow"
      },
      "distinct": true,
      "id": "d4f830561348462caa8f8466088bb921a718061c",
      "message": "fix [ci skip]",
      "modified": [
        ".github/workflows/main.yml"
      ],
      "removed": [],
      "timestamp": "2019-09-26T10:30:39+09:00",
      "tree_id": "f3fa584ac31aaecd08372b3ba89a4ba958e8a5ed",
      "url": "https://github.com/srz-zumix/ci-skip/commit/d4f830561348462caa8f8466088bb921a718061c"
    },
    "pusher": {
      "email": "[mail address]",
      "name": "srz-zumix"
    },
    "ref": "refs/heads/master",
    "repository": {
      "archive_url": "https://api.github.com/repos/srz-zumix/ci-skip/{archive_format}{/ref}",
      "archived": false,
      "assignees_url": "https://api.github.com/repos/srz-zumix/ci-skip/assignees{/user}",
      "blobs_url": "https://api.github.com/repos/srz-zumix/ci-skip/git/blobs{/sha}",
      "branches_url": "https://api.github.com/repos/srz-zumix/ci-skip/branches{/branch}",
      "clone_url": "https://github.com/srz-zumix/ci-skip.git",
      "collaborators_url": "https://api.github.com/repos/srz-zumix/ci-skip/collaborators{/collaborator}",
      "comments_url": "https://api.github.com/repos/srz-zumix/ci-skip/comments{/number}",
      "commits_url": "https://api.github.com/repos/srz-zumix/ci-skip/commits{/sha}",
      "compare_url": "https://api.github.com/repos/srz-zumix/ci-skip/compare/{base}...{head}",
      "contents_url": "https://api.github.com/repos/srz-zumix/ci-skip/contents/{+path}",
      "contributors_url": "https://api.github.com/repos/srz-zumix/ci-skip/contributors",
      "created_at": 1519212106,
      "default_branch": "master",
      "deployments_url": "https://api.github.com/repos/srz-zumix/ci-skip/deployments",
      "description": "CI skip comment",
      "disabled": false,
      "downloads_url": "https://api.github.com/repos/srz-zumix/ci-skip/downloads",
      "events_url": "https://api.github.com/repos/srz-zumix/ci-skip/events",
      "fork": false,
      "forks": 1,
      "forks_count": 1,
      "forks_url": "https://api.github.com/repos/srz-zumix/ci-skip/forks",
      "full_name": "srz-zumix/ci-skip",
      "git_commits_url": "https://api.github.com/repos/srz-zumix/ci-skip/git/commits{/sha}",
      "git_refs_url": "https://api.github.com/repos/srz-zumix/ci-skip/git/refs{/sha}",
      "git_tags_url": "https://api.github.com/repos/srz-zumix/ci-skip/git/tags{/sha}",
      "git_url": "git://github.com/srz-zumix/ci-skip.git",
      "has_downloads": true,
      "has_issues": true,
      "has_pages": false,
      "has_projects": true,
      "has_wiki": true,
      "homepage": "https://github.com/srz-zumix/ci-specs",
      "hooks_url": "https://api.github.com/repos/srz-zumix/ci-skip/hooks",
      "html_url": "https://github.com/srz-zumix/ci-skip",
      "id": 122327168,
      "issue_comment_url": "https://api.github.com/repos/srz-zumix/ci-skip/issues/comments{/number}",
      "issue_events_url": "https://api.github.com/repos/srz-zumix/ci-skip/issues/events{/number}",
      "issues_url": "https://api.github.com/repos/srz-zumix/ci-skip/issues{/number}",
      "keys_url": "https://api.github.com/repos/srz-zumix/ci-skip/keys{/key_id}",
      "labels_url": "https://api.github.com/repos/srz-zumix/ci-skip/labels{/name}",
      "language": null,
      "languages_url": "https://api.github.com/repos/srz-zumix/ci-skip/languages",
      "license": {
        "key": "mit",
        "name": "MIT License",
        "node_id": "MDc6TGljZW5zZTEz",
        "spdx_id": "MIT",
        "url": "https://api.github.com/licenses/mit"
      },
      "master_branch": "master",
      "merges_url": "https://api.github.com/repos/srz-zumix/ci-skip/merges",
      "milestones_url": "https://api.github.com/repos/srz-zumix/ci-skip/milestones{/number}",
      "mirror_url": null,
      "name": "ci-skip",
      "node_id": "MDEwOlJlcG9zaXRvcnkxMjIzMjcxNjg=",
      "notifications_url": "https://api.github.com/repos/srz-zumix/ci-skip/notifications{?since,all,participating}",
      "open_issues": 2,
      "open_issues_count": 2,
      "owner": {
        "avatar_url": "https://avatars3.githubusercontent.com/u/1439172?v=4",
        "email": "[mail address]",
        "events_url": "https://api.github.com/users/srz-zumix/events{/privacy}",
        "followers_url": "https://api.github.com/users/srz-zumix/followers",
        "following_url": "https://api.github.com/users/srz-zumix/following{/other_user}",
        "gists_url": "https://api.github.com/users/srz-zumix/gists{/gist_id}",
        "gravatar_id": "",
        "html_url": "https://github.com/srz-zumix",
        "id": 1439172,
        "login": "srz-zumix",
        "name": "srz-zumix",
        "node_id": "MDQ6VXNlcjE0MzkxNzI=",
        "organizations_url": "https://api.github.com/users/srz-zumix/orgs",
        "received_events_url": "https://api.github.com/users/srz-zumix/received_events",
        "repos_url": "https://api.github.com/users/srz-zumix/repos",
        "site_admin": false,
        "starred_url": "https://api.github.com/users/srz-zumix/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/srz-zumix/subscriptions",
        "type": "User",
        "url": "https://api.github.com/users/srz-zumix"
      },
      "private": false,
      "pulls_url": "https://api.github.com/repos/srz-zumix/ci-skip/pulls{/number}",
      "pushed_at": 1569461440,
      "releases_url": "https://api.github.com/repos/srz-zumix/ci-skip/releases{/id}",
      "size": 103,
      "ssh_url": "git@github.com:srz-zumix/ci-skip.git",
      "stargazers": 2,
      "stargazers_count": 2,
      "stargazers_url": "https://api.github.com/repos/srz-zumix/ci-skip/stargazers",
      "statuses_url": "https://api.github.com/repos/srz-zumix/ci-skip/statuses/{sha}",
      "subscribers_url": "https://api.github.com/repos/srz-zumix/ci-skip/subscribers",
      "subscription_url": "https://api.github.com/repos/srz-zumix/ci-skip/subscription",
      "svn_url": "https://github.com/srz-zumix/ci-skip",
      "tags_url": "https://api.github.com/repos/srz-zumix/ci-skip/tags",
      "teams_url": "https://api.github.com/repos/srz-zumix/ci-skip/teams",
      "trees_url": "https://api.github.com/repos/srz-zumix/ci-skip/git/trees{/sha}",
      "updated_at": "2019-09-26T01:24:27Z",
      "url": "https://github.com/srz-zumix/ci-skip",
      "watchers": 2,
      "watchers_count": 2
    },
    "sender": {
      "avatar_url": "https://avatars3.githubusercontent.com/u/1439172?v=4",
      "events_url": "https://api.github.com/users/srz-zumix/events{/privacy}",
      "followers_url": "https://api.github.com/users/srz-zumix/followers",
      "following_url": "https://api.github.com/users/srz-zumix/following{/other_user}",
      "gists_url": "https://api.github.com/users/srz-zumix/gists{/gist_id}",
      "gravatar_id": "",
      "html_url": "https://github.com/srz-zumix",
      "id": 1439172,
      "login": "srz-zumix",
      "node_id": "MDQ6VXNlcjE0MzkxNzI=",
      "organizations_url": "https://api.github.com/users/srz-zumix/orgs",
      "received_events_url": "https://api.github.com/users/srz-zumix/received_events",
      "repos_url": "https://api.github.com/users/srz-zumix/repos",
      "site_admin": false,
      "starred_url": "https://api.github.com/users/srz-zumix/starred{/owner}{/repo}",
      "subscriptions_url": "https://api.github.com/users/srz-zumix/subscriptions",
      "type": "User",
      "url": "https://api.github.com/users/srz-zumix"
    }
  },
  "workspace": "/home/runner/work/ci-skip/ci-skip",
  "action": "run1",
  "event_path": "/home/runner/work/_temp/_github_workflow/event.json"
}
```
