API Security Risk Analysis Report

Future Interns – Cyber Security Internship | Task 3

Project Detail| Information
Project| API Security Risk Analysis
Testing Tool| Postman
Target| Postman Echo Public Demonstration API
Assessment Type| Preliminary API Security Assessment
Assessment Date| November 2026

---

1. Executive Summary

This assessment examined API endpoints, HTTP methods, authentication mechanisms, query parameters, custom headers, rate-limiting behaviour and input handling using Postman.

The tests demonstrated successful endpoint communication and authentication responses. Input reflection was also observed.

No production API vulnerabilities were confirmed during this assessment. Since Postman Echo is a demonstration service, the results should not be interpreted as proof of the security posture of a real production API.

2. Scope and Methodology

2.1 Scope

The assessment covered:

- GET, POST, PUT and DELETE requests
- Query parameter handling
- Custom HTTP headers
- Basic Authentication
- Bearer Token Authentication
- Rate-limiting behaviour
- Input validation and input reflection

2.2 Tools Used

- Postman
- Postman Echo public demonstration API

2.3 Methodology

Requests were sent through Postman. HTTP response codes, response bodies, authentication results and reflected request data were examined.

Testing was limited to non-destructive requests against the demonstration API.

3. Endpoint and HTTP Method Analysis

Test| Endpoint| Observed Result
GET| "/get"| 200 OK
POST| "/post"| 200 OK
PUT| "/put"| 200 OK
DELETE| "/delete"| 200 OK

Observation: All four HTTP methods returned successful responses during testing.

Security Note: Successful responses confirm endpoint functionality, not the absence of security weaknesses.

4. Query Parameter Analysis

Endpoint: "/get"

Test parameters included:

- "Project=FutureInterns"
- "task=APISecurity"

Observed Result: The submitted parameters were reflected in the response.

Assessment: Parameter handling was demonstrated. No confirmed injection vulnerability was established.

5. Custom Header Analysis

Header Tested: "X-Custom-Header: FutureInterns"

Observed Result: The custom header was reflected in the response.

Assessment: The test confirmed that the demonstration API received and returned the custom header. It did not establish an authorization or header-security vulnerability.

6. Authentication Analysis

6.1 Basic Authentication

Endpoint: "/basic-auth"

Test credentials:

- Username: "postman"
- Password: "password"

Observed Result: HTTP 200 OK and ""authenticated": true".

6.2 Bearer Token Authentication

Endpoint: "/auth/bearer"

A test bearer token was supplied through Postman's Authorization configuration.

Observed Result: HTTP 200 OK and ""authenticated": true".

Assessment: Both authentication demonstrations returned successful responses.

Limitation: These tests did not establish whether a production API properly enforces permissions, role-based access control or resource-level authorization.

7. Rate-Limiting Analysis

Repeated manual GET requests were sent to the demonstration endpoint.

Observed Result: Multiple requests returned HTTP 200 OK. No HTTP 429 response was observed during the limited manual test.

Assessment: The result is inconclusive. It does not prove that rate limiting is absent.

Recommendation: Production APIs should implement suitable rate limits, request quotas, monitoring and appropriate HTTP 429 responses when limits are exceeded.

8. Input Validation Analysis

A script-like input was submitted as a query parameter:

"<script>alert(1)</script>"

Observed Result: The API returned HTTP 200 OK and reflected the submitted input in its response.

Assessment: Input reflection was observed. This alone does not establish cross-site scripting (XSS), since browser execution and the relevant output context were not tested.

Recommendations:

- Validate input against expected formats.
- Apply context-appropriate output encoding.
- Use parameterized queries for database operations.
- Reject invalid or unexpected input where appropriate.

9. Risk Assessment

Area| Finding| Assessment
HTTP methods| All four methods returned 200 OK| No confirmed vulnerability
Query parameters| Values reflected| No confirmed vulnerability
Custom headers| Header reflected| No confirmed vulnerability
Basic Authentication| Authentication response successful| Limited demonstration
Bearer Authentication| Authentication response successful| Limited demonstration
Rate limiting| No 429 observed in limited testing| Inconclusive
Input validation| Script-like input reflected| Requires further testing
Authorization| Resource-level access control not tested| Assessment gap

No confirmed production security vulnerabilities were identified.

10. Recommendations

1. Enforce authentication on protected API endpoints.
2. Implement authorization checks for every protected resource.
3. Validate and sanitize user-supplied input.
4. Apply context-appropriate output encoding.
5. Implement rate limiting and request monitoring.
6. Avoid exposing sensitive information in API responses.
7. Use HTTPS for API communication.
8. Protect authentication tokens and credentials.
9. Maintain structured API logs and monitor suspicious activity.
10. Perform further security testing in an authorized environment.

11. Limitations

- Testing was conducted against Postman Echo, a public demonstration API.
- No production application was assessed.
- Rate-limiting tests were limited to a small number of manual requests.
- Resource-level authorization and access-control testing were not completed.
- Input reflection was observed, but exploitability was not established.
- Results cannot be generalized to other APIs.

12. Conclusion

The assessment demonstrated API communication, HTTP method handling, parameter reflection, custom header handling and authentication mechanisms using Postman.

The tests also identified areas requiring deeper assessment, particularly rate limiting, input validation and authorization.

Further testing against an authorized application with defined security requirements would be necessary to establish actual security vulnerabilities.

---

Prepared for: Future Interns Cyber Security Internship
Task: Task 3 – API Security Risk Analysis
