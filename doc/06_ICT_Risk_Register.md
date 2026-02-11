# ICT Risk Register

This document includes the **ICT Risk Register** and provides context by explaining:

* The purpose of the ICT risk register within a DORA readiness assessment
* How the register should be interpreted and used
* The qualitative risk scoring approach applied
* The meaning of key columns and risk concepts

---

## 1. Purpose of the ICT Risk Register

The ICT Risk Register consolidates identified ICT risk scenarios into a structured management tool that supports:

* Prioritisation of ICT risks affecting the instant payments service
* Decision-making on risk treatment (mitigation, acceptance, etc.)
* Traceability between regulatory requirements (DORA), identified gaps, and remediation actions

The register is **service-centric**, focusing on the instant payments service rather than individual systems in isolation, in line with DORA expectations for critical ICT-supported services.

---

## 2. How to Use the ICT Risk Register

The ICT Risk Register is intended to be used as follows:

1. **Risk identification**: Each entry represents a plausible ICT risk scenario derived from the DORA gap assessment.
2. **Risk prioritisation**: Likelihood and severity ratings are used to determine relative criticality.
3. **Risk treatment decision**: Management determines whether risks should be mitigated, accepted, transferred, or avoided.
4. **Remediation tracking**: Key mitigation actions and ownership support follow-up and accountability.

The register supports supervisory discussions by demonstrating a structured and risk-based approach rather than exhaustive control-level detail.

---

## 3. Risk Scoring Approach (Qualitative)

### Likelihood

Represents the expected probability of the risk scenario occurring, considering the current control environment.

Scale used:

* **Low** – Unlikely under normal operating conditions
* **Medium** – Plausible occurrence over time
* **High** – Likely to occur without further mitigation

### Severity

Represents the potential severity of consequences should the risk materialise, with emphasis on:

* Availability and integrity of instant payments
* Operational disruption and recovery complexity

Scale used:

* **Low** – Limited, localised impact
* **Medium** – Service degradation with manageable disruption
* **High** – Severe service disruption or loss of critical functionality

### Overall Risk

The overall risk represents a single score that is assigned based on likelihood and severity according to the conservative risk matrix:

| Likelihood ↓ \ Severity → | Low    | Medium | High   |
|---------------------------|--------|--------|--------|
| **Low**                   | Low    | Medium | Medium |
| **Medium**                | Medium | Medium | High   |
| **High**                  | Medium | High   | High   |

---

## 4. Risk Treatment Options

Each risk includes an explicit **Risk Treatment** decision:

* **Mitigate** – Implement additional controls or improvements to reduce likelihood and/or severity
* **Accept** – Formally acknowledge and tolerate the residual risk based on business justification
* **Transfer** – Shift risk exposure through contractual or insurance mechanisms (limited applicability for ICT risks)
* **Avoid** – Discontinue the activity creating the risk (rare for critical banking services)

Risk acceptance is used selectively to demonstrate risk-based decision-making and proportionality.

---

## 5. ICT Risk Register Structure

| Field                            | Description                                            |
| -------------------------------- | ------------------------------------------------------ |
| Risk ID                          | Unique identifier                                      |
| Risk Title                       | Title of the risk                                      |
| Likelihood                       | Qualititive likelihood that the risk scenario occures  |
| Severity                         | Qualitative severity that the risk scenario causes     |
| Overall Risk                     | Overall risk level prior to additional remediation     |
| Residual Risk                    | Risk level after existing controls are considered      |
| Risk Treatment                   | Management decision on how the risk will be handled    |
| Risk Owner                       | Accountable role for managing and monitoring the risk  |
| Response                         | Remediation actions or justification for acceptance    |


---

## 6. Risk Register

![ICT Risk Register Table](/images/risk_register.png)


## 7. Notes and Limitations

* The register is not intended to replace detailed control testing or audits.
* Quantitative risk modeling and financial impact estimation are out of scope.
* Residual risk assumes partial but incomplete control alignment to DORA.
* Risk levels are indicative and designed to support prioritisation and supervisory dialogue.
* Risk ownership is indicative and reflects plausible operating models in retail banks.


