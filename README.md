# EX01 Developing a Simple Webserver
## Date:23/02/2024

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<h1 align ="center"> TOP FIVE SOFTWARE COMAPANIES </h1>
<table align ="center" border ="2">

    <tr>
        <th>RANK</th>
        <th>COMPANIES</th>
        <th>REVENUE</th> 
    </tr>
    <tr>
        <td>1</td>
        <td>Amazon</td>
        <td>$514.0</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Apple</td>
        <td>$394.3</td>
    </tr>
    <tr>
        <td>3</td>
        <td>Alphabet</td>
        <td>$282.8</td>
    </tr>
    <tr>
        <td>4</td>
        <td>Samsung</td>
        <td>$234.1</td>
    </tr>
    <tr>
        <td>5</td>
        <td>Hon Hai Presision industry</td>
        <td>$222.5</td>
    </tr>
</table>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![alt text](<Screenshot 2024-03-15 092631.png>)

![alt text](<Screenshot 2024-03-15 092710.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
