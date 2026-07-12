# SPEC-AUTH-0004

## Spec Header

| Field | Value |
|-------|-------|
| format_version | 2 |
| spec_id | SPEC-AUTH-0004 |
| namespace | auth |
| type | feature |
| status | draft |

## User Request

> Add a change-password endpoint to the authentication system: a logged-in user provides their current password and a new password. The request is rejected with an error if the current password is wrong, and the new password must be at least 8 characters long.

## Summary

```yaml
Add a change-password endpoint to the authentication system: a logged-in user provides their current password and a new password. The request is rejected with an error if the current password is wrong, and the new password must be at least 8 characters long.
```

## Requirements

```yaml
functional:
  - id: FR-1
    description: Logged-in user can change their password
    priority: must-have
  - id: FR-2
    description: System checks if the current password is correct
    priority: must-have
  - id: FR-3
    description: New password must be at least 8 characters long
    priority: must-have
  - id: FR-4
    description: System returns an error if the current password is incorrect
    priority: must-have
non_functional:
  - id: NFR-1
    description: Change-password endpoint responds within 500ms at p95
    priority: should-have
```

## Technical Design

```yaml
affected_components:
  - auth/views.py
  - auth/serializers.py
api_changes:
  - method: PATCH
    path: /api/v1/auth/change-password
    description: Accepts current password and new password, returns success or error
data_model_changes: []
```

## Acceptance Criteria

- [ ] AC-1: Logged-in user can change their password with a valid current password and new password that meets length requirement
- [ ] AC-2: System returns an error if the current password is incorrect
- [ ] AC-3: Response time is under 500ms at p95

---

<details>
<summary>Raw Spec (XML)</summary>

```xml
<spec_header>
format_version: 2
spec_id: SPEC-AUTH-0004
namespace: auth
type: feature
status: draft
</spec_header>

<summary>
Add a change-password endpoint to the authentication system: a logged-in user provides their current password and a new password. The request is rejected with an error if the current password is wrong, and the new password must be at least 8 characters long.
</summary>

<requirements>
functional:
  - id: FR-1
    description: Logged-in user can change their password
    priority: must-have
  - id: FR-2
    description: System checks if the current password is correct
    priority: must-have
  - id: FR-3
    description: New password must be at least 8 characters long
    priority: must-have
  - id: FR-4
    description: System returns an error if the current password is incorrect
    priority: must-have
non_functional:
  - id: NFR-1
    description: Change-password endpoint responds within 500ms at p95
    priority: should-have
</requirements>

<technical_design>
affected_components:
  - auth/views.py
  - auth/serializers.py
api_changes:
  - method: PATCH
    path: /api/v1/auth/change-password
    description: Accepts current password and new password, returns success or error
data_model_changes: []
</technical_design>

<acceptance_criteria>
- [ ] AC-1: Logged-in user can change their password with a valid current password and new password that meets length requirement
- [ ] AC-2: System returns an error if the current password is incorrect
- [ ] AC-3: Response time is under 500ms at p95
</acceptance_criteria>
```

</details>
