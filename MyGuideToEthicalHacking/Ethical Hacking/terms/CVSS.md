# CVSS

CVSS stands for Common Vulnerability Scoring System, and it is a framework used to assess and communicate the severity of security vulnerabilities in software. The CVSS provides a way to standardize the measurement of these vulnerabilities, allowing organizations to prioritize and address them effectively.

The CVSS vector is a string that represents the various aspects and characteristics of a security vulnerability. It consists of a set of metrics, each with its own value, and together they define the overall score for the vulnerability. The vector includes the following metrics:

- **Base Metrics:**
Attack Vector (AV): Describes how an attacker can exploit the vulnerability. Examples include Local (L), Adjacent Network (A), and Network (N).
Attack Complexity (AC): Describes the level of complexity required to exploit the vulnerability. It can be Low (L), Medium (M), or High (H).
Privileges Required (PR): Indicates the level of privileges an attacker needs to exploit the vulnerability. Options include None (N), Low (L), and High (H).
User Interaction (UI): Describes whether user interaction is required to exploit the vulnerability. Possible values are None (N) or Required (R).

- **Impact Metrics:**
Confidentiality (C): Reflects the impact on confidentiality if the vulnerability is exploited. Possible values are None (N), Low (L), or High (H).
Integrity (I): Reflects the impact on integrity if the vulnerability is exploited. Possible values are None (N), Low (L), or High (H).
Availability (A): Reflects the impact on availability if the vulnerability is exploited. Possible values are None (N), Low (L), or High (H).

- **Temporal Metrics:**
Exploit Code Maturity (E): Represents the likelihood that an exploit will be developed in the near future. Possible values are Unproven (U), Proof-of-Concept (P), Functional (F), or High (H).
Remediation Level (RL): Describes the existence and effectiveness of official solutions for the vulnerability. Possible values are Official Fix (O), Temporary Fix (T), Workaround (W), or Unavailable (U).
Report Confidence (RC): Reflects the confidence in the existence of the vulnerability and the credibility of the information. Possible values are Unknown (U), Reasonable (R), or Confirmed (C).

- **Environmental Metrics:**
Confidentiality (CR), Integrity (IR), Availability (AR): These metrics are similar to the corresponding base metrics but are applied to the impact on the environment in which the vulnerable system operates.
The CVSS vector provides a standardized way to communicate the severity of vulnerabilities, making it easier for organizations to prioritize and address security issues based on their potential impact.
