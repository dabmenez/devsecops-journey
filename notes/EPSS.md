# EPSS (Exploit Prediction Scoring System)

EPSS, or Exploit Prediction Scoring System, is a scoring framework that estimates the likelihood of a vulnerability being exploited in the wild within the next 30 days.

## Key Points

- **EPSS** is managed by **FIRST**, the same organization that oversees **CVSS**.
- Provides a **daily probability score** ranging from 0 to 1.
- Designed to **complement CVSS**, not replace it.
- Assigned to known **CVEs** (Common Vulnerabilities and Exposures).
- Helps prioritize which vulnerabilities should be addressed first.

## Usage

- A **high EPSS score** combined with a **critical CVSS score** indicates an urgent need to remediate.
- Example prioritization logic:
  ```
  High EPSS + Critical CVSS > Low EPSS + Critical CVSS
  ```

## Score Breakdown

- **EPSS Score**: A float between 0.0 and 1.0 indicating likelihood of exploitation.
- **Percentile**: Indicates how a particular EPSS score compares with all others (e.g., 99th percentile means only 1% of scores are higher).

## Example

| CVE ID          | EPSS Score | Percentile |
|-----------------|------------|------------|
| CVE-2021-44228  | 0.9691     | 0.99747    |

## Summary

EPSS is a valuable addition to vulnerability management programs by offering predictive analytics on which vulnerabilities are most likely to be exploited, improving patch prioritization decisions.