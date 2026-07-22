Question 5: vi Recovery Mechanisms
Swap Files

While editing a file, vi or Vim creates a temporary swap file.

The swap file stores information about the editing session and can preserve unsaved changes.

If the editor or system crashes, Vim can detect the swap file when the file is opened again and offer a recovery option.

In this experiment, the swap file successfully recovered the unsaved change:

backup_enabled=true
Undo History

Undo history allows recent changes to be reversed during an editing session.

It is useful for recovering from accidental changes while Vim is still running.

However, undo history may not always be sufficient after a complete system crash unless the relevant undo information has been saved.

Registers

Registers temporarily store copied or deleted text.

They can be used to restore text that was accidentally deleted or to paste previously copied content.

Registers are mainly useful during an active editing session.

Backup Files

Backup files contain an earlier saved version of a file.

They can be used to restore the previous version if the main file becomes corrupted or damaged.

However, a normal backup file may not contain the latest unsaved changes.

Auto-Recovery

Auto-recovery uses temporary recovery information to restore unsaved changes after an unexpected termination.

This is closely related to swap-file recovery and is particularly useful after a crash.

Most Reliable Recovery Strategy

The most reliable recovery strategy after a crash is to first check for a Vim swap file and use the recovery option.

The swap file is specifically designed to preserve information from an editing session that may not have been written to the original file.

After recovering the file, the contents should be carefully checked before saving.

The old swap file should then be removed after successful recovery to prevent repeated warning messages.

Regular backups should also be maintained for critical configuration files.

Conclusion

Swap-file recovery is the primary recovery method for restoring unsaved changes after a Vim crash.

Undo history and registers are useful during an active editing session, while backup files can restore previously saved versions.

For critical configuration files, the safest strategy is to combine swap-file recovery with regular backups and careful verification of the recovered content.
