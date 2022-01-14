# Basic Syntax on RAML-RESTful API Modeling Language

- Has 4 components:
    1. Operation
        - Defines the resource and the HTTP method (GET, POST, PUT, PATCH, DELETE ...)
            - resource is the path to query, for example ``/flights``, or ``/accounts``
        ```yaml
        #%RAML 1.0

        /accounts
        ```

    2. Input
        - is the data and or metadata used for the method request, involves 3 parts:
        - *URI Paramters*: ``/{ID}`` identify a nested resource like: ``/{Gender}``, `{CustomerID}` tec.
        - *Query Parameter*: used for filtering conditions like: ``salary = 1000``, `age=13`, `name=Dan` etc.
        - *Header*: it contains metadata like: content-length, content-type, clientID, clientSecret.
        - *Body*: It will contain resource details, for example, when creating a customer account, we would need customer data like name, age, location, payment details etc.
            - GET, DELETE does not need body
            - Other methods might need body, like PUT, PATCH
    3. Output: 
        1. HTTP Status response:
            - Is the response we obtain for an operation done, those response are from the server as HTTP status codes
            ![](https://softcrony.com/blog/wp-content/uploads/2020/07/http-code.png)*HTTP status codes*
            - 200 success
            - 201 resource created
            - 400 BAD request
            - 401 Unauthorized : incorrect or missing credentials or password
            - 404 Page not found
            - 500 Critial error
        2. Body: It will contain resource details
    4. Uderlying Data type:
        - It is data type of our input or output, which can be in:
            - XML format.
            - JSON format.
            - Java Object format.
            - CSV format.
            - Text file format ... etc
