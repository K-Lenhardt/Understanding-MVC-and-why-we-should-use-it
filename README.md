<h1 align="center">=== Understanding MVC and why we should use it! ===</h1>
<h5 align="center">A quick Lecture on MVC, what it is and why we should be using it.</h5>

![No Idea Dog](https://i.imgflip.com/6rjt27.jpg)

<p>As software engineers there are many times we come across code that is hard to follow, that looks messy and unorganized. But it doesn't have to be that way if we 
all 
follow the same principals. This is where MVC, or Model/View/Control comes into play.
It is a way for us to structure our codebase in a certain way, that not only helps us with readability and organization, but also ensures our different sections of 
code are abstracted away from each other, so that if we make changes in one area it won't automatically break stuff elsewhere. </p>

![MVC Model](https://blog.kakaocdn.net/dn/CZudV/btqQDGrt8eX/B2AWSQvjrtCGrVffTU4F81/img.png)

<p> Essentially we will segregate our code into different categories that each handle their own Tasks. Say the user makes a request to the server that requires the 
server to put out a different View of the page. In this case the Client will talk to the Router, the Router then checks on which Route this request was made and hands 
it to the appropriate Controller. The Controller will then communicate to the View which View it is that we want to serve. It then gets handed back to the Controller 
and the Controller will Respond to the Client with the new View and refreshes it. </p>
<p> The same principal applies to the Model. If something happens that requires a change in our Database, the Controller hands this task off to the Model, which then 
updates the Database, hands it back to the Controller, then tells the View what changes to make and then respond with it to the Client.
This might all sound a bit complicated at first glance, but we will go into more detail. </p>

<h3 align="left">=== THE VIEW ===</h3>

<p> Views are essentially our stored HTML templates, in this case ".ejs", that we serve to the Client. It differentiates from static HTML pages in the way that it 
allows us to generate content within the page by using our embedded code and show it to the Client. </p>

![View Example](https://i.gyazo.com/15342e15d3356f1e30b7027915117f63.png)

<p> Say we serve the user a page with a to-do list. In this case we have our li's with span's etc., which have nothing in them unless we tell our server to insert 
our elements from our database into the View and then respond with it to the client. </p>

<h3 align="left">=== REQUESTS & ROUTING ===</h3>

<p> After telling our Server which Routes we will be using, we can use these to contact the appropriate Controller for the Task.
In this case we are simply making a GET request for the index/main page. </p>

![Route Example 1](https://i.gyazo.com/5e8a78dff453fc3b7f304c8499a2e9b8.png)

<p> Here we have a variable of "mainRoutes" assigned to use the path of "./routes/main", and are telling the server to use it whenever the index (./) of our page is 
called. </p>

![Route Example 2](https://i.gyazo.com/03891b89df40ed4cb4f422e8d4ee8d4f.png)

<p> Now in our "./routes/main.js" we have set up our express.Router() function and a variable of "homeController". 
Once the "router.get()" is called it will route us to the homeController and call its ".getIndex" function. </p>

<h3 align="left">=== CONTROLLER ===</h3>

<span>Here is an example of the Controller we just called in the prior section:</span

![Controller Example](https://i.gyazo.com/36a410bdff8e387f2043ddf68e62c535.png)

<p> After calling the appropriate Controller for the Task it will simply get the View of our "index.ejs" that we have stored, and responds with it to the Client and  render it out. </p>
<p> By separating our code like this we could easily just change out what View we want to serve up on this request without affecting any other code of our codebase. </p>

<h3 align="left">=== MODEL, MONGOOSE & SCHEMA ===</h3>

<p>Our Model is basically what does the talking to our Database. When we require to make any changes to our Database or pull data from it to insert into the View the 
appropriate Controller will contact the Model to achieve this.</p>
<p> In this example we will be using Mongoose and something called a Schema. </p>
<p> The Schema allows us to communicate data to our database in a by us pre-determined format. This helps us to keep everything organized and prevent other people we 
work with from inputting additional Object properties into our database that aren't supposed to be there. </p>

![Model Example](https://i.gyazo.com/e2f18f370c55afc5828b7d781abc14d3.png)

<p> After making a POST request, the controller handling that specific POST will communicate to the model on what to put into the database. Our model then takes that 
request and formats it into our set Schema and puts it into our database. </p>

<h3 align="left">=== CONCLUSION ===</h3>
<p> In conclusion, using MVC helps us to keep our Code organized and abstracted from each other in a way that we can work on one part of the Code without breaking 
anything else and allows us to more easily interchange certain parts. </p>
<p> As long as we collectively adhere to this Standard, we can make our lives as Software-Engineers a lot easier and less stressful. </p>
