# Lab 02 — Web Recon & Intercept

- **Difficulty:** 🟡 Intermediate
- **Estimated time:** 90–120 minutes

## Objectives

After this lab, you should be able to:

- Configure a browser to route traffic through an intercepting proxy.
- Use Burp Suite's (or OWASP ZAP's) core workflow: Proxy → Intercept → Repeater.
- Map out an application's attack surface (forms, parameters, cookies) before testing.
- Distinguish client-side from server-side controls in a real application.

## Environment

- **Operating system:** Kali Linux VM
- **Target:** DVWA, self-hosted inside your isolated lab network (see [`docs/lab-guidelines.md`](../../docs/lab-guidelines.md))
- **Applications:** Burp Suite Community Edition (or OWASP ZAP), Firefox/Chromium

## Setup

1. Deploy DVWA per its official README (linked in [`resources/tools.md`](../../resources/tools.md)).
2. Confirm DVWA is reachable only within your host-only/internal lab network — verify it is **not** reachable from outside that network.
3. Launch Burp Suite (or ZAP) and configure your browser's proxy settings to point to it (default Burp proxy listener: `127.0.0.1:8080`).
4. Install Burp's CA certificate in your browser if you intend to intercept HTTPS traffic.

## Tasks

1. With interception off, browse DVWA normally and log in, letting Burp passively record every request in the **Proxy → HTTP history** tab.
2. Review the history and map out every distinct endpoint and parameter you can find (e.g., `login.php`, `vulnerabilities/*.php?id=`).
3. Turn interception on and manually walk through submitting one form, observing the raw request before it's sent.
4. Send an interesting request to **Repeater** and modify a parameter, then resend it and compare the response.
5. Identify at least one endpoint where changing a numeric ID parameter returns different data.
6. Identify at least one form field with a client-side restriction, and confirm via Repeater that the server does not enforce the same restriction.

## Expected Results

A documented map of DVWA's tested endpoints, plus at least one confirmed finding of missing server-side validation or authorization.

## Evidence

Export your Burp/ZAP history for the session, or screenshot the key Repeater request/response pairs.

## Questions

1. Why is passive traffic mapping (browsing normally with interception off) often a faster first step than immediately trying to break things?
2. What's the practical difference between Burp's Proxy tab and its Repeater tab?

## Resources

- [`challenges/02-web-exploitation-basics`](../../challenges/02-web-exploitation-basics/README.md) — the companion challenge this lab supports
- [`resources/tools.md`](../../resources/tools.md) — Burp Suite, OWASP ZAP, DVWA entries
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) *(Recommended Additional Resource)*

## Cleanup

- Log out of DVWA and clear any test accounts you created.
- Revert your VM snapshot before starting an unrelated exercise.
