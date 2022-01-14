# Mulesoft Fundamentals - Self Paced-ILT

**Parts of the course**:
1) Build an application network using API-Led connectivity and Anypoint Platform
2) Use *Anypoint Platform*
    - As a central repository for discoverable and reusable assets
    - To build apps to connect assets and connect systems
    - To take an API through its complete development cycles
3) *Use Anypoint Studio* to build and debug integrations and API implementations
    - Connect to databases, files, web services, Saas apps, JMS queues, and more
    - Add application logic and handle errors
    - Handle batch data processing (process for achieves the completion of work)


## Case of Study
- It is presented as *The Mule United Airport* which has 3 airlines that can deliver their flight data through several methods:
    1) *United Airlines* flight info is presented as a REST web service (as a JSON).
    2) *Delta Airlines* flight info is presented as a SOAP web service (as an XML).
    3) *American Airlines* provides access to their MySQL database (a RESTful web service is needed in order to be consumable and reusable, as well as composable).

*Note:* _The Mule United Airport_ also stores data of their customers' accounts on a MySQL database and Salesforce 

![](https://image.slidesharecdn.com/mulesoftmodule2-170415045944/95/mule-soft-raml-api-designing-16-638.jpg?cb=1492232586)

## Purpose of Case of Study
- Deliver an application that consumes:
    - Data from a RESTful API.
        - Provides access to American Flights database.
            - Use a System API created by other MUA developers.
- Design, build, deploy and manage APIs.
- Build a single API which allows users to search for flights of each of the airlines, either individualy or combined for a specific destination.
- Build Mulesoft applications using Anypoint Studio.
    - Learn abour DataWeave (programming language used for data transformation, from java to XML, JSON, CSV and others ...)
    - Retrieve flight data for each individual airline consuming different types of APIs (RESTful, SOAP web services)
    - Create a single endpoint to retrieve all flights or filter by airlines, destination etc.
    - Handle errors on Mule applications.
    - Write DataWeave Transformation Scripts.

## API Led-connectivity
- It is an approach to design API that encourages reusable, composable (can be assemble by different combinations).
- It uses feedback from users to get better.

![](https://blogs.mulesoft.com/wp-content/uploads/img_6059cf82c124c.png)

- System APIs: is data obtained from differents web services as SAP, Salesforce customers, and the records of orders which will be credit card numbers, items and shipping.
- Proccess APIs, with all this information, it aggregates Customers in a common endpoint it also retrieves data from customers such as order history, as well as order status, all is packaged
- Experienced APIs, is the result of all unification of data in one consumable, composable and reusable endpoint.
- It is a design approach where APIs can be easily modify.
This approach means that developers does not need to create all data one more time, instead they used the available data from other APIs and build a common web service which will contain information from different sources.

## Application Network
- It refers to the connection of data like a node.
- Every new API, or node added adds more value to the network.
![](https://www.mulesoft.com/sites/default/files/What%20is%20an%20application%20network_0.JPG)
- Every node is either an API that can be data retrieve from a social network such as Facebook, Twitter, SAP, Salesforce, Workday, Oracle etc, many of them sideloaded at the same time. 

- It is build to bend, not break, recomposable or built to change.

## RESTful APIs structure

- Application Programming Interface - API
    - It provides *inputs* and *outputs* of data

## Web Services
- Is a way of communication between different systems, when providing a standard exchange of data.

    - Web Service API. Refers to how you interact  with it, it could be any type of file but ideally should implement some standard API description language sucha as RAML. 
    - Web service interface implemeting the API. Is the code providing the structure to the application so it implements the API
    - Web Service implementation itself. Is the actual code and application.

## Two main types of web Services
1. SOAP web services:
    - Traditional, more complex.
    - The communication rules are defined in an XML-based Web Services Description Language.
2. RESTful web services:
    - Recent, simpler type.
    - Use the existing HTTP communication protocol.

## Representational State Transfer - REST
- Clients and servers exchange representations of resources using the standard HTTP Protocol.
- Stateless: The server does not remember any client state from previous requests.
- Clients can cache previous responses to avoid repeated network calls.

- The HTTP request method indicates which operation should be performed on the object identified by the URL.
![](https://res.cloudinary.com/practicaldev/image/fetch/s--9G_NLci7--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1uapyaa2ob49xctta1j7.png)
![](https://ichi.pro/assets/images/max/640/1*bqTWyL7IFU4Z4xL0y4Su6A.jpeg)

## HTTP Methods

1. Is used to retrieve a collection of companies
```
(GET)/companies
```
2. Uses a query Parameter to retrieve a collection of companies based out on France.
```
(GET)/companies?country=France
```
3. Uses a URI - Unique Resource Identifier to retrieve a member of the collection with the unique ID "3"
```
(GET)/companies/3
```
4. It is used to create a new company, or collection of companies.
```
(POST)/companies  with JSON/XML in HTTP body
```
5. Deletes number 3 out of the collection of companies.
```
(DELETE)/companies/3
```
6. It is used to replace the company identified by the ID "3". 
```
(PUT)/companies/3   with JSON/XML in HTTP body.
```

|HTTP Methods| definition|
|------------|-----------|
|GET         |Retrieves the current state of a resource in some representation (usually JSON or XML).|
|POST        |Create a new resource.|
|DELETE      |Deletes a resource.    |
|PUT         | replaces a resource completely, if the resource does not exist, a new one is created.|
|PATCH       | partially updates a resource. |

## Calling RESTful web services
- Need to be able to specify the HTTP method, request headers, and request body
- Example tools include:
    - An API portal with an API console.
    - Advanced REST Client.
    - Postman.
    - A cURL command-line utility.

### 2 Types of Calls - Secured / Unsecured
- Unsecured call to APIs does not require any credentials.
- Secured call to APIs may be secured and required authentication by some credentials or tokens.
    - Often a proxy (a program that serves as gate keeper) is created to govern the access to an API.
    - Can also be secured by other authentication protocols:
        - OAuth, SAML, JWT, and more.

### Getting response from web service calls
- RESTful web services return an HTTP status code with the response.
- Status code provides client feedback for the outcome of the operation (succeded, faile updated).
![](https://softcrony.com/blog/wp-content/uploads/2020/07/http-code.png) *HTTP Status response code*

## API Design-first approach
![](https://www.mulesoft.com/sites/default/files/inline-images/image2_2.png) *API development cycle*

## Anypoint Platform
- Design Center:
    - Used for rapid Development.
- Exchange:
    - Used to collaborate, discover assets and get stakeholder feedback.
- Managment Center:
    - Used to manage parts of the application.

![](https://sumamoos.com/includes/uploads/2020/04/titan-anypoint-platform-1.png)

CloudHub: Mulesoft, self hosted environment

## Components of Anypoint Platform
There are tools for every phase of the API-Design

1. API Specification Phase tools:
    - Exchange, API Portal, API notebook, API Designer, and Mocking Service
    ![](https://miro.medium.com/max/1838/1*GXW42Ll59A8VcshcCKJ1bQ.png)
    - Exchange is the platform where APIs can be discoverable
2. API Implementation Phase tools:
    - MUnit, Anypoint Studio
    ![](https://miro.medium.com/max/1838/1*oDe2ZFHoe7Yz3ZkIMaMAAw.png)
    - Munit is used for - unit testing
    - Anypoint Studio is used to create the flows of the application, as well as debugging and testing.

3. API Management (used to create proxy applications to govern and secured the APIs by creating Policies) Phase tools:
    - API Analytics, Visualizer, Runtime Manager, API Manager, Anypoint Monitoring.
    ![](https://miro.medium.com/max/1838/1*oDe2ZFHoe7Yz3ZkIMaMAAw.png)

### REST Connectors in Anypoint Exchange
- When a RAML 1.0 API specification is added to Exchange, a *connector* is automatically created for it.
    - The connector can be used in Mule applications to make calls to an API
    - REST Connect is the name of the technology that performs this conversion.
    ![](https://www.mulesoft.com/sites/default/files/2019-08/MS_AP_Exchange_MainHeader.png) *Connectors on Exchange to make calls to APIs*

## Building Integration applications and APIs on Design Center
![](https://www.mulesoft.com/sites/default/files/2018-07/MS_AnypointPlatform_DesignerCenter_MainHeader-01__.png)

**Design Center** allows you to create integration application such as:
1. API Specification: 
    - Defines how the API will behave and how it communicates with other systems and APIs.
2. Fragments:
    - Compose snippets that can easily be reused accross multiple APIs
3. Mule Apps:
    - Design a Mule integration flow.

## Desgin Center applications
- It includes 3 applications 

|Application|Purpose|
|-----------|-------|
|Flow Designer|Web app for building integration apps that connect systems and consume APIs|
|API Designer|Web app for designing documenting, and mocking APIs|
|Anypoint Studio|Desktop IDE for implementing APIs and building integration applications|

## Creation of Mule applications with Flow Designer
Flow Designer and Anypoint Studio are Java based applications, using the Spring Framework; used for creating Mule applications with similar approaches.
- **Flow Designer** is web based application for creating Mule applications used to assemble integrations applications using visual connectors and other assets from Exchange and publishes them to CloudHub.
- **Anypoint Studio** is an IDE used to create Mule applications by adding also components and proccesors to flows, which create XML code.
    - This apps cna be published anywhere or in Mule Runtime.
- **Mule Runtime** is a lightweight Java-based enterprise service bus (ESB) and integration platform that allows developers to connect apps together quickly and easily, enabling them to exchange data.
    - Acts as a transit system for carrying data between apps (the Mule).
    - Can connect all systems including web services, JMS, JDBC, HTTP and more.
    - *Decouples point to point integrations* by having all (non-Mule) apps talk to the bus (to a Mule Runtime) instead of directly to each other.
    - *Enforces policies for API governance*

## Mule 4 applications and flows
- **Mule Application** is a set of XML files that can have multiple flows. 
**A Mule application is a sequence of Mule event procesors.**

![](https://docs.mulesoft.com/mule-runtime/4.4/_images/batch-processing-concept-d1bdd.png) 

- Mule Event Processors are organized on another processor called the **flow**.

- **Flow** is the unique thing that can be excecuted on a Mule 4 application, which includes 3 main areas:
    1. A source.
        - Controls how the flow is trigger.
    2. Process area.
        - Determines what it does.
    3. Error handling.
        - Handles the error.

## Typical Mule 4 applications
1. **Source** initiates execution of the flow.
    - Data and metadata passed to the source is subsecuently enrich, process and transformed. 
2. **Process** 

## Running Flow Designer applications
- When a Mule application is created in Design Center:
    - The application is deployed to a MuleSoft-hosted Mule runtime (called a CloudHub worker).

## CloudHub Worker
- **It is a dedicated instance of Mule that runs a single application**
    - has different memory capacity and power.

## Accessing and modifying Mule 4 event data
- When a Mule application is triggered, a data structure is created and stored internally
    - **Mule event** is the data structured, has 2 main elements:
        1. **Mule Message** , contains 2 elements:
            - **Attributes** - metadata, contains the parameter and headers.
            - **Payload** - actual data you will like to process.
        2. **Variables**

## Transforming data with DataWeave 
- DataWeave 2.0 is programming language used to transform data either from XML to JSON, Java, CSV and others.

- Transformation of data on Flow Designer is done by using the Transform component.
    - *Transform component* displays the input and output data structure.
    ![](https://docs.mulesoft.com/design-center/_images/transform-second-mappings-panel.png) *Transform Component in Flow Standard*

*Note: Using Transform component (DataWeave) to transform one source of input data, to another format of output data is as follows:*
**Example format of input data:**
```json
[
  {
    "ID": 1,
    "code": "rree0001",
    "price": 541,
    "departureDate": "2016-01-20T00:00:00",
    "origin": "MUA",
    "destination": "LAX",
    "emptySeats": 0,
    "plane": {
      "type": "Boeing 787",
      "totalSeats": 200
    }
  },
  {
    "ID": 2,
    "code": "eefd0123",
    "price": 300,
    "departureDate": "2016-01-25T00:00:00",
    "origin": "MUA",
    "destination": "CLE",
    "emptySeats": 7,
    "plane": {
      "type": "Boeing 747",
      "totalSeats": 345
    }
]
```
**Example format of output data, using Transform component (DataWeave):**
```json
[
    {
      "airline": "United",
      "flightCode": "ER38sd",
      "fromAirportCode": "LAX",
      "toAirportCode": "SFO",
      "departureDate": "May 21, 2016",
      "emptySeats": 0,
      "totalSeats": 200,
      "price": 199,
      "planeType": "Boeing 737"
    },
    {
      "airline": "Delta",
      "flightCode": "ER0945",
      "fromAirportCode": "PDX",
      "toAirportCode": "CLE",
      "departureDate": "June 1, 2016",
      "emptySeats": 24,
      "totalSeats": 350,
      "price": 450,
      "planeType": "Boeing 747"
    }
]
```
*Note: Observe that flightCode from the * *output* *it is with upper case, also data structure is simplier to read and consume, less nested as in the *input*.

### Sumary of Module 2
- **Anypoint Exchange**: 
    - Acts as a central repository for assets so they can be discovered and reused.
- **Flow Designer**:
    - Is a visual way of construction for integration applications.
- **Mule runtimes**: 
    - Is a Java based service bus and integration platform that allows connection of NonMule applications carrying data to Mule applications for integration.
        - Also Mule runtimes can be hosted on CloudHub workers, or Customer-Hosted in the cloud or in Server of the client.
- **DataWeave 2.0**:
    - Is the language that allows APIs on different formats that contain data either as Java objects, JSON, XML, CSV and other types of data to be transformed on other types of data or rearrange to be consumed.
    - Can also access, query, and transform Mule 4 event data.
-------

## Designing Modern APIs
- **Spec driven development**: Is a process where your application is built in two-distinct phases:
    1. The creation of a spec (the design phase).
    2. Development of code to match the spec (the development phase).
- This API Specification is created using a standarizing API description language (RAML).
    - This can be tested with users without writing any code.
    ![](https://www.mulesoft.com/sites/default/files/2021-11/MS_Anypoint_API_Designer_v2.png) *View from an example of API specification using API designer from Anypoint Platform*

### Cycle of an API Spec (RAML)
- ![](https://anbukamalforu.files.wordpress.com/2018/01/apidesignlifecycle.png) 
    - **API designer** features an embedded code editor for the *design of the API Spec* to write RAML code.
    - **API Console** and **Mocking Service** *serves as a Simulation state* where you can try (using example data) and visualize the endpoints, as well as different HTTP query methods defined before on the API Designer.
    -----
    *Note: When the API Specification is ready to be share to a broader audience, can be publish to Exchange*
    - **Exchange** is a web repository for discoverable assets such APIs, connectors and more, the API Spec designed and tested on the *Desgin* and *Simulates* phases, can be published here so more people can try it in order to get feedback.
    - **API Portal** is a web page intended for developers to access to API Spec to test it and provide feedback as well as visualize it graphically.

## Options for defining the API Spec (RAMl)
There are several approaches available, for designning APIs.
1. Hand coding, it was the initial approach for developers to build the API.
2. API blueprint
3. Swagger, OpenAPI Spec.
4. RAML, is open source, supports inheritance and easy to read human syntaxis.

## Introduction to RAML - RESTful API Modeling Language
- Is used to define the API Specification.
- Is simple, structured, and succint (clear and short) way of describing RESTful APIs.
- It is entirely modular.
- Encourages reuse. 
- Can be used to autogenerate documentation, mock endoints, and intefraces for API Implementation
- Is based on YAML.

### RAML Syntax - Resources and Methods
- **Resources** are all the nodes that begin with a slash `/something`
    - they are obejcts identified by the web serivec UTL that you want to act upon using HTTP method used for the request.
    - Any methods and parameters nested under a resource belong to and act upon that resource.
    - **Nested Resources** are used to select members from a collection (URI parameters)
        - URI parameters are enclosed in curly braces ``{}``
```yaml
#%RAML 1.0
version 1.0
title: American Flights API

/flights:
    get:
    post:

    /{ID}:
    get:
    delete:
    put: 
        responses:
            200:
                body:
                    application/json:
``` 
- `/{ID}` is the **nested resource** definition, which is designed to retrieve a single flight out of the list of flights.

### Using API Designer to define API Spec (RAMl)
![](https://www.mulesoft.com/sites/default/files/2021-11/MS_Anypoint_API_Designer_v2.png)*API Deisgner User Interface*
- File Browser, to search files or paths.
- Editor.
- Shelf, adds code depending on the context you are writting code on the Editor or where your cursor is located.
- API Console, to visualize the autogenerated documentation of HTTP methods added to the API Spec using RAML.

```yaml
#%RAML 1.0
title: API_Spec_American_Flights_API
# Rsource /flights
/flights:

    # GET method
  get:
    # queryParameters used on the URL /flights?destinitation=SFO
        # destinitation=LAX
        # destinitation=CLE
    queryParameters:
      destination:
        required: false
        enum:
          - SFO
          - LAX
          - CLE
    # POST Method
  post:
  
  # Nested Resource, used on the URL to identify a single member (flight) from a collection of flights
  # /flights/3
  # /flights/50
  /{ID}:
    #GET Method
    get:
    # POST method  
    post:
    # DELETE method  
    delete:
      
```
## Testing API design without writting code
- *API Console* is graphical way of visualizing the API and the different HTTP Methods
    - It is available through:
    - **API Designer** - so the API Designer can test.
    - **API Portals in Exchange** - so users/developers can test it.
- *Mocking Service* is a test URL to share links for stakeholders (developers).
    - This allows to make calls to the mocked API.

## Using RAML to define specifications for requests and responses
- This is used to define for requests and responses.

### Defining the responses details with RAML
- Responses must be of one or more HTTP status codes.
- For each response, specify posible return data types along with descriptions and examples.
```yaml
    /{ID}:
        get:
            responses:
                # HTTP status succes code 200
                200:
                    # body definition
                    body:
                        # media type of application json
                        application/json:
                            # return data type
                            type: AmericanFlight
                            # inline definition of return data
                            examples:
                                output:
                                    ID: 1
                                    code: ER38sd
                                    price: 400
                                    departureDate 2017/0726
                                    origin: CLE
                                    destination: SFO
                                    emptySeats: 0
                                    plane: 
                                        type: Boeing 737
                                        totalSeats: 150
```

### Defining Request definitions
- Specify the posible request data types along with descriptions and examples.
```yaml

/flights:
    get:
    post:
        # body definition
        body:
            # media type of application json
            application/json:
                # Request data type American Flight
                type: AmericanFlight
                # inline definition of request data
                examples:
                    input:
                        code: ER38sd
                        price: 400
                        departureDate: 2017/07/26
                        origin: CLE
                        destination: SFO
                        emptySeats: 0
                        plane: 
                            type: Boeing 737
                            totalSeats: 150

``` 
#### Specifying examples on inline definitions
- There are 2 types of facets you can use to specify example data:
    - **example** represents a single instance of the data.
    ```yaml
    type: User
    example:
        name: Bob
        lastname: Marley
    ```
    - **examples** represents multiple instances of data as a map of key-value pairs
    ```yaml
    type: User
    examples:
        person1:
            name: Paul
            lastname: McCartney
        person2:
            name: Lady
            lastname: Gaga
    ```
## Modularizing APIs by using RAML Fragments
- Use Fragments of APIs that are RAML code that can be discovered on Exchange and or imported to the API Specification (RAML) as RAML files
    - Such files encourages reusable fragments which can be:
        - **Data types**, **examples**, traits, resource types, overlays, extentions, security schemes, documentation, annotations and libraries
        - **Fragments can be stored** in:
            - Different folders and files within a project.
            - Seperate API fragment project in Design Center.
            - In a seperate fragment in Exchange.

**Adding a data type on API designer**
Once imported the ``Training American  Flight data type`` and ``Training  American Flights Example`` RAML Framents to the Explorer files within API designer:
1. Add the following data type at the begining of the ```Root file``-API specification RAML

**API Specification RAML**
```yaml
#%RAML 1.0
title: API_Spec_American_Flights_API

#This is added to import from within the files of the Explorer using the special word !include
types:
  AmericanFlight: !include /exchange_modules/68ef9520-24e9-4cf2-b2f5-620025690913/training-american-flight-data-type/1.0.1/AmericanFlightDataType.raml
  
/flights:

  get:
    queryParameters:
      destination:
        required: false
        enum:
          - SFO
          - LAX
          - CLE
```
2. Specify **Response** to the /flights:get method to return an array of AmericanFlight objects
    - responses > 200 > body > application/json > type > AmericanFlight
```yaml
/flights:

  get:
    queryParameters:
      destination:
        required: false
        enum:
          - SFO
          - LAX
          - CLE
    responses:
        # response for the request 200 success status code
        200:
            body:
            application/json:
                type: AmericanFlight[]
```
3. Add an example response for the /flights:get method
- Locating the **path** for `AmericanFlightsExample.raml` that contains an example of flights to respond.
**exchange_modules/training-american-flights-example/1.0.1/AmericanFlightsExample.raml**
```yaml
#%RAML 1.0 NamedExample
value:

  - 
    ID: 1 
    code: ER38sd
    price: 400
    departureDate: 2017/07/26
    origin: CLE
    destination: SFO
    emptySeats: 0
    plane: 
      type: Boeing 737
      totalSeats: 150
  - 
    ID: 2 
    code: ER45if
    price: 540.99
    departureDate: 2017/07/27
    origin: SFO
    destination: ORD
    emptySeats: 54
    plane: 
      type: Boeing 777
      totalSeats: 300

```

- In this step should add the response of 2 flights:
```yaml
/flights:

  get:
    queryParameters:
      destination:
        required: false
        enum:
          - SFO
          - LAX
          - CLE
    responses:
      200:
        body:
          application/json:
            type: AmericanFlight[]
            #examples that represents multiple instances of data 
            examples:
              output: !include /exchange_modules/68ef9520-24e9-4cf2-b2f5-620025690913/training-american-flights-example/1.0.1/AmericanFlightsExample.raml
```
4. Specify the /{ID}:get method to return an AmericanFlight object
    - In the editor, indent the /{ID} resource get method.
    - In the shelf, click responses > 200 > body > application/json > type > AmericanFlight.
```yaml
  /{ID}:
    get:
      responses:
        200:
          body:
            application/json:
              type: AmericanFlight
```
5. Define an example response for the /{ID}:get method in new folder
    - Create a folder at the main path, named it `examples`
    - in pc local files, search for  `Student_files\resources\examples\AmericanFlightExample.raml` and this should contain information for 1 flight.
*Now the body response for /{ID} should be accessible from API Designer console*
- When trying it should retrieve the same flight object since it was hard coded even though you use different URI parameters.

6. Specify the /flights:post method request to require an AmericanFlight object
    - In the editor, under /flights post method add the body > application/json > type: AmericanFlight
    ```yaml
        post:
        body:
            application/json:
            type: AmericanFlight
    ```
    - Create a new file within API Designer `examples/AmericanFlightNoIDExample.raml` deleting the ID key value pair which should have the same content as `examples/AmericanFlightExample.raml` as the following code:
    **./examples/AmericanFlightNoIDExample.raml**
    ```yaml
    #%RAML 1.0 NamedExample
    value:
        # Deleted "ID" key-value pair
        code: ER38sd
        price: 400
        departureDate: 2017/07/26
        origin: CLE
        destination: SFO
        emptySeats: 0
        plane: 
        type: Boeing 737
        totalSeats: 150
    ```
    - Adding the the instance `examples` treats as the input type of data.
    ```yaml
        post:
            body:
                application/json:
                type: AmericanFlight
                examples:
                    input: !include examples/AmericanFlightNoIDExample.raml
    ```
    - Specifying an example response for the /flights:post method
        - adding response > 201 > body > application/json > example > input: !include *./path_of_the_file*
        ```yaml
            post:
                body:
                    application/json:
                    type: AmericanFlight
                    examples:
                        input: !include examples/AmericanFlightNoIDExample.raml
                responses:
                    201:
                    body:
                        application/json:
                        example:
                            message: Flight added (but not really)
        ```

## Engaging with Users when publishing the API Specification (RAML)
- When publishing the API Specification on Exchange an API Portal is created so it allows:
    - Get feedback from developers on ussability and functionality.
    - Either public the API Spec for internal developers or public for external developers.
    - **API Portals** are automatically created for REST APIs added to Exchange
        - An **API Console** is also added for consuming and testing APIs within the same browser without a REST Client application.
        - An **automatically generated API endpoint** that uses **mocking service** to allow the API to be tested without having to implement it.

-----
## Creating an API specification with RAML
Tasks / Requirements
1. Create a RAML 1.0 specification.
2. Add a method to retrieve customer accounts.
    - Inputs:
        1. The person or system requesting the data
        2. An optional account type to fetch personal or business accounts
        3. An optional name to identify the accounts belonging to a particular customer
    - Outputs:
        1. A JSON array of accounts; each account contains: 
            - ID, a positive integer identifier
            - Name, a string value identifying either the name of the individualor company
            - Type, either business or personal
            - Address, a CSV string value containing the address,e.g.,``12345 GreenSt,Boulder,Colorado,82433,USA``
            - Air Miles, a positive integer value indicating the air miles accrued
            - Creation Date, a timestamp identifying the date and time the account was created
3. Add a method to create customer accounts.
    - Inputs:
        1. The person or system creating the data
        2. A JSON array of accounts; each account contains: 
            - Name, a string value identifying either the name of the individual or company
            - Type, eitherbusinessor personal
            - Address, a CSV string value containing the address
            - Air Miles, a positive integer value indicating the air miles accrued
    - Outputs:
        1. Success:
            - A literal JSON object containing: ``{"message": "Accounts created"}``
4. Document your specification where appropriate.
5. Create types and examples where necessary.
6. Organize your specification in folders and files.
7. Publish to Exchange.

    ### Creating a RAML Spec and adding the method to retrieve customer accounts

    ```yaml
    #%RAML 1.0
    title: Customer_accounts
    # types are the definition of what types of data are the output going to throw
    types:
        Account: !include dataType/accountDataType.raml
    # Defining the Resource /accounts
    /accounts:
        # Method for retrieving data: GET
        get:
            # Query Paramters: used to filter a condition
            queryParameters:
                # 2. optional account type to filter
                accountType:
                    required: false
                    # enum: list of conditional constants on the request
                    enum: 
                        - personal
                        - business
                # 3. optional name belonging to a particular customer
                name:
                    required: false
        # 2. Outputs of the the GET request 
        responses:
            # 200 if it is a Successful call or request to the API
            # 200: is also metadata from the server
            200:
                # body: what will be contained when requested data
                body:
                    # type of output data
                    application/json:
                        # type: Account[] refers to the structure of data that will be the output taking a data type in count
                        type: Account[]
                            # examples: defines that the instance of data whill be multiple objects
                            examples:
                            # output is the keyword to tell what the data of the body will contain
                            output: !include accounts/accountsExampleResponseGET.raml
      post:
        description: Create accounts
        #headers: will be the metadata to identify the person or system trying to modify data
        headers:
            # user_id is a requiered field in order to acces the operation
            user_id:
        body:
            application/json:
                type: Account
                example:
                input: !include accounts/accountExamplePost.raml

        responses:
            201:
                body:
                    application/json:
                        example:
                            message: Accounts created
    ```
-------
