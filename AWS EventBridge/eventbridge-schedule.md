# Create a Lambda function with Nodejs 16 and the below code

```js
exports.handler = async (event, context) => {
  const message = event["message"];
  console.log(message);
};
```

# Create an Eventbridge schedule with the following payload

```json
{
  "message": "Hello from EventBridge!"
}
```
