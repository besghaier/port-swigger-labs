# Server-Side Request Forgery (SSRF)

SSRF is a vulnerability that allows an attacker to make a server-side application send HTTP requests to unintended destinations, potentially accessing internal services or exposing sensitive data.

## SSRF Attacks Against the Server

An attacker manipulates a server-side request to access internal endpoints, such as `http://localhost/admin`. This may bypass access controls if the server trusts requests originating from its loopback interface.

## Why SSRF Can Bypass Access Controls

Applications may trust local requests because authentication checks are handled by another component, administrative interfaces allow local access, or internal services listen on restricted ports. These trust relationships can make SSRF a critical vulnerability.

## Lab 1

**Inspect the stock request**

![Inspect stock request](images/screenshot1.png)

**Change the stock API URL to `http://localhost/admin`**

![Access admin interface through SSRF](images/screenshot2.png)

**Attempt to delete the user directly**

![Attempt direct user deletion](images/screenshot3.png)

**Observe the access-denied response**

![Access denied](images/screenshot4.png)

**Target the internal deletion endpoint through SSRF**

![Send SSRF request to deletion endpoint](images/screenshot5.png)

**Verify successful user deletion**

![User deleted successfully](images/screenshot6.png)




## Lab 2

Used the stock check functionality to scan the internal `192.168.0.X` range for an admin interface on port `8080`, as described in the lab.

**Inspect the stock check request**

![Inspect stock request](images/2-screenshot1.png)

**Send the request to Intruder and scan IPs 1–254**

![Scan internal IP range](images/2-screenshot2.png)

**Identify the target IP address**

![Identify target IP](images/2-screenshot3.png)

**Access the admin interface at `192.168.0.212`**

![Access admin interface](images/2-screenshot4.png)

**Delete user `carlos` through SSRF**

![Delete user Carlos through SSRF](images/2-screenshot5.png)