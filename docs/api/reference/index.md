This page is dedicated to the reference of the API.  
Here, you will find the all the events that are available with the API, what are their parameters and how to use them.

!!! Warning "Information"
    Please keep in mind that this page is for Experienced users, it requires some technical knowledge. Here is what you need to know:
    
    * **Lua**
    * **BeamMP** (*Server scripting*)
    * **General Programming Understanding**

## **Example of an API Event**

!!! abstract "API Example Event"

    ``` mermaid
    sequenceDiagram
    participant API as API Implementation
    participant BP as BeamPerms

    Note over BP,API: This is an example of an API call <br><br> arg1: string <br> arg2: number <br><br> result1: string <br> result2: number
    API->>+BP: "eventName", arg1, arg2
    Note over BP: Process
    BP->>-API: result1,result2
    ```

## **API Initialization Sequence**
???+ abstract "API Initialization Sequence"

    ``` mermaid
    sequenceDiagram
    participant API as API Implementation
    participant BP as BeamPerms

    Note over BP,API: Check if BeamPerms is present <br> (If there is an endpoint for the API)
    API->>+BP: "checkBpPresence"
    alt
        Note over BP: Endpoint Found
        BP->>-API: true
    else
        activate BP
        Note over BP: Endpoint NOT Found <br> (By default BeamMP will return false)
        BP--x-API: false
    end

    Note over BP,API: Check if API version is compatible <br><br> API_VERSION: string (Example: "v1.0.0")
    API->>+BP: "checkBpApiCompatibility", API_VERSION
    alt
        Note over BP: Compatibility check is successful
        BP->>-API: true
    else
        activate BP
        Note over BP: Compatibility check is NOT successful
        BP->>-API: false
    end
    ```