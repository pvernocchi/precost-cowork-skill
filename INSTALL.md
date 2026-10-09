# Install a Copilot Cowork skill from a ZIP file

This guide explains how to install a custom skill in Microsoft Copilot Cowork
from a `.zip` file. It also covers the archive structure Cowork expects,
verification, updates, removal, and common upload errors.

> [!IMPORTANT]
> A skill contains instructions that Cowork can follow and may tell Cowork to
> use tools or access data available to you. Install skills only from sources
> you trust, and review `SKILL.md` and any companion files before uploading
> them.

## 1. Download the skill

For the `/precost` skill in this repository:

1. Open the
   [latest release](https://github.com/pvernocchi/precost-cowork-skill/releases/latest).
2. Under **Assets**, download `precost.zip`.
3. Do not use GitHub's automatically generated **Source code (zip)** archive.
   It includes repository-level files and extra folder nesting that are not
   part of the installable skill.
4. If the release publishes a checksum, compare it with the downloaded file
   before installing.

Keep the original download until you have confirmed that the skill works.

## 2. Upload the ZIP to Cowork

1. Open **Copilot Cowork**.
2. In the left navigation, select **Customize**.
3. Select the **Skills** tab.
4. Select the arrow next to **Add**.
5. Select **Upload skill**.
6. In the file picker, select the downloaded ZIP file.
7. Confirm the upload if Cowork displays the trusted-source reminder.
8. Wait while Cowork validates the archive and saves it to OneDrive.

After synchronization finishes, the skill appears under **Your skills**. This
can take a few moments.

## 3. Verify the installation

1. On **Customize** > **Skills**, find the skill under **Your skills**.
2. Open the skill and confirm that its name and description are correct.
3. Start a **new Cowork conversation** so Cowork loads the newly installed
   skill.
4. Invoke the skill by its command or by a request that matches its
   description.

For this repository, type:

```text
/precost
```

You can also try a matching request such as:

```text
Estimate the cost and value of this task before starting it.
```

The installation is successful when Cowork recognizes the skill and follows
its workflow. If Cowork does not recognize it in an existing conversation,
start another new conversation before troubleshooting the package.

# Updating an installed skill

Uploading another skill with the same `name` does not overwrite the existing
copy. Cowork keeps both and adds a number to the new skill's name.

To avoid duplicate or ambiguous skills:

1. Download and inspect the new version.
2. Open **Customize** > **Skills**.
3. Open the old skill and delete it.
4. Upload the new ZIP by following the steps above.
5. Start a new conversation and test the updated skill.

If you need to preserve the old version temporarily, upload the new version,
test it in a new conversation, and then delete the old one. Check the displayed
name carefully because Cowork may append a number.

# Removing a skill

1. Open **Cowork** > **Customize** > **Skills**.
2. Select the skill under **Your skills**.
3. Open its detail page.
4. Select **Delete** and confirm the action.
5. Start a new conversation to confirm that the skill is no longer available.

Use Cowork's delete action instead of manually deleting the backing files from
OneDrive.

# Troubleshooting

## Cowork says the archive is invalid

Check that:

- The file extension is `.zip` or `.skill`.
- `SKILL.md` is at the archive root, not inside another folder.
- `SKILL.md` includes valid YAML frontmatter delimited by `---`.
- The frontmatter contains both `name` and `description`.
- The ZIP opens normally and is not corrupted or password-protected.
- The archive stays within the 10 MB compressed, 50 MB uncompressed, and
  100-file limits.

Rebuild the ZIP from the skill folder's contents if necessary.

## The skill uploads but does not work correctly

- Confirm that all files referenced by `SKILL.md` are included at the same
  relative paths used by the instructions.
- Preserve directory names and letter casing.
- Start a new conversation after installing or editing the skill.
- Invoke the skill explicitly once, such as `/precost`, to test discovery.
- Open the skill's detail page and confirm that the expected instructions were
  imported.

## The skill does not appear under Your skills

- Wait a few moments for OneDrive synchronization, then refresh Cowork.
- Confirm that the upload completed without a validation error.
- Verify that OneDrive is available and signed in with the same work or school
  account used in Cowork.
- Sign out and back in only after checking for an active Microsoft 365 service
  incident.

## Upload skill is unavailable

The feature may be disabled, restricted by organizational policy, or not yet
available for your account. Ask your Microsoft 365 administrator to confirm:

- Your Copilot Cowork entitlement
- Whether custom skill uploads are permitted
- Whether OneDrive is enabled
- Whether the Cowork customization features have been deployed to your tenant

## A duplicate skill appears

Cowork keeps both copies when their frontmatter uses the same `name`. Delete
the unwanted copy from its detail page, then start a new conversation.

# Supported file types

Cowork can import:

- A `.md` file containing one self-contained `SKILL.md`, up to **1 MB**
- A `.zip` or `.skill` archive with `SKILL.md` at its root and any companion
  files, subject to the archive limits above

A ZIP is the appropriate format when the skill uses reference documents,
scripts, templates, or other companion files.

# Official documentation

For the current Cowork interface and limits, see
[Customize Copilot Cowork](https://learn.microsoft.com/en-us/microsoft-365/copilot/cowork/cowork-customize#upload-a-skill).
Microsoft can change product availability, interface labels, and limits, so
check the official documentation if the screens differ from this guide.