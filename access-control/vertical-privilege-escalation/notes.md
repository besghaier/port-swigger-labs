## Vertical Privilege Escalation

If a user gains access to functionality they are not authorized to access, this is vertical privilege escalation.

## Robots.txt (Robots Exclusion Protocol or REP)

A file that specifies which URLs web crawlers should or should not crawl.

## Unprotected Functionality

Sensitive admin URLs lack access controls, allowing unauthorized users to access them directly.

These URLs can be discovered through exposed paths or brute-forced using a wordlist.

## Lab

**1. Login Page**

![Login Page](images/1-screenshot1.png)

**2. Access Robots.txt**

![Robots.txt](images/1-screenshot2.png)

**3. Successful Exploitation**

![Successful Exploitation](images/1-screenshot3.png)

## Unprotected Functionality - Continued

Hiding admin URLs (**security by obscurity**) is not effective access control.

Obfuscated URLs may still be discovered in client-side JavaScript, even if the admin link is hidden from ordinary users.

## Lab

**1. Login Page**

![Login Page](images/2-screenshot1.png)

**2. Access Page Source**

![Page Source](images/2-screenshot2.png)

**3. Successful Exploitation**

![Successful Exploitation](images/2-screenshot3.png)

## Parameter-Based Access Control

Some applications store user roles in client-controllable locations, such as hidden fields, cookies, or URL parameters.

Attackers can modify these values to gain unauthorized access to privileged functionality.

**Examples:**
- `?admin=true`
- `?role=1`

## Lab

**1. Logged in as `wiener:peter`**

![Login as Wiener](images/3-screenshot1.png)

**2. Change Admin Value to `true`**

![Modified Request](images/3-screenshot2.png)

**3. Successful Exploitation**

![Successful Exploitation](images/3-screenshot3.png)