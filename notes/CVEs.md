# CVEs (Common Vulnerabilities and Exposures)

## What is a CVE?
- CVE (Common Vulnerabilities and Exposures) identifies, defines, and catalogues publicly disclosed cybersecurity vulnerabilities.
- It is important to stay aware of relevant CVEs for the tech stack that you or your company use.
- It is maintained by [MITRE](https://www.mitre.org/), a US non-profit organization.

## CVE Format
- A CVE identifier follows the format: `CVE-[YEAR]-[ID]`
- Example: `CVE-2021-44228`

## CVE Ratings
- CVEs are rated to indicate the severity of the vulnerability:
  - Low
  - Medium
  - High
  - Critical
- These ratings often rely on the [CVSS (Common Vulnerability Scoring System)](https://www.first.org/cvss/).

## Famous CVEs
| CVE ID          | Name/Description          | Affected Area       |
|-----------------|---------------------------|----------------------|
| CVE-2014-0160   | Heartbleed                | OpenSSL             |
| CVE-2017-0143   | SMB (Used by WannaCry)    | SMB Protocol        |
| CVE-2019-0708   | BlueKeep                  | Remote Desktop (RDP)|
| CVE-2021-44228  | Log4Shell (Log4j exploit) | Java logging (Log4j)|

## Why CVEs Matter
Understanding and tracking CVEs is critical in maintaining a secure environment. Regular patching and vulnerability scanning tools can help identify and mitigate risks associated with known CVEs.