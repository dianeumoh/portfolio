# Most websites
Request response cycle:

1) HTTP request comes to the server from the web client.
2) Linux (OS) gives the request to nginx (networking layer - code that knows how to listen to HTTP requests and serve responses)
--- after step 2 is where things start to slow down, slow site speeds --
3) Nginx passes that HTTP request to Django (the application code - turns the request into a response.)
4) Django asks the database for any information that it needs based on the parameters of the request.
5) Django takes that information combines it with HTML templates to produce the actual HTML.
6) Django passes the HTML back to nginx
7) nginx serves the response back to the web client.

But what if the content is really simple?
Then comes static site generators 

# What happens offline (Jekyll):
1) Jekyll then asks the database for all the answers (does the work upfront before any request comes in) example: your computer
2) Jekyll renders all the answers against appropriate templates (ex: blog posts)
3) Jekyll then saves the resulting HTML to actual files
4) Then the developer uploads those files to the server

# Time for a request (Jekyll)!
1) HTTP request comes to the server from the web client.
2) Linux (OS) gives the request to nginx (networking layer - code that knows how to listen to HTTP requests and serve responses)
3) Nginx simply returns the appropriate files
4) AND YOU'RE DONE! YOUR SITE IS FAST, MAN!

What are the other benefits?
- It's more secure (no one will hack it)
- Less maintenance (ex: Python could run out of memory, why sites go down)  
- Lower cost (databases cost money and you can have a much simpler server - ex: $1 of server buys you a lot more capacity for traffic)
- Blog aware (you can write your content in markdown)
** Barack Obama's campaign website used Jekyll**
