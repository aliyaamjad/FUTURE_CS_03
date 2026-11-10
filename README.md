API Security Risk Analysis

Future Interns – Cyber Security Internship | Task 3

Project Overview

This project documents a preliminary API security assessment conducted using Postman and the Postman Echo public demonstration API.

Objectives

- Examine API endpoints and HTTP methods.
- Analyse query parameters and custom headers.
- Test Basic and Bearer Token authentication.
- Observe rate-limiting behaviour.
- Examine input validation and input reflection.

Tools Used

- Postman
- Postman Echo API
- GitHub

Tests Performed

1. GET endpoint testing
2. POST endpoint testing
3. PUT endpoint testing
4. DELETE endpoint testing
5. Query parameter testing
6. Custom header testing
7. Basic authentication
8. Bearer token authentication
9. Rate-limiting observation
10. Input validation testing

Project Files

- "API Security Risk Analysis Report" (API_Security_Risk_Analysis_Report.md)
- "Evidence Screenshots" (evidence/)

Key Observations

- All four tested HTTP methods returned successful responses.
- Both authentication demonstrations returned successful responses.
- Query parameters and custom headers were reflected.
- No HTTP 429 response was observed during limited manual rate-limit testing.
- Script-like input was reflected, but no XSS vulnerability was confirmed.

Limitations

Testing was performed against a demonstration API, not a production application. Resource-level authorization and comprehensive security testing were outside the assessment scope.

Conclusion

The assessment demonstrates API testing techniques and documents observations, limitations and security recommendations. No production vulnerabilities were confirmed.

Internship: Future Interns
Task: CS Task 03 – API Security Risk Analysis
