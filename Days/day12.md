#What i learned

Today we started working on a game for thursday, we started by mkaing the server and how we could access things through the server. I thought the parameters was pretty interesting how the code kind of translates "/greet/:fname/:lname", We used the npm init to create the project, npm install express added the expess package whihc enabled us to crete the routes like app.get("/menu/:mealTime", (request, response). also the response.send is from the express package.

example of if statement
\\\js
app.get("/rockPaperScissors", (request, response)=>{
  let randomNumber = Math.floor(Math.random() * 3) + 1;
  if (randomNumber == 1) {
    response.send(["Rock"]);
  }
  if (randomNumber == 2) {
    response.send(["Paper"]);
  }
  if (randomNumber == 3) {
    response.send(["Scissors"]);
  }
  response.send("error")
});
\\\

how to create express tool
\\\js
let express = require("express");
let app = express();

app.get("/", (request, response)=>{{
  response.send("hey there");
}});
\\\
how to start listening on port
\\\js
app .listen(4005);
console.log("Listening on port 4005");
\\\
