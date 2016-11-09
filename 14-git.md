# Git

## Branches
* Each story **MUST** live in it's own branch.

* Branch name **SHOULD** be a story number preceded by `issues/` without any additional description.
  * Correct: `issues/PRJ-123`
  * Incorrect: `my-feature`, `PRJ-123`, `issues/PRJ-123-my-feature`

## Comments
* Each comment **SHOULD** start with an issue number(s) inside square braces `[` and `]` followed by a sentence starting with a verb in past tense and properly terminated.
  * Correct:
    * `[PRJ-123] Verb in the past tense ending with a dot at the end.`
    * `[PRJ, PRJ-123] Verb in the past tense ending with a dot at the end.`
    * `[PRJ-321, PRJ-123] Verb in the past tense ending with a dot at the end.`
    * `[PRJ] Verb in the past tense ending with a dot at the end.`
    * `Verb in the past tense ending with a dot at the end.`
    * `Verb in the past tense ending with a dot at the end. Another sentence with a dot.`
  * Incorrect:
    * `Adding a feature`
    * `some stuff`
    * `PRJ-123 Adding a feature`
    * `[prj-123] Adding a feature`

* It is highly advised to use a git `commit-msg` hook to automatically validate the format of commits. Use [https://github.com/alexdesignworks/git-hooks](https://github.com/alexdesignworks/git-hooks) to instal such hook implementation (a 1-liner command ran from your project git repo).

## Cleanup
Each developer is expected to cleanup own branches in `remote` repository as soon as they merged to main development branch.

**Remove not fully merged local branches:**

````
git branch --merged master | egrep -v "master|releases|release|hotfix|project|develop|ci" | xargs git branch -d
```

**Remove not fully merged remote branches:**

```
git branch -r --merged | egrep -v "master|releases|release|hotfix|project|develop|ci" | sed 's/origin\///'|xargs -n 1 git push --delete origin
```

{% include "./footer.md" %}
