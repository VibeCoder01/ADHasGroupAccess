# AD-GroupMembershipAccessAudit

Enumerate Active Directory groups and determine whether the current user has rights to add or remove group members based on effective ACLs.

## Overview

This PowerShell script inspects Active Directory group object permissions and identifies groups where the currently logged-on user can modify membership.

It evaluates permissions including:
- GenericAll
- GenericWrite
- WriteDacl
- WriteOwner
- WriteProperty on the member attribute

Results are displayed in an interactive grid view with a clear True/False access indicator.

## Requirements

- Windows PowerShell 5.1 or PowerShell 7+
- Active Directory PowerShell module (RSAT)
- Domain-joined machine
- Read access to Active Directory

## Usage

1. Open PowerShell with the ActiveDirectory module available.
2. Optionally restrict `$searchBase` in the script to a specific OU.
3. Run the script.
4. Review results in the grid view.

## Output Fields

- GroupName
- GroupScope
- GroupCategory
- HasAccess
- Reason
- DN

## Notes

- Deny ACEs are not explicitly evaluated.
- Protected groups (AdminSDHolder) may behave differently.
- This script does not modify Active Directory.

## License

MIT
