# PartnerTap Analytics API
The [PartnerTap Analytics API](https://reports.partnertap.com/swagger-ui.html) provides usage statistics and partnership data for your organization.

## Overview

### API Basics
The [API Basics](https://reports.partnertap.com/swagger-ui.html#/*_API_Basics) endpoints provide auth functionality. This is the first endpoint you will need to setup in order to retrieve a JWT token with your API Key (provided by PartnerTap customer service). 

### Dashboard
The [Dashboard](https://reports.partnertap.com/swagger-ui.html#/Dashboard_by_Division) endpoints provide organization wide high level point in time analytics for chat counts, partnership counts, slaes rep counts, and sales rep login counts.

### Partnership Statistics
The [Partnership Statistic](https://reports.partnertap.com/swagger-ui.html#!/Partnerships_Statistics/getNewRepConnectionsUsingGET) endpoints provide a individual sales rep stats for number and type of partnership connections. You can use these endpoints to determine which sales reps have  partnership requests that they have not responded to, the number of partnership requests they've sent they have not been responded to yet, and the number of partnerships accepted. 

### Opportunities Shared
The [Opportunities Shared](https://reports.partnertap.com/swagger-ui.html#/Opportunities_Shared) endpoints provide a high level summary of the all the orgs you are sharing opps with. It also provides a complete list of opportunities inbound/outbound for all partner organizations that can be filtered by partner organiztion.

### SaleAccounts Matched/Unmatched
The [SaleAccounts](https://reports.partnertap.com/swagger-ui.html#/SaleAccounts_Matched/Unmatched) endpoints provide a complete list of matched or unmatched accounts. The results can be filtered by a partner organization or search string.

### Chats Exchanged
The [Chats Exchanged](https://reports.partnertap.com/swagger-ui.html#/Chats_Exchanged) endpoints provide a list of sales reps and how many chat exchanges they have generated, segregated by partner org.

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
### Pagination
Most endpoints are paginated and have three optional params: page, size and sort.  Page is the page number you would like to retrieve. Size is the number of records per page. Sort is the column you would like to sort on (e.g. sort=partnerOrg,asc).

### Explore the Documentation

Get familiar with PartnerTap API by looking through the [swagger documentation](https://reports.partnertap.com/swagger-ui.html).

## Roadmap
1. Sales Rep endpoints for Chat Exchanges details
2. Time series endpoints for Dashboard 
3. Usage examples
