# EX01 Developing a Simple Webserver
## Date:
29/04/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```html

from http.server import HTTPServer, BaseHTTPRequestHandler
content="""
<html>
    <head>
        <body>
            <table border ="1" align ="center" cellpadding ="5" bgcolor="yellow">
                <tr>
                    <th>S.no</th> <th>Layer</th> <th>Protocols</th>
                </tr>
                <tr>
                    <td>1</thd> <td>Application layer</td> <td>HTML , FTP ,TFTP , DNS , DHCP , SMTP , TELNET</td>
                </tr>
                <tr>
                    <td>2</td> <td>Transport Layer</td> <td>TCP , UDP</td>
                </tr>
                <tr>
                    <td>3</td> <td>Internet Layer</td> <td>IP</td>
                </tr>
                <tr>
                    <td>4</td> <td>Network Interface Layer</td> <td>ETHERNET , TOKEN RING , FRAME RELAY , ATM</td>
                </tr>
            </table> 
        </body>
    </head>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("My webserver is running...")
httpd.serve_forever()

```

## OUTPUT:
![alt text](image.png)
![alt text](output.png)
## RESULT:
The program for implementing simple webserver is executed successfully.


