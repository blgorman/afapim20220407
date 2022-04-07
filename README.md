# Simple Function App Demo

This is a simple function app used for demonstration of deployment to azure via ARM template from a GitHub URL, or via direct deployment from Azure using a GitHub url.

Either create the ARM template and leverage the link, or use the Deployment center in your Azure Function app to point to the public URL for this repo.  

```https
https://github.com/blgorman/SimpleFunctionAppDemo.git
```  

>**Note:** that's not the same repo!

## Quick Info

The following information may be useful to aid in your demonstrations

- There are two functions
  - Function1 (Anonymous access, the default function generated in a new Azure Function - pass your name in the query string or body)
  - GetPeople (A function that requires a function key along with the URL to return data.  The data is prefabricated with eight people. The people are four superheros, two Smiths and two Johnsons - you can filter the results by name of the person, such as `smith`).

Additional functions:

- Http Trigger xls parser
  - ParseFileHTTPTrigger
- EventGrid Trigger xls parser
  - ParseFileEventGridTrigger

These functions model two ways to trigger a function app from an azure storage account  

- ParseFileEventGridTrigger happens directly from the event grid, and requires that you create the event grid subscription on your storage account to respond to blob storage create events.  

- ParseFileHTTPTrigger requires that you build a logic app that responds to the storage account blob created event (via event grid integration).  Then use the logic app to post the values from the parsed event info to the azure function via http post and details in the body of the request.

## A postman collection

In order to easily query this function app, import the Postman collection that is included.  Also import the environment variables and update the variables to match your deployment.

## Slides

On 2022.01.11 I delivered a serverless precompiler talk at CodeMash. I have added the slides from that talk to this repo. 

## References

Some of the code and some of the concepts are ported and modified based on this [Serverless Architecture MCW Repository](https://github.com/microsoft/MCW-Serverless-architecture).  

## Additional Links

Some detailed information for serverless architectures can be found at the following links:

- [Serverless apps: Architecture, patterns, and Azure implementation](https://docs.microsoft.com/dotnet/architecture/serverless/?WT.mc_id=AZ-MVP-5004334)

