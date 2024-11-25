# EX01 Developing a Simple Webserver
## Date: 19/11/2024

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
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
</head>
<body>

    <h1>System Configuration</h1>
    <table>
        <tr>
            <th>Component</th>
            <th>Specification</th>
        </tr>
        <tr>
            <td>Model</td>
            <td>Lenovo ThinkPad E16</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i5</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16 GB DDR4</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>512 GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>Integrated Intel Iris Xe / AMD Radeon Graphics</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>16-inch FHD (1920 x 1200) IPS</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 11 Pro</td>
        </tr>
        <tr>
            <td>Battery</td>
            <td>Up to 10 hours</td>
        </tr>
    </table>

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
![alt text](<Screenshot (2).png>)
![alt text](<Screenshot (3).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
