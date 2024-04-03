![Actions](https://github.com/sourceduty/ChatGPT_Actions/assets/123030236/c8834e52-3e29-4851-ad86-9ca0858c646f)

### ChatGPT Actions API

> Alex: "Understanding and learning about the OpenAI specification for API actions in custom GPTs proved challenging for me initially. However, with the assistance of ChatGPT, I gained detailed explanations that clarified my questions regarding the OpenAI specification, schema, and more. Integrating custom GPT action APIs and services using JSON format is significantly more complex than providing plain text instructions. In upcoming projects, I may integrate a custom API or service, such as the Twitter API, Google Vision API, or PayPal API, into one of my custom GPTs.
>
> Initially, I successfully developed a JSON format in the OpenAPI specification for the Google Maps API. This specific JSON format was utilized by my 'Maps Guide' custom GPT. However, I later removed the specification for the Google Maps API.
>
> Subsequently, I attempted to integrate the Google Cloud Vision API, GPT-4 with Vision, and the Twitter API into several custom GPTs, but unfortunately, I was unsuccessful. During these attempts, I utilized 'OpenAPI Spec JSON Actions' to guide JSON format creation in custom GPT actions. This custom GPT was designed to facilitate the creation of JSON formats for integrating APIs. I extensively optimized, expanded, and improved 'OpenAPI Spec JSON Actions' in an effort to aid in API integration.
>
> Despite my efforts, integrating image recognition APIs proved to be complex. While I found Vertex AI Vision easy to manage and use, it is highly customized. Moving forward, I may consider using image recognition if a simpler, standardized method becomes available that doesn't necessitate customization of my own model.
>
> Authentication of APIs for custom GPTs posed challenges. To mitigate this, I developed a custom GPT to access the Public APIs Directory, enabling access to APIs that don't require authentication. These APIs cover various topics such as weather, public data, news, transit, currency exchange, sports, and astronomy. Additionally, I integrated the Public APIs Directory into 'Easy APIs'.
>
> At the beginning of 2024, OpenAI released ActionsGPT, which superseded all custom GPTs specialized in OpenAPI spec development."

#

<details><summary>OpenAI Custom Actions Template</summary>
<br>

```
openapi: 3.0.0
info:
  title: OpenAI Custom Actions API
  description: API specification for interacting with OpenAI custom actions.
  version: 1.0.0
servers:
  - url: https://api.openai.com/v1
    description: OpenAI API server
paths:
  /actions:
    get:
      operationId: listActions
      summary: Lists all available actions.
      description: Retrieves a list of actions that have been defined in the OpenAI system.
      responses:
        '200':
          description: A JSON array of actions
          content:
            application/json:
              schema: 
                type: array
                items: 
                  type: object
                  properties:
                    id:
                      type: string
                    name:
                      type: string
                    description:
                      type: string
    post:
      operationId: createAction
      summary: Creates a new action.
      description: Allows the creation of a new action within the OpenAI system.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              properties:
                name:
                  type: string
                description:
                  type: string
                code:
                  type: string
      responses: 
        '201':
          description: Successfully created
          content:
            application/json:
              schema:
                type: object
                properties:
                  id:
                    type: string
                  name:
                    type: string
                  description:
                    type: string
```

<br>
</details>

***
