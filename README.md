# EX01 Developing a Simple Webserver
## Date:
25/03/2024
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Welcome</h1>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
![s2](https://github.com/PranaveshSaikumar/simplewebserver/assets/151001393/0ad5f254-f2db-4ef5-b795-bb88405cf775)
![sc1](https://github.com/PranaveshSaikumar/simplewebserver/assets/151001393/87e6d571-250e-4853-9af5-b270290e0633)

## RESULT:
The program for implementing simple webserver is executed successfully.
