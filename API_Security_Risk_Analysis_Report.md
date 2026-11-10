API SECURITY RISK ANALYSIS REPORT

Future Interns – Cyber Security Internship | Task 3

Project: API Security Risk Analysis
Testing Tool: Postman
Target: Postman Echo Public Demonstration API
Assessment Type: Preliminary API Security Assessment
Assessment Date: November 2026

---

1. EXECUTIVE SUMMARY

This assessment examined API endpoints, HTTP methods, authentication mechanisms, query parameters, custom headers, rate-limiting behaviour, and input handling using Postman.

The tests demonstrated successful endpoint communication and authentication responses. Input reflection was also observed.

No production API vulnerabilities were confirmed during this assessment. Postman Echo is a public demonstration service, so these results cannot establish the security posture of a real production API.

2. SCOPE AND METHODOLOGY

2.1 Scope

The assessment covered:

- GET, POST, PUT and DELETE requests.
- Query parameter handling.
- Custom HTTP headers.
- Basic Authentication.
- Bearer Token Authentication.
- Rate-limiting behaviour.
- Input validation and input reflection.

2.2 Tools Used

- Postman.
- Postman Echo public demonstration API.
- GitHub for documentation and evidence storage.

2.3 Methodology

Requests were sent through Postman.

The following elements were examined:

- HTTP response status codes.
- Response bodies.
- Authentication results.
- Query parameter reflection.
- Custom header handling.
- Input reflection.

Testing was limited to non-destructive requests against the demonstration API.

3. ENDPOINT AND HTTP METHOD ANALYSIS

3.1 GET Request

Endpoint: "/get"

Observed Result: HTTP 200 OK.

3.2 POST Request

Endpoint: "/post"

Observed Result: HTTP 200 OK.

3.3 PUT Request

Endpoint: "/put"

Observed Result: HTTP 200 OK.

3.4 DELETE Request

Endpoint: "/delete"

Observed Result: HTTP 200 OK.

3.5 Overall Observation

All four tested HTTP methods returned successful responses.

Successful responses demonstrate endpoint functionality, not the absence of security weaknesses.

4. QUERY PARAMETER ANALYSIS

Endpoint: "/get"

Test parameters included:

- "Project=FutureInterns"
- "task=APISecurity"

Observed Result:

The submitted parameters were reflected in the API response.

Assessment:

Parameter handling was demonstrated. No confirmed injection vulnerability was established.

5. CUSTOM HEADER ANALYSIS

Header Tested:

"X-Custom-Header: FutureInterns"

Observed Result:

The custom header was reflected in the response.

Assessment:

The test confirmed that the demonstration API received and returned the custom header. It did not establish an authorization or header-security vulnerability.

6. AUTHENTICATION ANALYSIS

6.1 Basic Authentication

Endpoint: "/basic-auth"

Test credentials:

- Username: "postman"
- Password: "password"

Observed Result:

- HTTP response: 200 OK.
- Authentication response: "true".

6.2 Bearer Token Authentication

Endpoint: "/auth/bearer"

A test bearer token was supplied through Postman's Authorization configuration.

Observed Result:

- HTTP response: 200 OK.
- Authentication response: "true".

6.3 Assessment

Both authentication demonstrations returned successful responses.

These tests did not establish whether a production API properly enforces permissions, role-based access control, or resource-level authorization.

7. RATE-LIMITING ANALYSIS

Repeated manual GET requests were sent to the demonstration endpoint.

Observed Result:

Multiple requests returned HTTP 200 OK. No HTTP 429 response was observed during the limited manual test.

Assessment:

The result is inconclusive. It does not prove that rate limiting is absent.

Recommendation:

Production APIs should implement appropriate rate limits, request quotas, monitoring, and HTTP 429 responses when limits are exceeded.

8. INPUT VALIDATION ANALYSIS

A script-like input was submitted as a query parameter:

"<script>alert(1)</script>"

Observed Result:

The API returned HTTP 200 OK and reflected the submitted input in its response.

Assessment:

Input reflection was observed. This alone does not establish cross-site scripting (XSS), since browser execution and the relevant output context were not tested.

Recommendations:

- Validate input against expected formats.
- Apply context-appropriate output encoding.
- Use parameterized queries for database operations.
- Reject invalid or unexpected input where appropriate.

9. RISK ASSESSMENT

9.1 HTTP Methods

Finding: All four tested methods returned HTTP 200 OK.

Assessment: No confirmed vulnerability.

9.2 Query Parameters

Finding: Submitted parameter values were reflected.

Assessment: No confirmed vulnerability.

9.3 Custom Headers

Finding: The custom header was reflected.

Assessment: No confirmed vulnerability.

9.4 Basic Authentication

Finding: Authentication demonstration returned a successful response.

Assessment: Limited demonstration; production security not established.

9.5 Bearer Token Authentication

Finding: Authentication demonstration returned a successful response.

Assessment: Limited demonstration; production security not established.

9.6 Rate Limiting

Finding: No HTTP 429 response was observed during limited manual testing.

Assessment: Inconclusive.

9.7 Input Validation

Finding: Script-like input was reflected.

Assessment: Further testing required; no confirmed XSS vulnerability.

9.8 Authorization

Finding: Resource-level access control was not tested.

Assessment: Assessment gap.

Overall Assessment:

No confirmed production security vulnerabilities were identified during this preliminary demonstration-API assessment.

10. SECURITY RECOMMENDATIONS

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

11. LIMITATIONS

The assessment had the following limitations:

- Testing was conducted against Postman Echo, a public demonstration API.
- No production application was assessed.
- Rate-limiting tests were limited to a small number of manual requests.
- Resource-level authorization and access-control testing were not completed.
- Input reflection was observed, but exploitability was not established.
- Results cannot be generalized to other APIs.

12. CONCLUSION

The assessment demonstrated API communication, HTTP method handling, parameter reflection, custom header handling, and authentication mechanisms using Postman.

The tests also identified areas requiring deeper assessment, particularly rate limiting, input validation, and authorization.

Further testing against an authorized application with defined security requirements would be necessary to establish actual security vulnerabilities.

---

Prepared for: Future Interns Cyber Security Internship
Task: Task 3 – API Security Risk Analysis
