# Security Policy

We believe that no technology is perfect and that working with skilled security researchers
is crucial in identifying weaknesses.

If you believe you've found a security bug in our service, we'll be happy to work with you
to resolve the issue promptly and ensure you are fairly rewarded for your discovery.

We will investigate legitimate reports and make every effort to quickly resolve any vulnerability.
To encourage responsible reporting, we will not take legal action against you nor ask law enforcement
to investigate you providing you comply with the current policy and more generally with the following guideline: Make a good faith effort to
avoid privacy violations, destruction of data, and interruption or degradation of our services.

## Eligibility and Responsible Disclosure

Only those that meet the following eligibility requirements may receive a monetary reward:

- You must be the first reporter of a vulnerability.
- The vulnerability must be a qualifying vulnerability.
- Any vulnerability found must be reported no later than 72 hours after discovery.
- You must send a clear textual description of the report along with steps to reproduce the issue, include attachments such as screenshots or proof of concept code as necessary.
- You must avoid tests that could cause degradation or interruption of our service (refrain from using automated tools, and limit yourself about requests per second).
- You must not leak, manipulate, or destroy any user data.
- You must not be a former or current employee of Open Collective or one of its contractor.

## Scope

We **won't** accept reports made by testing on our production servers (https://opencollective.com).

We provide staging servers with a very similar configuration on the following URLs:

- API: https://api-staging.opencollective.com
- Frontend: https://staging.opencollective.com
- Invoices: https://invoices-staging.opencollective.com
- Images: https://images-staging.opencollective.com

Please use this staging servers or (better) setup a local server:

- API: https://github.com/opencollective/opencollective-api
- Frontend: https://github.com/opencollective/opencollective-frontend
- Invoices: https://github.com/opencollective/opencollective-invoices
- Images: https://github.com/opencollective/opencollective-images
- BackYourStack: https://github.com/opencollective/backyourstack

## Contact

- Mail: security@opencollective.com
- Preferred languages: English

## Rewards

| Project       | Type            | Security requirement | Low  | Medium | High  | Critical |
| ------------- | --------------- | -------------------- | ---- | ------ | ----- | -------- |
| API           | API             | +++                  | \$50 | \$100  | \$200 | \$500    |
| Frontend      | Web Application | +++                  | \$50 | \$100  | \$200 | \$500    |
| Invoices      | API             | ++                   | \$25 | \$50   | \$100 | \$250    |
| Images        | API             | ++                   | \$25 | \$50   | \$100 | \$250    |
| BackYourStack | Web Application | +                    | \$15 | \$30   | \$75  | \$150    |

## Qualifying vulnerabilities

- Remote code execution (RCE)
- Local files access and manipulation (LFI, RFI, XXE, SSRF, XSPA)
- Code injections (JS, SQL, PHP, ...)
- Cross-Site Scripting (XSS)
- Cross-Site Requests Forgery (CSRF) with real security impact
- Open redirect
- Broken authentication & session management
- Insecure direct object references
- CORS with real security impact
- Horizontal and vertical privilege escalation
- SQL injections

## Non-qualifying vulnerabilities

- "Self" XSS
- Rate Limiting
- Text/HTML Injection
- Social engineering
- Homograph Attack
- Missing cookie flags
- Information disclosure
- SSL/TLS best practices
- Mixed content warnings
- Denial of Service attacks
- Missing security headers
- Clickjacking/UI redressing
- Software version disclosure
- Stack traces or path disclosure
- Missing autocomplete attributes
- Physical or social engineering attempts
- Recently disclosed 0-day vulnerabilities
- Presence of autocomplete attribute on web forms
- Vulnerabilities affecting outdated browsers or platforms
- Our policies on presence/absence of SPF/DMARC records
- Any hypothetical flaw or best practices without exploitable POC
- Issues that require physical access to a victim’s computer/device
- Logout and other instances of low-severity Cross-Site Request Forgery
- Extension manipulation without any evidence of vulnerability (Attachments)
- Missing security-related HTTP headers which do not lead directly to a vulnerability
- Reports from automated web vulnerability scanners (Acunetix, Vega, etc.) that have not been validated
- Invalid or missing SPF (Sender Policy Framework) records (Incomplete or missing SPF/DKIM/DMARC)
- Any issues regarding single session features/management
- RTLO and related issues

## Process

- Reporter submit a report
- Open Collective Team...
  - Confirm that the report has been received
  - Tries to reproduce the issue
  - Discuss results and possible impact to determine the score (low/medium/high/critical) and bounty amount
- Reporter is rewarded with a bounty at this stage (if applicable)
- Team work on a fix, verify it and pushes it
- Team confirm that the issue has been patched and may ask reporter to confirm the fix

## How do we calculate the severity score

Our analysis is always based on worst case exploitation of the vulnerability, as is the reward we pay. We will rely on CVSS3 as well as internal criterias to score the vulnerabilities.

CVSS3 score:

- From 1 to 4 ==> Low
- From 4 to 7 ==> Medium
- From 7 to 9 ==> High
- From 9 to 10 ==> Critical

Things that we take into account to adjust the score for vulnerabilities:

- Everything related to authentication
- Allow to take control or leak information about payment methods
- Compromise the integrity or historicity of our transactions ledger
- Compromise the permission system
