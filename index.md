<!doctype html>
<html>
  <head>
    <title>Test</title>
    <script>
      var data = {user: "test", pwd: "test"};
      var jsonData = JSON.stringify(data);
      
      function authn() {
/*
        var xhttp = new XMLHttpRequest();
        xhttp.withCredentials = true;
        xhttp.open("POST", "https://script.google.com/macros/s/AKfycbyvME4exGupBz0ClVnkZsfuNycn2Vi6E5jeT6UuhqWyQSyFcinp/exec?param=fake", true);
        xhttp.setRequestHeader("Content-type", "application/json");
        xhttp.send(jsonData);

        xhttp.onreadystatechange = function() {
          if (this.readyState == 4 && this.status == 200) {
            if (this.responseText == "OK") {
              document.getElementById("demo").innerHTML = "<h1>Congratulation! You'd just logged in.</h1>";
            } else if (this.responseText == "NG") {
              document.getElementById("demo").innerHTML = "<h1>Sorry! It seems I don't you who you are.</h1>";
            } else {
              document.getElementById("demo").innerHTML = "<h1>WTF!!</h1>";
            }
          }
        };
*/
var data = JSON.stringify({
  "user": "test",
  "pwd": "test"
});

var xhr = new XMLHttpRequest();
//xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4 && this.status == 200) {
            if (this.responseText == "OK") {
              document.getElementById("demo").innerHTML = "<h1>Congratulation! You'd just logged in.</h1>";
            } else if (this.responseText == "NG") {
              document.getElementById("demo").innerHTML = "<h1>Sorry! It seems I don't you who you are.</h1>";
            } else {
              document.getElementById("demo").innerHTML = "<h1>WTF!!</h1>";
            }
  }
});

xhr.open("POST", "https://script.google.com/macros/s/AKfycbyvME4exGupBz0ClVnkZsfuNycn2Vi6E5jeT6UuhqWyQSyFcinp/exec");
xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");
//xhr.setRequestHeader("Cache-Control", "no-cache");

xhr.send("user=test&pwd=test");
      }
    </script>
  </head>
  <body onLoad="authn();">
    <div id="demo">what do you see?
    </div>
  </body>
</html>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3Mjc4NTA5MTFdfQ==
-->