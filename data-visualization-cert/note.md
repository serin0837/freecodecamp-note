# JSON APIs and Ajax

- APIs :Application Programming Interfaces
- APIs are tools that computers use to communicate with one another, in part to send and receive data.
- Programmers often use AJAX technologies when working with APIs.

- The term AJAX originated as an acronym for Asynchronous JavaScript And XML.
- It refers to a group of technologies that make asynchronous requests to a server to transfer data, then load any returned data into the page.

- The data transferred between the browser and server is often in a format called JavaScript Object Notation (JSON).

- JSON resembles JavaScript object literal syntax, except that it's transferred as a string.

## 1. Handle Click Events with JavaScript using the onclick property

## 2.

왜자꾸 이벤트 핸들러 , 이벤트 리스너 헷갈리지?ㅠ

## 3. Get JSON with the JavaScript XMLHttpRequest Method

- how to update HTML with the data we get from APIs using a technology called AJAX.
- Most web APIs transfer data in a format called JSON. JSON stands for JavaScript Object Notation.
- JSON syntax looks very similar to JavaScript object literal notation. JSON has object properties and their current values, sandwiched between a { and a }.
- However, JSON transmitted by APIs are sent as bytes.
  and your application receives it as a string.

- The JSON.parse method parses the string and constructs the JavaScript object described by it.

-

```js
const req = new XMLHttpRequest();
req.open("GET", "/json/cats.json", true);
req.send();
req.onload = function () {
  const json = JSON.parse(req.responseText);
  document.getElementsByClassName("message")[0].innerHTML = JSON.stringify(
    json
  );
};
```

    - The JavaScript XMLHttpRequest object has a number of properties and methods that are used to transfer data.
    -  the open method initializes a request - this example is requesting data from an API, therefore is a "GET" request.
    - The second argument for open is the URL of the API you are requesting data from.
    - The third argument is a Boolean value where true makes it an asynchronous request.
    - . Finally, the onload event handler parses the returned data and applies the JSON.stringify method to convert the JavaScript object into a string. This string is then inserted as the message text.

## 4. Get JSON with the JavaScript fetch method

- Another way to request external data is to use the JavaScript fetch() method.
- It is equivalent to XMLHttpRequest, but the syntax is considered easier to understand.

-

```js
fetch("/json/cats.json")
  .then((response) => response.json())
  .then((data) => {
    document.getElementById("message").innerHTML = JSON.stringify(data);
  });
```

    - So, fetch(URL) makes a GET request to the URL specified. The method returns a Promise.
    - After a Promise is returned, if the request was successful, the then method is executed, which takes the response and converts it to JSON format.
    - The then method also returns a Promise, which is handled by the next then method. The argument in the second then is the JSON object
    - , it selects the element that will receive the data by using document.getElementById(). Then it modifies the HTML code of the element by inserting a string created from the JSON object returned from the request.

## 5. Access the JSON Data from an API

array and object

## 6. Convert JSON Data to HTML??

forEach

```js
let html = "";
json.forEach(function (val) {
  const keys = Object.keys(val);
  html += "<div class = 'cat'>";
  keys.forEach(function (key) {
    html += "<strong>" + key + "</strong>: " + val[key] + "<br>";
  });
  html += "</div><br>";
});
```

## 7. Render Images from Data Sources

When you're looping through these objects, you can use this imageLink property to display this image in an img element.

```js
html += "<img src = '" + val.imageLink + "' " + "alt='" + val.altText + "'>";
```

## 8. Pre-filter JSON to Get the Data You Need

- can use the filter method to filter out the cat whose "id" key has a value of 1.

```js
json = json.filter(function (val) {
  return val.id !== 1;
});
```

## 9. Get Geolocation Data to Find A User's GPS Coordinates

- you can do is access your user's current location. Every browser has a built in navigator that can give you this information.

- The navigator will get the user's current longitude and latitude.

```js
if (navigator.geolocation) {
  navigator.geolocation.getCurrentPosition(function (position) {
    document.getElementById("data").innerHTML =
      "latitude: " +
      position.coords.latitude +
      "<br>longitude: " +
      position.coords.longitude;
  });
}
```

## 10. Post Data with the JavaScript XMLHttpRequest Method

- In the previous examples, you received data from an external resource. You can also send data to an external resource, as long as that resource supports AJAX requests and you know the URL.

```js
const xhr = new XMLHttpRequest();
xhr.open("POST", url, true);
xhr.setRequestHeader("Content-Type", "application/json; charset=UTF-8");
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 201) {
    const serverResponse = JSON.parse(xhr.response);
    document.getElementsByClassName("message")[0].textContent =
      serverResponse.userName + serverResponse.suffix;
  }
};
const body = JSON.stringify({ userName: userName, suffix: " loves cats!" });
xhr.send(body);
```
