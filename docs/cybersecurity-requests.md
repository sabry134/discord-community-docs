# Cybersecurity Requests for Users

## Introduction

This document outlines the cybersecurity requests that users can make to the cybersecurity team for their projects. Each request serves a specific purpose and must meet certain criteria to be approved. It's important to understand the reasons behind each request and when it is appropriate to make them. Requests will be evaluated based on necessity, feasibility, and alignment with cybersecurity best practices.

## No CI/CD

**Reason:** Continuous Integration/Continuous Deployment (CI/CD) pipelines automate software delivery processes, ensuring code quality and enabling rapid deployment. However, there may be situations where CI/CD pipelines are not feasible or suitable for a project.

**Approved Use Case:**
- Legacy Systems: Projects running on legacy systems may not support CI/CD pipelines due to compatibility issues.
- Regulatory Compliance: Compliance requirements may restrict the use of automated deployment processes like CI/CD.

**Rejected Use Case:**
- Modern Development Practices: Projects that can benefit from CI/CD pipelines should prioritize their implementation to improve development efficiency and deployment speed.

## Specific Tools for Analysis

**Reason:** Certain cybersecurity analysis tools are essential for identifying and mitigating security vulnerabilities. However, the use of proprietary or non-free tools may not align with the organization's budget or open-source principles.

**Approved Use Case:**
- Necessity: If specific security analysis tools are required to address unique security challenges, the cybersecurity team may approve their usage.
- Lack of Open-Source Alternatives: When no suitable open-source alternatives are available for critical security assessments, proprietary tools may be considered.

**Rejected Use Case:**
- Budget Constraints: Requests for non-free tools exceeding the organization's budget will be rejected.
- Availability of Open-Source Options: If viable open-source alternatives exist, users should prioritize their usage over proprietary tools.

**Reason:** Encryption is essential for protecting sensitive data from unauthorized access or interception. However, implementing encryption mechanisms requires careful consideration of factors such as performance impact and key management.

**Approved Use Case:**
- Data Protection: Encrypting sensitive data helps mitigate the risk of data breaches and ensures confidentiality.
- Regulatory Compliance: Compliance frameworks may mandate the use of encryption to protect sensitive information.

**Rejected Use Case:**
- Performance Overhead: Requests for encryption mechanisms imposing significant performance overhead may be rejected if alternative security measures can achieve similar protection levels with less impact.
- Inadequate Key Management: Encryption solutions lacking robust key management practices may pose security risks and be deemed unsuitable for deployment.

## Conclusion

Users should carefully evaluate the necessity of each cybersecurity request and ensure that it aligns with project requirements and cybersecurity best practices. Requests will be evaluated based on their feasibility and alignment with organizational policies. If a requested solution is not feasible or aligns with existing practices, users are encouraged to explore alternative solutions in collaboration with the cybersecurity team.
