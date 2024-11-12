# API-helper
ApiHelper
The ApiHelper class provides methods for making HTTP requests with JSON payloads. It uses AsyncHttpClient to manage network connections, handles JSON data using JsonHttpResponseHandler, and returns success or error messages as Toasts.

Methods
POST - post(api: String, jsonData: JSONObject)
GET - get(api: String, callBack: CallBack)
PUT - put(api: String, jsonData: JSONObject)
DELETE - delete(api: String, jsonData: JSONObject)
Each of these methods can be used to interact with REST APIs by passing the API endpoint and required data. The GET method also includes a CallBack interface for handling successful responses.

Interface: CallBack
The CallBack interface is used by the GET function to handle responses, allowing for customized responses to each API call.

Usage Example
To use ApiHelper, instantiate it in your Activity or Fragment, and call the appropriate method based on the request type.

kotlin
Copy code
val apiHelper = ApiHelper(context)

// Example POST request
val jsonData = JSONObject()
jsonData.put("key", "value")

apiHelper.post("https://api.example.com/endpoint", jsonData)

// Example GET request
apiHelper.get("https://api.example.com/endpoint", object : ApiHelper.CallBack {
    override fun onSuccess(result: String?) {
        // Handle successful response here
    }
})
Error Handling
Errors are handled in each request's onFailure method. Toasts display error messages, making debugging easier.

Contributions
Contributions are welcome! Please fork the repository, make changes, and submit a pull request.

License
This project is licensed under the MIT License.

