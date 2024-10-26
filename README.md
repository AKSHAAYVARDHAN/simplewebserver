# EX01 Developing a Simple Webserver
## Date: 26-10-2014

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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

"""
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1><center>Welcome</center></h1>

<table border="2" cellspacing="10" cellpadding="6">
<tr>
<th>Manufacturer</th><td>HP</td>
</tr>
<tr>
<th>Edition</th><td>Windows 11</td>
</tr>
<tr>
<th>Processor</th><td>8th Gen Intel(R) Core(TM)</td>
</tr>
<tr>
<th>config</th><td>i7</td>
</tr>
<tr>
<th>RAM</th><td>8 GB</td>
</tr>
<tr>
<th>System Type</th><td>64-bit Operating System</td>
</tr>
<table>
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

"""


## OUTPUT:

![alt text](<WEB Ex LOCAL.png>)
![alt text](<WEB Ex LOCAL.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
