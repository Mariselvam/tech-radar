# The important aspects of developing great REST APIs

##  1. Identifying Resources
From the application domain model objects, identify the objects/resources that need to be exposed through REST APIs for users to perform actions on those resources.


## 2. Identifying Actions (GET, POST, PUT, DELETE, ...)
This is about identifying what are all the actions the consumers can perform on the exposed REST resources.

## 3. Defining Request and Response structures

### 3.1 Defining Request Structure includes:
1. defining http verb

2. defining request body

3. defining requests parameters if any

4. defining request headers if any

### 3.2 Defining Response Structure includes:
1. defining response status code

2. defining response body

3. defining response headers
      
## 4. Using appropriate Response Status code
Appropriate http response status codes need to be returned based on the action on the resource and use case scenario.

## 5. Validation
This is about adding validations to the request body, parameters and headers.
    
## 6. Internationalization - i18n
If the consumers for the REST API are all over the world, then adding support for different languages is required.
## 7. Exception Handling
It's important to handle error scenarios and return appropriate error codes and error messages in the response.
This will help the consumers of the REST APIs to decide on their side business logic in case of error scenarios.

## 8. HATEOAS
*HATEOAS* - **Hypermedia As The Engine Of Application State**

- This is all about enhancing your REST API responses to tell consumers how to perform subsequent actions by including links in the response body.

- There is a standard defined for this : **HAL - JSON Hypertext Application Language**

- HAL - Simple format that gives a consistent and easy way to hyperlink between resources in your API

## 9. Versioning

Versioning is important because, it will allow to implement changes in the REST APIs without breaking existing consumers code.

### 9.1 Different approaches for implantation

1. URI path based versioning
2. Request parameters based versioning
3. Custom headers based versioning
4. Content Negotiation based versioning

### 9.2 Factors to be considered while deciding the approach for versioning implementation:

1. URI Pollution
2. Misuse of HTTP Headers
3. Caching
4. Can we execute the request on the browser?
5. API Documentation

## 10. Response Content Filtering
### 10.1 Static Filtering

This about filtering contents in the response body of REST APIs.

1) password fields can't be included in the response body.

2) secret values can't be included in the response body

3) Related domain objects need not to be included in response body.

4) Static filter is about implementing common filtering for all the APIs.

5) Static filtering is usually implemented in domain object classes

### 10.2 Dynamic Filtering

1. Dynamic filtering is all about implementing specific filtering for each REST API.

2. Dynamic filtering is usually implemented in controllers.

## 11. Monitoring
Monitoring capability is needed in production environment.

This should include:
- Application overall health status
- Metrics on handled http requests
- Metrics on runtime environment


## 12. Documentation

- Clear documentation is important for the consumers of REST APIs
- Generating accurate and consistent documentation for the REST API urls
- Generating from code is the answer to make the documentation accurate and consistent.