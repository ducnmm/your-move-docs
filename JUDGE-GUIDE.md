# Your Move — installation and judging guide

## Installation status

[Install Your Move for Jira](https://developer.atlassian.com/console/install/9c641745-3a47-4ff3-b434-1f3a00e6f1a2?signature=AYABeLufAlPB7JlYyD0Opr0dfvwAAAADAAdhd3Mta21zAEthcm46YXdzOmttczp1cy13ZXN0LTI6NzA5NTg3ODM1MjQzOmtleS83MDVlZDY3MC1mNTdjLTQxYjUtOWY5Yi1lM2YyZGNjMTQ2ZTcAuAECAQB4CxqLTo9l4lqXuFjNim1xJM%2Bp%2F3TVP9xHS2BrU5DRRucBo6fG09DTRBAslqWkbgqO1gAAAH4wfAYJKoZIhvcNAQcGoG8wbQIBADBoBgkqhkiG9w0BBwEwHgYJYIZIAWUDBAEuMBEEDKQauWFKVdoQdm0pyAIBEIA7pj4FDCfB%2FhgHAvV0FOrYOHjGgx8Se%2BQdVjfbIiSdhcG44QgKvCeu5tR7LpcyfPsmqpGQbPX%2FQz%2B7HcgAB2F3cy1rbXMAS2Fybjphd3M6a21zOmV1LXdlc3QtMTo3MDk1ODc4MzUyNDM6a2V5LzQ2MzBjZTZiLTAwYzMtNGRlMi04NzdiLTYyN2UyMDYwZTVjYwC4AQICAHi9bVMAkme4qVQX1fQHo6ePw3H40A7cGfz7yrmSfBWMXgE3NJziQFFIJiL8EscJfgRmAAAAfjB8BgkqhkiG9w0BBwagbzBtAgEAMGgGCSqGSIb3DQEHATAeBglghkgBZQMEAS4wEQQMbAFKnpk4gN63PmvOAgEQgDsUUAUWX8LaOh8npj7WOMIkHa02iYBx5mBHjc4aZ4EqiafeBvj52Wto%2B35MHKh5OKDI%2FfKrr09%2BRTX6igAHYXdzLWttcwBLYXJuOmF3czprbXM6dXMtZWFzdC0xOjcwOTU4NzgzNTI0MzprZXkvNmMxMjBiYTAtNGNkNS00OTg1LWI4MmUtNDBhMDQ5NTJjYzU3ALgBAgIAeDYASx0XCjkny4iLV6vz%2BKtEGSGT6kdt0QRpkn6D%2FlVEAXNkRRYYoobBQQVo9XlJt7gAAAB%2BMHwGCSqGSIb3DQEHBqBvMG0CAQAwaAYJKoZIhvcNAQcBMB4GCWCGSAFlAwQBLjARBAxsPx3LzYpz%2FdoOTTgCARCAO6mdFaIw2HIg4s7bdUp1l8eFsYy%2BZWEqVRBypJhWUYVxJDSBHP9Kl17lLg%2BCpWCWBfJ5Cbuons9RSaI9AgAAAAAMAAAQAAAAAAAAAAAAAAAAADJb%2BvMnhF511UTdxrlXc1f%2F%2F%2F%2F%2FAAAAAQAAAAAAAAAAAAAAAQAAADJ6R3TUZE2ln0Wbo3mkzXwtH0wK9%2B2Xux6q7K9LafGP18XbUeoYmDNVhAgBb0uB7mneIeNVsbL4hA5vjQq5X9iOhLw%3D&product=jira)

Production **2.0.0** was deployed and installed on November 12, 2026. The production My court page loaded successfully on the existing test site. A separate clean-site installation has not been verified. Development and production store separate app data.

[Watch the 2:35 English demo](https://youtu.be/cnNutuTzSNE).

## Requirements

- A Jira Cloud site and an administrator who can install Forge apps.
- A software or business project with at least one issue the tester can view and edit.
- Two active, assignable Jira users for the complete handoff scenario. One user can test creation, history and lifecycle behavior.
- No AI provider, API key, external account or paid integration is required by Your Move. Optional email depends on the site's Jira notification channel.

## Install and configure

1. Open the release's installation link, choose the Jira site and install Your Move after reviewing its permissions.
2. Open an issue and choose **View app actions → Your Move**. If Jira offers a consent prompt, authorize the app with the current account.
3. In the project's issue layout, add the custom **Ball** field to Details, preferably beside Assignee. Jira configuration labels can differ between project types. If an older test installation is also present, use the field belonging to this release.
4. Open **Apps → Your Move** to access My court, Inbox and Notification settings.
5. Repeat authorization with the second tester. Both testers must be eligible for assignment on the issue.

The Ball field supports several holders. Its native people picker is edited inside the issue; Jira board cards do not offer an additional inline app-owned picker.

## Five-minute walkthrough

1. Keep the developer as Jira Assignee. In the issue’s **Your Move** panel, click **Add action** to create an action such as **Confirm the release acceptance criteria**, assign it to the second tester, and enter a short handoff context.
2. Add a second, independent action for the developer, such as **Prepare the release checklist**. Confirm both people appear in Ball while Assignee remains unchanged.
3. As the second tester, open My court. Confirm the **You received a Ball** announcement and the new Inbox item. Open its action; the unread count should decrease and the correct action should receive focus.
4. Click **Pick up**. Open **History** and verify the assignment and pickup events. Pass the action back with a note. Its title, context and history should remain intact; the other action should be unchanged.
5. In Jira, replace one Ball holder with one different person and confirm. Open actions held by the removed person transfer together; retained holders keep their work. Add or replace only one new person per edit.
6. Add a normal, unrestricted Jira comment with a structured @mention of the other tester. Expand Your Move and refresh Suggestions. Review the suggestion, choose one action, then cancel: nothing should move. Review again and explicitly confirm: only the selected action should move.
7. On a disposable issue, assign its first Assignee while Ball and action history are empty. Wait for event processing and verify one initial action. Set the issue to a status in the **Done category**. Open Balls should close and Ball should clear; Assignee and history remain. Reopening the issue does not silently recreate actions.

Background synchronization is asynchronous. My court Inbox checks on focus, when visible again, and every 30 seconds while visible. Use Refresh when testing immediately after another person's action.

## Optional email check

1. As the recipient, open Notification settings and explicitly turn email On. Old notifications are not sent retroactively.
2. If the recipient has an active Ball, **Send test email** queues a self-test. A queue acknowledgement is not proof of mailbox delivery.
3. Have the other tester make a new handoff to the opted-in recipient. Leave it unread until the delivery attempt, then verify the recipient's mailbox separately.
4. Email may be skipped for restricted or unknown issue security, unsupported projects, an inactive/ineligible recipient, a read notice, resolved work or a changed holder. Inbox remains the durable record.

## Permission and conflict checks

- Remove the recipient's access to a disposable test issue, then refresh My court and Inbox. The issue's actions and notifications must no longer be returned. Restore access after the test.
- Open the same Ball twice. Save a change in one view, then attempt a change using the stale view. The stale write should be rejected and ask for refresh.
- Do not perform access-revocation checks on essential project permissions or production work.

## Known limits

- Local demo users are simulated and do not prove Jira delivery.
- The current verified real-account evidence covers native-field handoff, recipient Inbox, opening the exact action, pickup and retained history. Distinct-account automatic email, real access revocation and simultaneous native/app edits still require verification.
- Ball choices are limited to active users eligible for Jira assignment. Lists are paginated; counts describe loaded accessible data.
- An action retains at most 200 ordinary history events. A final trusted Done closure can append one additional terminal event.
- No AI, Rovo agent, MCP server, Teamwork Graph integration, automatic reminders or realtime push is claimed.
