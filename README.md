# GPT
The GPT open-source project by Selldone offers scripts and documentation for implementing GPT for [**Open AI Store**](https://openai.com/blog/introducing-gpts), facilitating its integration and utilization in various applications.


## Schema.json
The schema.json file contains the structure of the GPT data. This file is used to validate the data and to generate the GPT data entry form. The schema.json file is a JSON file that contains the following fields:


The provided schema is a configuration for an OpenAPI Specification (OAS) document, version 3.1.0, detailing the structure and behavior of an API for "My shops" related to a business and sales platform on Selldone. This document is structured to provide comprehensive information about the API's paths, methods, and operational details. Here's a detailed breakdown of each section and item within the schema:


## OAuth Configuration
Authorization URL: `https://selldone.com/oauth/authorize`

Token URL: `https://selldone.com/oauth/token`

Scopes: `read-shops profile backoffice-read-products`

Privacy: `https://selldone.com/privacy`



### 1. **openapi**: "3.1.0"
- **Definition**: Specifies the version of the OpenAPI Specification that this document conforms to. It dictates the overall structure and available features.

### 2. **info**:
- **Definition**: Provides metadata about the API.
- **title**: "My shops"
    - **Description**: The name or title of the API.
- **description**: "Get information about my business and sales on Selldone."
    - **Description**: A brief summary of what the API does or is used for.
- **version**: "v1.0.0"
    - **Description**: The version of this particular API, which helps in version control and management.

### 3. **servers**:
- **Definition**: An array of server objects used for connecting to the API.
- **url**: "https://api.selldone.com"
    - **Description**: The base URL for the API calls, indicating where the API is hosted and accessible.

### 4. **paths**:
- **Definition**: The available paths and operations for the API.

#### "/security/2fa/check":
- **get**:
    - **description**: "Check user two-factor authentication is enabled? If the 'user' value is in response, it means the user successfully logged in. Otherwise, call Verify2FA."
    - **operationId**: "Check2FA"
    - **parameters**: []
        - **Description**: An empty array, indicating no parameters are required for this operation.
    - **deprecated**: false
        - **Description**: Indicates whether this path is obsolete or not.

#### "/auth/2fa":
- **post**:
    - **description**: "Request user to enter 6 digit number 2FA code if Check2FA does not return 'user' value in its response."
    - **operationId**: "Verify2FA"
    - **parameters**: []
        - **Description**: An empty array, indicating no parameters are required for this operation.
    - **requestBody**:
        - **description**: "6-digit 2FA numeric code to verify access."
        - **required**: true
        - **content**:
            - **application/json**:
                - **schema**:
                    - **type**: "object"
                    - **properties**:
                        - **code**:
                            - **type**: "string"
                            - **description**: "6-digit 2FA numeric code to verify access."
    - **deprecated**: false
        - **Description**: Indicates whether this path is obsolete or not.

#### "/shops/me":
- **get**:
    - **description**: "Get the list of my shops"
    - **operationId**: "GetShops"
    - **parameters**:
        - **name**: "search"
        - **in**: "query"
        - **description**: "Something about business name or its URL."
        - **required**: false
        - **schema**:
            - **type**: "string"
    - **deprecated**: false
        - **Description**: Indicates whether this path is obsolete or not.

### 5. **components**:
- **schemas**: {}
    - **Definition**: A placeholder for reusable objects like response and request models. It's empty in this schema, indicating no reusable components are defined.

This schema is a structured configuration for an API that deals with various aspects of shops and two-factor authentication. It outlines the base URL, the available operations, their details, and how to interact with them. The paths "/security/2fa/check", "/auth/2fa", and "/shops/me" correspond to operations related to checking two-factor authentication, verifying it, and getting information about shops, respectively.


# Configuring Your GPT with OpenAI

Welcome to the future of business technology! OpenAI is launching its groundbreaking service, and you're invited to create your very own GPT for your business. Whether you're a developer, entrepreneur, or tech enthusiast, this guide will help you set up your GPT with ease. Let's get started!

## Step 1: Create a New GPT

Begin by setting up your new GPT:

- Navigate to your ChatGPT and click on your profile picture.
- Select 'My GPTs'.
- At the top of the page, click on 'Create new GPT'.
![create-new-gpt.jpg](_docs%2Fcreate-new-gpt.jpg)
![create-GPT-step1.jpg](_docs%2Fcreate-GPT-step1.jpg)
**Note**: If you encounter any issues while uploading an image for your icon, consider using DALL·E to create a custom image. Alternatively, drag and drop your file on the 'Create' tab and write: "set it as my GPT icon".

## Step 2: Personalize Your GPT

It's time to give your GPT its unique identity:

- Go to the 'Configuration' tab.
- Fill out the details about your GPT. You can use the 'Create' tab to assist you in this process.
- Think of this step as infusing your GPT with a touch of your personality or business essence.

![creaet-GPT-step2.jpg](_docs%2Fcreaet-GPT-step2.jpg)

## Step 3: Feed Your GPT Extra Information

Enhance your GPT's knowledge:

- You can upload various files like Excel, CSV (preferred), text, JSON, or other formats to provide additional data.
- Use the '[ ... ]' format in the prompt/answer to maintain clarity and organization.

![creaet-GPT-step3.jpg](_docs%2Fcreaet-GPT-step3.jpg)

## Step 4: Connect Your GPT to Your Servers or 3rd Party Services & APIs

Integrate your GPT with your existing tech infrastructure:

- For instance, to connect to Selldone, use OAuth for secure and restricted access.
- Define API calls and follow a standard structure. Don't worry; it's more straightforward than it seems!

![creaet-GPT-step5.jpg](_docs%2Fcreaet-GPT-step5.jpg)


**Define APIs and Schema Code**

![creaet-GPT-step4.jpg](_docs%2Fcreaet-GPT-step4.jpg)

**Finding Your Callback URL**

- The callback URL can be found on the previous page or by logging into your GPT and checking the requested URL there.
- Remember, changing the OAuth configuration in ChatGPT will also change the callback URL.

![callback.jpg](_docs%2Fcallback.jpg)

**Setting Up OAuth on Your Server**

- If using Laravel, enable 'Passport' and run `php artisan passport:client` to create a client.
- Most back-end frameworks provide official solutions for OAuth implementation.

![oauth.jpg](_docs%2Foauth.jpg)

## Troubleshooting & Tips

- OpenAI may update configurations, so be prepared to make adjustments.
- OAuth | Calling APIs by ChatGPT: Ensure you're familiar with the process for a smooth experience.


Happy configuring!
