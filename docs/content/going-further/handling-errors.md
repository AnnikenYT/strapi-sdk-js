---
title: Handling Errors
description: "Discover how to handle errors from Strapi. 💡"
position: 9
category: "💡 Going Further"
---

Sometimes errors can be tricky to handle, especially Strapi's one 🤔
You don't know what type of error message you receive & what kind of object you'll have in the response from Strapi.


In order to help you, we decided to provide you a formatted error object when an error will be encounter:

- `status`
  - Type: `number`
  - Description: `status code of the response`
- `message`
  - Type: `string || array || object`
  - Description: `formatted response message from Strapi`
- `original`
  - Type: `object`
  - Description: `contain the original response object from axios (data)`

### Example

<d-code-group>
  <d-code-block label="Response" active>

  ```js
  {
    status: "400",
    statusText: "Bad Request",
    headers: [{...}],
    config: [{...}],
    request: [{...}],
    data: {
      message: [{
        messages: [{
          id: "Auth.form.error.email.invalid",
        }],
      }],
    },
  },
  ```

  </d-code-block>
  <d-code-block label="Error formatted">

  ```js
  {
    status: "400",
    message: {
      id: "Auth.form.error.email.invalid",
    },
    original: {
      message: [{
        messages: [{
          id: "Auth.form.error.email.invalid",
        }],
      }],
    },
  }
  ```

  </d-code-block>
</d-code-group>