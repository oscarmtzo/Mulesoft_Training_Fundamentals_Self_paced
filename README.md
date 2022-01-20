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
## Stages of Building an API
1. **Build of API implementation**: The API Specification (RAML) created before, can be used in this stage to build the API implementation.
2. **Testing the API implementation**: a rest client like Adavanced REST Client can be used to call the API implementation, also cna be used Postman as well as others.

    ----
    - Later in this module the following topics will be covered.
        - Using Anypoint Studio to build, run, and test Mule applications.
        - Use a connector to connect to databases.
        - Use the graphical DataWeave editor to transform data.
        - Create RESTful interfaces for applications from API specifications.
        - Connect API interfaces to API implementations.
        - Syncronize changes to API specifications between Anypoint Studio and Anypoint Platform.
## Mule 4 applications and flows anatomy
![](https://ingenierobinario.com/wp-content/uploads/2020/10/MuleFlow.png)
- Mule applications *receive events*, process them, and route them to other endpoints.
- Mule applications accept and process a Mule event through a series of Mule events processors plugged together in a flow with
    - **Mule event source** defines how the flow will be triggered 
    - **Mule event processor** specify how to transform, filter, enrich, and process the event data.
    
    ### Mule 4 event structure
    ![](https://i1.wp.com/thebasictechinfo.com/wp-content/uploads/2021/05/mule_soft_event.png?resize=841%2C412&ssl=1) *Mule 4 event structure*

    - Mule event contains:
        - Mule message object
            - Attributes: contain metadata such as the ones found at the header of an http request, like http method, query parameters and so on.
            - Payload: will contain the actual data you are about to process and that the end user can visualize.
        - Mule variable object
## Creating Mule applications with Anypoint Studio
- Anypoint Studio
    - Based on the Eclipse IDE, allows you to build Mule applications either with graphical view interface or an XML editor.
        - XML then can be executed and deployed in the Mule Runtime.
    - Include pre-built functionality which allows you to connect to all types of APIs (REST, SOAP), protocols (HTTP, FTP, SMTP & more) and popular services (Salesforce, Workday & more).
    - Allows you to transform data to structures
    - Allows you to sync, edit and upload API Specifications with Anypoint Platform
    - Can also run, debug and deploy Mulesoft applications 
    - Be able to create common integration patterns 
    - Utilize Maven Repositories for continuous build processes

    ------
    ### Anypoint Studio User Interface
    ![](https://docs.mulesoft.com/studio/6/_images/blank-canvas.png) *Anypoint Studio User Interface perspective of Design*
    - Has 3 perspectives:
        1. Debugging perspective.
        2. API development perspective.
        3. Design perspective.
            - Canvas: is meant to show the Mule flow of an application.
                - Can display a graphic view of the application flow, or an XML file editor.
            - Package Explorer: used to display project files.
            - Mule Palette: display the modules added to project and each one with their processors
            - Console: display important information like:
        - All are customizable.
        -----
        ### Anatomy of a flow: Visual
        ![](https://1.bp.blogspot.com/-W57UvZm6Qgo/Xv25YDKJFfI/AAAAAAAAKgQ/KEO5-JWCsj4WT9V2pDoNykCTzIocna0aQCLcBGAsYHQ/s1600/030201%2BAnatomy%2Bof%2Ba%2Bflow%2B-%2Bvisual.png) *Anatomy Visual Flow*
        - As you confiigure the flow, XML code is generated in the Configuration view Tab
        - Mule applications are built using the processors from the modules added to the Palette.
        ------
    ### Mule runtime embedded within Anypoint Studio to run Mule apps
    - It is used to test applications without leaving Anypoint Studio.
    - Helps viewing the messages generated when the project is deploying and running. 
        - A message of **Status DEPLOYED** means you can start testing the Mule application.
        - A message of **Status FAILED** you can scroll up in the console to check error messages

## Connecting to database within Anypoint Studio 
- It uses a `Database Connector` that can connect to almost any JDBC relational database.
    ![](https://docs.mulesoft.com/mule-runtime/4.4/_images/studio-palette.png) *Anypoint Studio Palette*
    - Any database engine for which you have a driver.
    - Just add the `Database` module to the project, the connectors are the operation for the database.
    ![](https://docs.mulesoft.com/db-connector/1.11/_images/database-select-operation-1.png)*Query a Database Examples  - Mule 4 | Mulesoft Doc*
    
- There is a *global configurations elements view* under the canvas
    - Its purpose to create reusable connector configuration for most of the modules that have connections 
    - Contain a shared configuration settings for the modules processors:
        - When you add the Database module you will be able to perform operation on the data that contain in the various tables of the database. 
        - For each operation you will need to specify:
            - Name of the database.
            - The kind of database it is.
            - How to connect to it.
        ![](https://dz2cdn1.dzone.com/storage/temp/9908694-db4.jpg)***Global Element Configurations tab > Global Element Properties*** *MySQL Database SELECT query operation in Mule 4*
    - For this, it is needed to create a *global configuration element* to perform a SELECT query to a MySQL database
        - Test Connection to verify the correct functionality.
## Transforming Java data from Database to JSON to be consumed by REST Client
- The purpose is to transform the `media type` that came from the query to the database to a different standard format in order to be consumed.
- It is performed by a ``Transform Message`` connector found at the Mule Palette.
![](https://i.stack.imgur.com/dkyXR.png)*Transform Message processor from the Mule Palette*

- **Transform Message** transforms data to different types using a transformation language named **DataWeave 2.0**.
    - It is provided with a graphical interface with payload-aware development
    - DataWeave Playground lets developers mock data transformations based on an input payload outside Anypoint Studio in a web browser.
        - Offers a tutorial
        - https://developer.mulesoft.com/learn/dataweave/ *DataWeave Playground*
    - It uses output metadata type to add in order to map the input payload to a different one
    **Input data queried from MySQL Database**
    ```java    
    %dw 2.0
    output application/java 
    ---
    [{
        ID : 32,
        code1 : "consequatur,",
        code2 : "velit",
        airlineName : "dolorem",
        toAirport : "magni",
        fromAirport : "quia",
        takeOffDate : |2005-05-16|,
        price : 37.13,
        planeType : "enim",
        seatsAvailable : 83,
        totalSeats : 9,
    },
    {
        ID : 12,
        code1 : "nesciunt.",
        code2 : "occaecat",
        airlineName : "sint",
        toAirport : "mollit",
        fromAirport : "dolorem",
        takeOffDate : |2019-11-06|,
        price : 7.67,
        planeType : "non",
        seatsAvailable : 74,
        totalSeats : 98,
    }]
    ```

    **DataWeave 2.0 language within Transform Message dialogue box**
    ```dataweave
    %dw 2.0
    output application/json
    ---
    payload map ( payload01 , indexOfPayload01 ) -> {
        ID: payload01.ID,
        code: (payload01.code1
    default "") ++ (payload01.code2 default ""),
        price: payload01.price default 0,
        departureDate: payload01.takeOffDate as String default "",
        origin: payload01.fromAirport default "",
        destination: payload01.toAirport default "",
        emptySeats: payload01.seatsAvailable default 0,
        plane: {
            "type": payload01.planeType default "",
            totalSeats: payload01.totalSeats default 0
        }
    }
    ``` 
    **JSON format after transformation from Java to JSON using DataWeave 2.0 language from the Transform Message**
    ```json
    [
        {
            "ID": 1,
            "code": "rree0001",
            "price": 541,
            "departureDate": "2016-01-19T18:00:00",
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
            "departureDate": "2016-01-24T18:00:00",
            "origin": "MUA",
            "destination": "CLE",
            "emptySeats": 7,
            "plane": {
            "type": "Boeing 747",
            "totalSeats": 345
            }
        }
    ]
    ```

    *Note: the key-value pairs from planeType and totalSeats of the input had been reused and transform to a nested JSON object under the key "plane" of the output, thanks to DataWeave 2.0 and Transform Message Mule event proccessor*
    
    -----
## Creating RESTful interfaces manually for Mule applications
- Once having the core functionality of the Mule application implemented, now it has to be exposed as RESTful web service.
    - *RESTful interface for an application*: will have listeners for each resource `/` method  defined by the API
        - ``GET: /flights``
        - ``POST: /flights/{ID}``
        - ``DELETE: /flights/{ID}``
        - ``PUT: /flights/{ID}``

    ### Developing the listener endpoint to retrieve or input data using a URI parameter
    - When querying a resource not develop the following error is the output from a REST Client (Advanced REST Client - ARC, Postman):
    ![](https://help.mulesoft.com/sfc/servlet.shepherd/version/renditionDownload?rendition=ORIGINAL_Png&versionId=0682T000009YJIX&operationContext=CHATTER&contentId=05T2T00000sITBZ)*Error example on of a non developed listener endpoint*

    - Example error on Advanced REST Client when requesting ID 3 from the Flights with GET method at `http://localhost:8081/flights/3`
        ```
        GET /flights/3 HTTP/1.1
        Host: localhost:8081
        ```
    - To solve this issue we must create an endpoint with all the previous components which were:
        - **Mule event Source**: HTTP Listener
        - **Mule event processors**: SELECT by ID from database connector, Transform Message (transform the output data from db on Java object format to JSON) using DataWeave 2.0.
    - **Steps for implementing an URI Parameter based endpoint:**
        1. Create a new flow with:
            - HTTP Listener, with path set to `/flights/{ID}`.
            - SELECT processor with SQL query to ID `SELECT * FROM american WHERE ID = 1` (this will always query the first element from ``db``).
            - Transform Message processor, to set a valid format for the succesful response of the query from Java Object format to JSON.
        2. Transform message output metadata should be define to the previously american_flights_json ( outputs only 1 flight wihtin an array) in order to display it with nested JSON format like this one when deployed and query it from a REST client:
        ```json
        [
            {
                "ID": 1,
                "code": "rree0001",
                "price": 541,
                "departureDate": "2016-01-19T18:00:00",
                "origin": "MUA",
                "destination": "LAX",
                "emptySeats": 0,
                "plane": {
                "type": "Boeing 787",
                "totalSeats": 200
                }
            }
        ]
        ```
        3. In order to add the logic to query the requested ID dynamically SQL Query Text and Input Parameters from the SELECT processor should be modify to:
            - SQL Query Text:
            ```sql
            SELECT *
            FROM american 
            WHERE ID = :ID
            ```  
            - Input Parameters `fx` on:
            ```js
            {'ID': attributes.uriParams.ID}
            ```
            *Note: accessing to the Mule Message > Attributes > uriParams from the input Tap* allow us to access the URI Parameter we need for the ID.
        4.- Requesting any ID using a REST client to the path, for example: ``http://localhost:8081/flights/3``; would give us any ID and its data we want.
        *Example output data:*
        ```json
        [
            {
                "ID": 3,
                "code": "ffee0192",
                "price": 300,
                "departureDate": "2016-01-19T18:00:00",
                "origin": "MUA",
                "destination": "LAX",
                "emptySeats": 0,
                "plane": {
                "type": "Boeing 777",
                "totalSeats": 300
                }
            }
        ]
        ```
        -------
        #### Developing the POST requests
        - Creating another flow to POST or create new flights, will be using the similar configuration:
            - HTTP Listener-*Mule event source*
            - 
        - **Steps to create enpoint for POST flights**:
            1. Drag and drop, in a new flow; an HTTP Listener 
                - Flows' display Name can set to POST_flights for easy identification.
                - HTTP Listener *connector configuration* should be set to the existing *HTTP_Listener_config* 
                - Set Path must be: ``/flights`
                - within HTTP Listener, on the *Advanced* tab, *Allowe methods* must be set to `POST`
            2. Add to the flow *Set Payload* processor, this will **output** to the REST Client console a generic and hard coded message of a flight created.
                - within general *Set Payload* tab > settings > value > `fx` (set to literal mode):
                    `{"message": "Flight added (but not really)"}`
            3. Requesting POST method on REST client to the defined path (`/flights`), results on a succesful operation 200 with the response message defined before.

## APIKit for generating RESTful interfaces automatically
- APIKit and API Specification (RAML) will be used to create automatically the RESTful interfaces (endpoints, eg. GET,POST /flights and GET /flights/{ID}).

    ### APIKit
    - Is an open-source toolkit that includes an Anypoint Studio plugin 
    - The **Anypoint Studio APIKit plugin** can generate an interface automatically from a RAML API definition
    - It can be used for generating Mule flows for each of the message and API Specification and stored them in a new Mule configuration file.
    - It creates a flow for the **APIKit Router and Console**  
        - **APIKit Router**: is the main entry point to call a Mule application 
        - **APIKit Console**: is used for testing the application just like it is on Exchange and on API Designer.
    - The generated flows represent the RESTful API interface and can be hooked to the implementation hub using **Flows Reference Processors**. 
    ### Using the APIKit Router to import the API Speficiation from Exchange and build the API Interfaces (GET, POST /flights endpoint)

    - At the File Explorer, right click on the current project > Manage Dependencies > Manage APIs
        - Add new dependency ➕ > From Exchange 
        - Search for `American Flight API` and click on add, select version 1.0.1
        - ``Apply and Close``
        -  When asked to scaffold selecte `Yes`
        *Note: there will be added new files to the project including ``./APIKit`` with several files as shown here:*
            - ![](https://miro.medium.com/max/665/0*vs2o1enRx92RxiBy)
            - Inside `./American Flights API` you will find `.raml` files that were worked on API Designer
    - Examining the generated `american-flights-api.xml` file we cna see 4 flows:
        - delete: /flights/{ID} 
        - ``get: /flights`` 
            Transform Message output preview
            ```json
            %dw 2.0
            output application/json
            ---
            [
            {
                ID: 1,
                code: "ER38sd",
                price: 400,
                departureDate: "2017/07/26",
                origin: "CLE",
                destination: "SFO",
                emptySeats: 0,
                plane: {
                "type": "Boeing 737",
                totalSeats: 150
                }
            }, 
            {
                ID: 2,
                code: "ER45if",
                price: 540.99,
                departureDate: "2017/07/27",
                origin: "SFO",
                destination: "ORD",
                emptySeats: 54,
                plane: {
                "type": "Boeing 777",
                totalSeats: 300
                }
            }
            ]
            ```

        - ``get: /flights/{ID} ``
            Transform Message Preview
            ```json
            %dw 2.0
            output application/json
            ---
            {
            ID: 1,
            code: "ER38sd",
            price: 400,
            departureDate: "2017/07/26",
            origin: "CLE",
            destination: "SFO",
            emptySeats: 0,
            plane: {
                "type": "Boeing 737",
                totalSeats: 150
            }
            }
            ```
        - post: /flights 
            Transform Message Preview
            ```json
            %dw 2.0
            output application/json
            ---
            {
            message: "Flight added {but not really}"
            }
            ```
            ------
    - Examine the main flow and it's HTTP Listener
        - HTTP Listener: in the Listener properties view, notice that the connector configuration is the existing  HTTP_Listener_config and that the path is set to ``/api/*` (when clicking on the connector configuration ➕, should see the same port 8081 used as the HTTP Listener created previously).
        *Note: The * is a wildcard allowwing any characters to be entered after the /api/*.
    - Removing the Listeners from the `training4-american-ws.xml`
        - deleting the HTTP Listeners from GET, POST and GET by ID.
    ### Using APIKit Console to test the application endpoints as on Exchange and API Designer
    - Saving the file after been deleted the HTTP_Listeners
    ![](https://help.mulesoft.com/sfc/servlet.shepherd/version/renditionDownload?rendition=THUMB720BY480&versionId=0682T000006LSTI&operationContext=CHATTER&contentId=05T2T00000cNPSm&page=0)*Button with URL to APIkit console web page view*
    - Redeploying will let ``APIkit Console`` to load the changes and let you open the console for testing purposes opening a web page similar to what are found on Exchange or API Designer at http://localhost:8081/console/ .

    - When testing with a REST Client, should be using http://localhost:8081/api/flights instead of http://localhost:8081/flights
        - Since imported API Specification (american-flights-api.raml) the current path changed to `/api/*` that is the reason to use the wildcard for selecting everything that was before on the path.

## Connecting the API interface (GET /flights) to the implementation flows
![](https://docs.mulesoft.com/mule-runtime/4.4/_images/flowref-about-8b5d1.png) *Flow Reference component*
- Large Mule flows can be broken down to multiple smaller flows to promode code reuse, it also makes them easier to read and maintain.

![](https://docs.mulesoft.com/mule-runtime/4.4/_images/mruntime-flow-ref-create.png)*Flow Reference on Anypoint Studio*
- Flows can be connected one to another using *Flow Referencess*
    - **Flow References** are processors which can call another flow by name.
        ![](https://miro.medium.com/max/664/1*iT9Egtm3Mfo1lriyPtgEpA.png) *How Payload, variable, and attributes behave when passing through differen flows in Anypoint Studio -Medium*
        - When call is made, the mule event is passed to the child flow and when the child flow completes processing it passes back the mule event to the calling flow.
    ------
    ### Build a RESTful API for the American Flight Database by connecting the interface (GET flights) using Flow References to call the backend functionality 

    - In the file explorer, rename the `american-flights-api.xml` file to ``inteface.xml``.
    - Rename the `training4-american-ws.xml` file to `implementation.xml`
    -----
    ### Using a Flow reference in the /flights resource
    - Open the `interface.xml`.
    - Delete the Transform message component int he  ``get:\flights` flow.
    - On the Mule Palette, drag and drop the *Flow Reference* processor to the ``get:\flights` flow.
    - Name the *Flow Reference* to getFlights
    *Note: make sure it links to the implementation.xml get endpoint*

    ### Using a flow Reference in the /flights/{ID} resource
    - Delete both Transform Message components in the `get:\flights\{ID}` flow.
    - On the Mule Palette, drag and drop the *Flow Reference* processor to the ``get:\flights` flow.
    *Note: make sure it links to the implementation.xml get  by ID endpoint*

    ### Examine the referenced flows 
    ![](https://static.wixstatic.com/media/e0d344_da3acc88f2914ceca7bf27cfdf1cb9af~mv2.png/v1/fit/w_320%2Ch_627%2Cal_c/file.png) *Contextual menu, Reference By*
    **GET Reference By**
    - Opening the ``implementation.xml``, and right click on the `getFlights` flow, > Referenced by > double click on the ``GET interface .xml`` file

    **GET by ID Reference By**
    - Opening the ``implementation.xml``, and right click on the `getFlights` flow, > Referenced by > double click on the ``GET by ID interface .xml`` file
    ----
    - Save all, re deploy, and test it with a REST client.
        - When calling for GET flights, should have the same result as not referencing flows
        *Example output of a reference flow call to our Mule application using REST Client*
        ```json
                    
        [
            {
                "ID": 1,
                "code": "rree0001",
                "price": 541,
                "departureDate": "2016-01-19T18:00:00",
                "origin": "MUA",
                "destination": "LAX",
                "emptySeats": 0,
                "plane": {
                "type": "Boeing 787",
                "totalSeats": 200
                }
            },
            ......
            
            {
                "ID": 10,
                "code": "eefd4511",
                "price": 900,
                "departureDate": "2016-01-14T18:00:00",
                "origin": "MUA",
                "destination": "LAX",
                "emptySeats": 100,
                "plane": {
                "type": "Boeing 777",
                "totalSeats": 300
                }
            },
            {
                "ID": 11,
                "code": "rree4567",
                "price": 456,
                "departureDate": "2016-01-19T18:00:00",
                "origin": "MUA",
                "destination": "SFO",
                "emptySeats": 100,
                "plane": {
                "type": "Boeing 737",
                "totalSeats": 150
                }
            }
        ]
    
        ```
## Synchronizing changes to API Specifications (RAML) between Anypoint Studio and Anypoint Platform
- API Sync is a feature within Anypoint Studio that enables you to follow API lifecycle development practices by offering offline editing to API Specification from Anypoint Studio.
    - After editing you are able to push the edited file to Design Center.
    - Can also publish the new API asset version to Exchange.

![](https://docs.mulesoft.com/studio/7.11/_images/compare-to-index-view.png)*API Design Perspective within Anypoint Studio*
- **API Design Perspective**: includes a Git Staging tab, that lets you see changes in the editing pipeline and resolves conflicts when needed by a Git version control system.
    - Git staging tab allows to correctly Push, pull and merge.

    ### Edit an API within Anypoint Studio, push changes to Design Center 
    - Make the imported API Specification (RAML) editable in Anypoint Studio in a new API project
    - Open the `american-flights-api.raml`, trying to make changes should NOT be allowed to make any changes.
    - To edit them use the contextual menu over the `american-flights-api.raml` > American Flights API > Edit API Specification.
    - When asked to change perspective to ``API Design Perspective`` accept.
    - **Locate the new API project created in Anypoint Studio**
        - `./american-flights-api/american-flights-api.raml` (should have opened automatically when changing view to API Design Perspective).
    - Add the -/{ID} Put method from ``snippets.txt``
        ```yaml
        * American Flights API - /{ID} PUT method
        put:
            body:
                application/json:
                    type: AmericanFlight
                    examples:
                        input: !include examples/AmericanFlightNoIDExample.raml
            responses:
                200:
                    body:
                        application/json:
                        example:
                            message: Flight updated (but not really)
        ```
        - Save the file.
        - **Review the Git Staging view for the API project** > Git stagging tab.
        - Examine the unstagged changes, you should see that the `american-flights-api.raml` it is not currently on the *Stagged Changes* area.
        - Click in the *Add files* button ➕, to add `american-flights-api.raml` file to the stagged area
        - Commit the changes *Added PUT method* 
        - Push the commited changes.
    ### Publish the modified API to Exchange from Anypoint Studio
    - On Anypoint Studio, in the Package Explorer > right click to american-flights-api project > Manage API Specification > Publish to Exchange
    - Set the version to `1.0.2`
    - Click finish.
    - Close the project and view of current project.
    ### Update the version of the API used in the Mule project and rescaffold the flows
    - Right click on American Flights API in the ``training-american-ws`` project and select American Flights API > Update Version > Update version > Apply and Close
    - When promted to scaffold select 'Yes'
    *Note: When returning to `ìnterface.xml` flows, you should now see 5 methods (GET, GET by ID, DELETE, POST, PUT)*

## Sumary from Building APIs
- **Anypoint Studio** can be used to build Mule applications for integrations and API implementations (RAML)
    - Two way editing between graphical and XML views.
    - An embedded Mule runtime for testing applications.
- **Mule Applications** accept and process events through a series of event processors plugged together in a flow
    - Use an **HTTP Listener** as an inbound endpoint (final starting point) to trigger a flow with an HTTP request.
    - Use the **Set Payload** transformer to set the payload.
    - Use a **Database** module with a SELECT connector to connect to JDBC databases.
    - Use **DataWeave** and the **Transform Message** component to transform messages from one data type and sturcture to another.
- **Create RESTful interfaces** for applications
    - Manually by creating flows with listeners for each resource/method pairing 
    - Automatically using Anypoint Studio and **APIkit**
        - APIkit consists on API console and API router
- **API Sync** uses Git digital version system to syncronize changes to API specifications between Anypoint Studio and Anypoint Platform.

    ### Implementing a REST API using APIkit
    **Objectives**
    In this exercise, a REST API that has a RAML specification is implemented using APIkit
    - Create a new project in Studio.
    - Scaffold flows using the Accounts API specification.
    - Add an implementation for the accounts retrieval method.
    - Organize flows appropiately.
    Tasks / Requirements
    1. Create a new Mule project.
    2. Use the Accounts API specification to scaffold the interface of your application.
    3. Implement theaccounts retrievalmethod:
        - Connect to the following database:
            - JDBC URL: ``jdbc:mysql://mudb.learn.mulesoft.com:3306/training?user=mule&password=mule``
            - JDBC driver: Latest version of the MySQL JDBC Driver
                 - Hint: Search for "mysql-"
            - JDBC class name: ``com.mysql.cj.jdbc.Driver``
            - Table name: ``flights_customers``
        - Transform the data returned from the database to reflect the output format in the spec.
            - Note that it is your responsibility to create sample data for the output column in your transformation
                - Hint: You could use the API Console to get a list of JSON objects to create the sample data
        - Ignore the implementation of the name and account type filtering of the data for the time being, you will revisit in a future exercise4.Deploy your application.
        - Test using a RESTful client
    ------
    

----
## Deploying and Managing APIs to CloudHub
- Steps:
    1. Deployment of the API as a Web Service.
    2. A proxy application is deployed to API Manager and policies (restrictions of access to APIs) for security and Governance.
## Deployement Option for Mulesoft aplications
- *CloudHub*:  
    - Uses Virtual Machines on Amazon Web Serices Platform.
    - Is a component from Anypoint Platform.
    *Bennefits*:
    - Simplicity, Mulesoft manages all hardware and software with no maintenance to the customer
    - Continous and scalable on servers all over the world.
    - Mule servers are easy to install.
- *Customer Hosted Mule Runtime*:
    - It is hosted on customers' own machine
    - Can also be hosted at several Cloud Service Providers.
- *Anypoint Runtime Fabric*:
    - Customer-hosted container service of the runtime plane.
    - Automates orchestration of apps and API gateways.
    