# Release verification — November 12, 2026

This is a bounded engineering verification with real Jira accounts, not a security certification or a guarantee of every possible distributed interleaving.

## Automatic recipient email — passed

On production, Henry enabled email notifications before Duc created an action for Henry on the disposable `[TEST] Production release verification` issue SCRUM-7. The recipient's actual mailbox received `[JIRA] [Your Move] A Ball is waiting for you` at 11:07 Vietnam time. Its issue reference was SCRUM-7 and its HTML contained the production My court URL. This was automatic delivery from a new action, not the Send test email control. Henry's Inbox also contained the matching action. Mailbox evidence remains local and is excluded from source publication.

## Access revocation and restoration — passed

Before restriction, Henry could see the SCRUM-7 action and unread notice. Duc restricted that disposable issue to the Administrator role. After Henry refreshed, My court returned zero actions and Inbox returned no notifications for the issue. Removing the restriction restored the notice and exact-action access. No project-wide or account-wide permissions were removed.

## Clean-site installation — passed

With explicit user approval of Atlassian's seven-day free Standard trial and Terms, created `yourmove-qa-ducnmm.atlassian.net`. No payment step was completed. The signed public judge installer displayed **Installation successful** for this site. My court loaded with zero existing actions, demonstrating a separate installation store.

Configured the app-provided Ball field through Space settings → Fields → Add field, then added it to the Feature layout's Context fields. Assigning the untouched sample SCRUM-1 to Duc initialized its first action and native Ball value. Moving the issue to Done closed the action, cleared Ball and retained the initialization and terminal history. The public judge guide now describes the global-field setup step before action creation.

## Conflicting edits — findings and fixes

A real stale handoff after another person's native-field change caused the production UI to become blank. Chrome recorded React error #130. The backend retained the action; this was a failure to render error feedback. A new browser regression passed against the development server but reproduced the crash in an optimized bundle. Atlaskit's generated CommonJS icon entry points exposed an object under Vite 8's changed default-import interpretation. Enabled Vite's documented compatibility option and retained production-bundle regression coverage in CI. This compatibility option is deprecated upstream and should be revisited when Atlaskit supports the newer interop behavior.

Production also retained one module-global Jira field ID. Field IDs differ between installations (the existing site uses customfield_10047; the new site uses customfield_10044). Removed that shared cache and added tests that rotate sites/environments and recover after administrator field setup. Each discovery now uses the current invocation's Jira connection and exact app/environment schema.

A near-overlapping native selection and app handoff was exercised with Duc and Henry on SCRUM-7; the app handoff committed, and both native field and stored action converged on Duc. Native events remain asynchronous. This bounded case does not establish atomicity between Jira and Forge storage.

After deployment, a held Duc handoff was submitted after Henry’s native edit had already transferred the stored action and appended history. Production displayed “This ball changed. Refresh and try again.” in the intact dialog and page. Cancelling and reloading remained functional. This was checked separately from the near-overlap case.

## Automated validation

- 135 unit tests.
- 17 development browser flows.
- 7 optimized-bundle browser flows, including stale handoff error rendering and selected source-comment rendering.
- Production build, offline manifest validation, Forge lint and formatting checks.

Two development fixture files rewrite individual served source modules; they remain in the full development suite and are excluded from optimized-bundle runs where that interception does not apply. The production suite exercises the remaining flows plus the new regression cases.

## Remaining limits

Cross-system writes are not an atomic Jira/Forge transaction. The per-issue native-event queue and stored-action versions do not prove all native/app interleavings. Notification recovery throughput, dependency advisories, history limits and lack of realtime push remain documented in the architecture review and judge guide.

## Cleanup

The old site’s disposable SCRUM-7 and the new site’s sample SCRUM-1 were moved to Done. Their history was retained. The issue access restriction was removed, and Henry’s production email preference was returned to its original Off setting after testing. Development demonstration data was not deleted.
