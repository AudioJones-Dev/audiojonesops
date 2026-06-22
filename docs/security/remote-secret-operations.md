# Remote Secret Operations Doctrine

| Field | Value |
|---|---|
| **Owner** | AJ Digital LLC / Audio Jones |
| **Status** | Required control |
| **Scope** | Remote agent, chat, repo, deployment, and integration setup workflows |
| **Canonical home** | `audiojonesops/docs/security/remote-secret-operations.md` |

## Problem

Remote AI and automation sessions sometimes need temporary secret values to finish setup work. That creates an immediate exposure risk because chat transcripts, logs, generated files, shell history, tests, PR bodies, and documentation can accidentally become secondary storage for secrets.

The operating rule is simple: agents may help configure secrets, but they must not become a secret store.

## Desired outcome

AJ Digital can complete remote setup work through approved secret managers without committing, logging, documenting, or preserving secret values in repo artifacts.

Any secret pasted into a remote chat is treated as exposed immediately, even if it was never committed.

## Success criteria

- Secret values are loaded only through Doppler CLI or another explicitly approved secret manager.
- Secret values are never written to repo files, docs, tests, examples, PR bodies, comments, logs, or screenshots.
- Pasted secrets are rotated immediately after the operational gate is complete.
- Verification includes repo grep, git diff review, and generated-doc review.
- The old value is confirmed dead when the provider supports verification.

## Scope

This doctrine applies to:

- Slack app tokens and signing secrets.
- GitHub tokens and app secrets.
- API keys for providers, model vendors, automation tools, payment tools, and deployment platforms.
- Temporary credentials pasted into ChatGPT, Codex, Claude, Copilot, or other remote agent sessions.
- Any agent-assisted setup where a secret crosses a chat, shell, browser, or repository boundary.

## Out of scope

- Public configuration values that are not secrets.
- Local-only secrets that never enter chat, logs, docs, commits, or remote tooling.
- Provider-side rotation mechanics, except where required to confirm an old value no longer works.

## Allowed

- The user may paste a temporary secret value into a private agent/chat session only to unblock a current configuration task.
- The agent may load the secret into Doppler CLI or another approved secret manager.
- The agent may verify that the application receives the secret from the approved secret manager at runtime.
- The agent may report that a secret was set, rotated, or verified, but must never repeat the value.

## Prohibited

Agents must never write secret values to:

- Source files.
- Markdown docs.
- `.env` examples.
- Tests or fixtures.
- Generated notes.
- PR bodies or comments.
- Commit messages.
- Shell scripts.
- Terminal logs.
- Screenshots.
- Chat summaries.

Agents must not echo secret values back to the user.

Agents must not preserve secret-bearing files as "temporary" repo artifacts.

Agents must not reintroduce Firebase or any deferred integration secret path without explicit approval.

## Required sequence

1. Receive the secret only for the current operational task.
2. Load the secret through Doppler CLI or another approved secret manager.
3. Verify the app, gate, worker, or integration uses the secret from the secret manager.
4. Rotate the secret through Doppler CLI or the provider console as soon as the setup gate is complete.
5. Confirm the old value no longer works when the provider exposes a safe verification path.
6. Confirm no committed or generated artifact contains the value.

## Verification checklist

Before claiming the secret operation is complete, run or document the equivalent of:

```powershell
git status -sb
git diff --check
git diff
rg "<known-secret-fragment>" .
```

Use the smallest safe search fragment that can prove absence without printing the full secret. If searching for the literal value would expose it in logs, use provider metadata, token prefix only, or a local non-logged verification method instead.

Also inspect:

- Generated docs.
- Generated session notes.
- PR body.
- Commit messages.
- Runtime logs touched during setup.

## Hard rule

**A pasted secret is treated as exposed the moment it enters chat, even if it is never committed.**

Rotation is not optional after a pasted-secret setup flow.

## Agent behavior

When a user pastes or offers a secret, the agent must:

- State that the value is now considered exposed.
- Use it only for the approved operational task.
- Avoid printing or restating it.
- Move it into the approved secret manager.
- Prompt for or perform rotation as soon as the setup gate is complete.
- Verify repo artifacts and logs before closing the task.

When the task can be completed without pasting the secret, the agent should prefer:

- Local provider login.
- Browser/provider console entry by the user.
- Doppler CLI commands that do not expose the value in command history.
- Secret-manager UI flows.

## Canonical references

Repos and runbooks may link to this doctrine instead of duplicating it. If a local repo needs a project-specific control, it should add a short reference such as:

> This project follows AJ Digital Remote Secret Operations Doctrine. Live worker, Slack, GitHub, Doppler, and provider-token setup must use Doppler or an approved secret manager. Pasted values require immediate rotation and repo artifact verification.

