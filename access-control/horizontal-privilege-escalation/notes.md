## Horizontal Privilege Escalation

Horizontal privilege escalation occurs when a user accesses another user's resources without authorization.

**Example:**

A user accesses their account using `?id=123`. Changing the ID to another user's ID may expose their account and data.

This is an example of **Insecure Direct Object Reference (IDOR)**, where user-controlled parameters directly reference resources without proper authorization checks.

User IDs may be predictable or exposed elsewhere in the application, even if they use unique identifiers (GUIDs).

## Lab

![Login](images/1-screenshot1.png)

![Request 1](images/1-screenshot2.png)

![Request 2](images/1-screenshot3.png)

![Successful Exploitation](images/1-screenshot4.png)

## Horizontal to Vertical Privilege Escalation

Horizontal privilege escalation can lead to vertical escalation if an attacker compromises a more privileged user's account.

For example, modifying `?id=123` to target an administrator may expose their account or enable password changes, granting access to administrative functionality.

## Lab

![Login](images/2-screenshot1.png)

![Modify id to administrator](images/2-screenshot2.png)

![Inspect Page Source](images/2-screenshot3.png)