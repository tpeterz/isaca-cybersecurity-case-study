# ISACA Case Study

**Author:** Taylor Peterson  
**Project Type:** Cybersecurity Case Study, Technical Report, Data Analysis  
**Completed For:** ISACA Detroit 11th Annual Scholarship Contest  
**Date:** March 21, 2025  

---

## Overview

This repository contains a redacted cybersecurity case study completed for the **ISACA Detroit 11th Annual Scholarship Contest**. The report investigates a simulated vulnerability affecting the online ordering system of a fictional company, **Widget Manufacturing Company**.

The project uses Burp Suite to inspect and modify HTTP requests, Google Colab/Python workflows to model possible public exposure, and sentiment analysis to evaluate reputational impact.

The case study focuses on a reported exploit where a product priced at **$299** could allegedly be purchased for **$1** by modifying client-side request data using **Burp Suite**. The project evaluates whether the vulnerability exists, explores how public exposure of the issue could affect company reputation, and provides security recommendations to reduce future risk.

This project combines cybersecurity testing, data science, sentiment analysis, technical writing, and risk communication.

---

## Project Goals

The case study was organized around three main goals:

1. **Confirm the reported vulnerability**
   - Test whether the application allowed client-side price manipulation.
   - Use Burp Suite to inspect and modify the HTTP request involved in the order process.
   - Determine whether the server validated price data properly.

2. **Investigate possible public exposure**
   - Search public platforms for evidence of the claimed leak.
   - Model how similar exploit-related discussions could appear online.
   - Use Python-based scraping and sentiment analysis to evaluate public tone and reputational risk.

3. **Provide security recommendations**
   - Identify broader weaknesses in the order workflow.
   - Recommend immediate and long-term fixes related to validation, payment handling, data masking, logging, and monitoring.

---

## Summary of Work Completed

### 1. Vulnerability Confirmation

Using **Burp Suite**, I intercepted the purchase request for the AI Assistant product and inspected the request body. The price value was visible and editable in the client-controlled request data.

I modified the product price from **$299** to **$1** and forwarded the altered request. The order confirmation accepted the changed value, confirming that the system did not properly validate pricing on the server side.

This demonstrated a serious client-side trust issue: critical business values, especially prices, should never be accepted directly from the client without server-side validation.

---

### 2. Public Exposure and Sentiment Analysis

After confirming the vulnerability, I investigated whether the alleged exploit had been shared publicly by the hacker alias “Overwatch.”

The investigation included:

- Manual searches on X/Twitter and Reddit
- Broader keyword searches across public web results
- Simulated leak modeling using related search terms
- Scraping search results into a structured dataset
- Sentiment analysis using Python and TextBlob
- Visualization of topic distribution, top domains, and sentiment trends

Although I did not find direct evidence of the original claimed post, the analysis showed that similar exploit methods, tools, and security topics were actively discussed across platforms such as GitHub, Reddit, Medium, PortSwigger-related sources, and other technical communities.

---

### 3. Security Audit and Recommendations

The final section of the report evaluates broader security risks in the ordering workflow, including:

- Client-side price manipulation
- Sensitive customer and payment-related fields appearing in request data
- Lack of observed third-party payment tokenization
- Unmasked data appearing in order confirmation output
- Need for stronger validation, masking, logging, and monitoring

The report recommends:

- Server-side price calculation
- Secure payment gateway integration
- Tokenization and masking of sensitive values
- HTTPS with modern TLS
- Security headers
- Removal of reflected sensitive data
- Rate limiting and logging
- Digital footprint monitoring for public leaks or brand exposure

---

## Key Takeaway

The case study shows why applications should never trust client-supplied values for critical business logic. Pricing, payment handling, and sensitive customer data should be validated, protected, masked, and processed securely on the server side.

Beyond the technical exploit, the project also demonstrates how data science methods can support cybersecurity investigations by helping assess public exposure, sentiment, and reputational risk.

---

## Tools and Technologies

- **Burp Suite**: HTTP request interception and inspection
- **Google Colab**: Notebook environment used for Python-based scraping, cleaning, sentiment analysis, and visualization
- **Python**: Data collection, cleaning, and analysis
- **TextBlob**: Sentiment analysis
- **DuckDuckGo Search Workflow**: Public web search modeling
- **Matplotlib / Seaborn-style visualizations**: Sentiment and domain analysis
- **LaTeX**: Final technical report formatting
- **GitHub**: Public project documentation and version control

---

## What This Project Demonstrates

This project highlights my ability to:

- Inspect and interpret HTTP requests using Burp Suite
- Identify client-side versus server-side validation issues
- Analyze cybersecurity risk in a simulated web application
- Use Python workflows to collect, clean, and analyze public web search results
- Apply sentiment analysis to evaluate public tone and potential reputational impact
- Create visualizations that summarize domain activity, topic distribution, and sentiment trends
- Translate technical findings into clear recommendations for both technical and non-technical audiences
- Document an investigation in a structured technical report

---

## Repository Contents

```text
isaca-web-security-assessment/
│
├── README.md
├── ISACA_Case_Study_Taylor_Peterson.pdf
└── notebooks/
    └── public_exposure_sentiment_analysis.ipynb
```

The PDF contains the full redacted case study report, including the investigation process, screenshots, visualizations, findings, and final security recommendations.

---

## Note on Redactions

This report was completed as a simulated case study using test data. Screenshots in the public version have been redacted to avoid displaying customer, email, or payment-related values.

The redactions are included to make the report appropriate for public sharing on GitHub while preserving the technical findings and overall investigation process.

---

## Ethical Use Notice

This project was completed in a controlled academic and competition-based context. The testing described in the report was performed as part of a simulated case study and is intended for educational, defensive, and analytical purposes only.

The goal of this work is to demonstrate responsible security analysis, clear documentation, and practical remediation planning.

---

## Key Takeaway

The case study shows why applications should never trust client-supplied values for critical business logic. Pricing, payment handling, and sensitive customer data should be validated, protected, masked, and processed securely on the server side.

Beyond the technical exploit, the project also demonstrates how data science methods can support cybersecurity investigations by helping assess public exposure, sentiment, and reputational risk.
