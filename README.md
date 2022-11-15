# We have a nested object. We would like a function where you pass in the object and a key and get back the value. 

### What is nested object?

The basic definition of an object in JavaScript is a container for named values called properties (keys). Sometimes, we need to create an object inside another object. In this case, it's called a nested object.

### Below is the code for the same.

  ```
  # Code
let str = `{"return":
                     {
                       "response": [{"$": 1234}],
                       "responseMessage": [{"$": "Success ABC"}],
                       "responseCode": [{"$": "CITY,India"}]
                     }
                    }`;
    
    
        let js_object = JSON.parse(str); // parse json string to javascript object
        let js_object_return = js_object.return;
        let formated_obj = {};
        let desired_obj = {};
        Object.keys(js_object_return).forEach(function(key) {
            formated_obj[key] = js_object_return[key][0]["$"];
        });
        desired_obj['return']=formated_obj;
        console.log(desired_obj.return.response);
  ```
  
### Output

1234

