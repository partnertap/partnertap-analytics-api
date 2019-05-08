# PartnerTap Analytics API
The PartnerTap Analytics API provides usage statistics and partnership data for your organization.

## Usage

### Obtain a JWT Token

1. Obtain an API Key from support@partnertap.com.  Note that you need to be an existing contracted client of PartnerTap.

2. Using the API key request a JWT and add it to all of your API requests in a 'Authorization' header
  ```
  curl 'https://reports.partnertap.com/api/auth?apiKey=dfaf26de-bf8a-4eb3-afe4-d378f8aaf6f8'
  ```
3. The resulting json response will look something like this:
  ```json
  {"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI4YTQyODFmMjZhOTYxMjdmMDE2YTk2MTJkYjQwMDAwMCIsImNvbS5wYXJ0bmVydGFwLnBlcm1pc3Npb25zIjoiQURNSU5fVklFV19SRVBPUlRTLEFQSV9BQ0NFU1MiLCJpc3MiOiJQYXJ0bmVyVGFwIiwiZXhwIjoxNTU5OTI4MzIxLCJpYXQiOjE1NTczMzU3MjEsImNvbS5wYXJ0bmVydGFwLmFkbWluLmlkIjoiOGE0MjgxZjI2YThlY2Q5NDAxNmE4ZWNlOWQzZDAwMDIifQ.lCTNoPiLjKWiZMnaHCsPVZF-S6MPN902A0FHIkI3RbY"}
  ```
4. Optional. You can test the generated JWT token payload in the [JWT.io debugger](https://jwt.io/)

5. Add the JWT to Authorization header for all of your requests
```
curl -X GET \
  https://reports.partnertap.com/analytics/newrepconnectionslist \
  -H 'Accept: */*' \
  -H 'Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI4YTQyODFmMjZhOTYxMjdmMDE2YTk2MTJkYjQwMDAwMCIsImNvbS5wYXJ0bmVydGFwLnBlcm1pc3Npb25zIjoiQVBJX0FDQ0VTUyIsImlzcyI6IlBhcnRuZXJUYXAiLCJleHAiOjE1NTk4ODk3NDQsImlhdCI6MTU1NzI5NzE0NCwiY29tLnBhcnRuZXJ0YXAuYWRtaW4uaWQiOiI4YTQyODFmMjZhOGVjZDk0MDE2YThlY2U5ZDNkMDAwMiJ9.6XapFtb-sAfpq1u9PwUgcsBu1PfTE3Zh5_bdl756zew' \
```

### Explore the Documentation

Get familiar with PartnerTap API by looking through the [swagger documentation](https://reports.partnertap.com/api).
