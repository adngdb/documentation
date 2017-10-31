# Sign-offs for Firefox desktop and Firefox for Android

<!-- toc -->

Sign-offs are a way for l10n-drivers to specify that a specific changeset is technically sound and ready to ship in Firefox for desktop or Android. Currenty, thanks to cross-channel, we ship all versions of Firefox from a [single localization repository](https://hg.mozilla.org/l10n-central/), but sign-offs only happen for the Beta channel:
* Nightly builds always use the tip of the repository, using the latest changes available.
* Beta builds only use the signed off version.
* Release builds uses the latest signed off version from Beta, and can’t normally be updated.

Sign-offs are tied to a specific app version. For example, Firefox 57 starts in Nightly and doesn’t get any sign-off, it then moves to Beta and get multiple sign-offs as the localization progresses. It then moves to release, and any dot release (e.g. 57.0.1) will use the latest sign-off available for the 57 version (done when it was still in Beta).

Note that sign-offs on Beta are not possible through the entire cycle: sign-offs deadline is normally on Wednesday, 2 weeks before the release, to allow time for at least one more Beta build before the end of the cycle.

Sign-offs are performed on l10n.mozilla.org (elmo) [in this page](https://l10n.mozilla.org/shipping/dashboard?tree=fennec_beta&tree=fx_beta).

## How to perform sign-offs

![Sign-offs table repository](/assets/images/signoffs/signoffs_table.png)

[This page](https://l10n.mozilla.org/shipping/dashboard?tree=fennec_beta&tree=fx_beta) only includes sign-offs for Firefox desktop and Firefox for Android beta.
A green checkmark in the status column indicates that the locale has a sign-off for this version, and doesn’t have any following activity to check.
A prohibited signal indicates that there is no activity after the last sign-off (belonging to a previous version), and therefore it’s not possible to do a sign-off at the moment.
A sparkline sign indicates activity that should be checked:
* Orange means that the product is still incomplete.
* Green indicates that the translation is complete (no error, no missing strings).
* Red means that there are errors in the localization. Errors and warnings are also reported within the table.

The lack of icons in the Status column means that there is no sign-off for this locale. This typically happens for brand new locales that are only shipping in Nightly.

To perform the sign-off, click on the sparkline icon. It will open a new page, showing information about the last sign-off, and the changesets that follows it.

![List of changesets](/assets/images/signoffs/changesets_table.png)

For each changeset, it’s possible to check the results from `compare-locale` by clicking on the link with the number of missing strings. Errors and warnings are reported in the link too.

By clicking the top gray circle on the rightmost column, you can display a diff between the latest changeset and the latest sign-off. Note that both circles can be dragged, to display the diff between specific changesets. It's also possible to load more changeset at the bottom of the table.

![Diff view](/assets/images/signoffs/diff_view.png)

In diff view, green means that content has been added, red it's been removed, while orange indicates a change. Each level of the diff can be collapsed simply by clicking on the same line as the file or folder name.

Once you have reviewed the diff, you can return to the previous page, and sign-off the changeset by clicking the *sign off…* button. To accept the sign-off, simply:

![Requesting and accepting a sign-off](/assets/images/signoffs/accept_signoff.png)

To explicitly reject a sign-off, unselect the *Sign off and accept* checkbox. Then click on *Review…* and reject the sign-off with a reason.

![Rejecting a sign-off](/assets/images/signoffs/reject_signoff.png)

## Things to check when doing a sign-off
