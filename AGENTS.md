<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- Global account controls live in SecurityProvider inside AccountProvider; one authenticated profile read drives the saved-name greeting and confirmed Cloud status.
- The security lock unmounts all app content, cancels and clears private query caches, and locally signs out; only successful account authentication restores access, not a local lock flag.
- Cloud's supported account authentication is used for unlock; do not simulate biometrics or treat browser credential creation as identity verification.
- Autonomous AI reviews run only from the cron-authenticated public job route, use server-only privileged snapshots, a durable daily lease, per-user quota and global pause, and write suggestions to Inbox only.
- Profile photos live in a private owner-folder bucket and are displayed via short-lived signed URLs; avatar choice is stored on the profile.
- The assistant chat streams from the authenticated `/api/chat` route with tools bound to the signed-in user's client (RLS-scoped), one persisted conversation, a daily request quota, and no money-moving tools.
- User-entered figures (income, budget, savings plan, body data) live on the profile and dashboard cards compute from them plus ledger rows; never hardcode figures.
