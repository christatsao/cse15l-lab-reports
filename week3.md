# Part 1

![chat server](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.31.44%20PM.png)

![add message 1](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.34.25%20PM.png)
## Which methods in your code are called?
- ```main(), handleRequest()```
- ```getPath(), equals(), contains(), getQuery(), split(), println(), parseInt(), start()```
## What are the relevant arguments to those methods, and the values of any relevant fields of the class?
- main has the ```String[] args``` from the cmd line, ```handleRequest()``` has the URI called url from the web browser
- ```getPath()``` destructures the path from the url, ```getQuery()``` gets the request parameters after the ?
- the rest is in the screenshot
## How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
- ```runningSingleString``` gets constantly concatenated with the parameters being added to the web server.

![add message 2](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.35.19%20PM.png)
## Which methods in your code are called?
- ```main(), handleRequest()```
- ```getPath(), equals(), contains(), getQuery(), split(), println(), parseInt(), start()```
## What are the relevant arguments to those methods, and the values of any relevant fields of the class?
- ```main``` has the ```String[] args``` from the cmd line, ```handleRequest()``` has the URI called url from the web browser
- ```getPath()``` destructures the path from the url, getQuery gets the request parameters after the ?
- the rest is in the screenshot
## How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
- ```runningSingleString``` gets constantly concatenated with the parameters being added to the web server.

# Part 2
![abs path priv](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.25.10%20PM.png)
![abs path pub](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.21.50%20PM.png)
![interaction](https://github.com/christatsao/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-30%20at%2011.12.24%20PM.png)

# Part 3
I had no idea mkdir had so many possible parameters. I thought it was just to make a directory but you can set read / write permissions with flags.
