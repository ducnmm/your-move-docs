# Your Move — privacy and data handling

Last updated: November 12, 2026.

Your Move is a Jira Cloud app built on Atlassian Forge. This notice describes the current evaluation release and the data the application uses to provide explicit next actions, handoffs, history and notifications.

## Information the app uses

When authorized, the app reads the current Jira user's account ID and display name, issue identity, summary, status, assignee and project metadata, permissions and eligible assignees. Shared comment sources and structured mentions are read to support user-reviewed suggestions. The app excludes restricted, internal and threaded comments from shared-source suggestions.

## Information stored

In the Forge installation's app storage, Your Move stores account IDs and display names associated with action creators, holders and history actors; issue IDs; action titles and optional handoff context, due dates and notes; source comment identifiers and revision fingerprints; timestamps and audit history; notification delivery/read state; per-person email preferences; and lifecycle/idempotency metadata. The native Jira Ball field contains the distinct holders of open actions.

The app therefore stores personal data associated with Jira user references. Display names are retained in audit events as snapshots; changing a profile does not rewrite historical records.

Full source comment bodies are not copied into stored action records. People can enter their own text in action titles, context and notes; that text is visible to people who can view the corresponding issue.

## Purposes and access

The app uses this information to display the next action, preserve handoff history, keep Ball in sync with open actions, and show the intended recipient's Inbox. User-driven issue reads and mutations check the current Jira permissions. Background processing handles issue lifecycle, native-field changes and notification recovery with app-level authority.

Data is scoped to a Forge installation. The app does not provide a cross-customer directory or expose one installation's stored actions to another installation.

## Hosting and notifications

The application backend and stored action data run on Atlassian Forge. This release does not call an external AI provider, use an external analytics service, or send action content to an external inference service.

Email is optional and defaults to Off for each person. When enabled, the app requests targeted Jira notification email for eligible assignments. The supplied app email body is generic and links to My court; Jira's own template can include project and issue identity. Email delivery involves the site's Jira notification service and the recipient's configured mailbox provider.

## Retention and controls

Action and audit records are retained by the app; this release has no automatic age-based deletion job or dedicated end-user export/deletion screen. Resolving a Ball or completing an issue retains history. Uninstallation and platform retention are governed by Atlassian Forge's hosted-storage lifecycle; this notice does not promise immediate removal on uninstall.

A person can turn optional email off in Notification settings. Issue access remains controlled by Jira. For an installation's data-access or removal request, contact your Jira site administrator and the app maintainer through the support page below.

## Support

[Your Move support](https://github.com/ducnmm/your-move-docs/issues/new).

Support issues on that page are public. Describe the problem without posting private Jira issue contents, account identifiers, credentials or personal information. Coordinate any sensitive request through your site administrator.
