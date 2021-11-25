# Developing a Simple Webserver
## AIM:
To develop a simple webserver to dispaly top five programming language.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>top five programming languages</h1>

<h1>1.javascript</h1>
<p>Speed. Client-side JavaScript is very fast because it can be run immediately within the client-side browser. ...
Simplicity. JavaScript is relatively simple to learn and implement.
Popularity. ...
Interoperability. ...
Server Load</p>

<h1>2.C++<h1>
<p>Mid-level programming language. ...
Object-Oriented. ...
Multi-paradigm programming language. ...
Memory Management. ...
Fast and Powerful.</p>

<h1>3.C</h1>
<p>Easy to write. ...
Low cost. ...
Fast execution speed. ...
Portable. ...
Easy debugging.</p>

<h1>4.python</h1>
<p>Improved Productivity.
Interpreted Language. ...
Dynamically Typed. ...
Free and Open-Source.
Vast Libraries Support. ...
Portability</p>

<h1>5.swift</h1>
<p>Interoperable with Objective-C. ...
Low maintenance. ...
Better user experience. ...
Effective memory management. ...
ABI stability.</p>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![output1](.images/output1.png)
![output2](.images/output2.png)

## RESULT:
A simple webserver to display top five programming languages is developed
