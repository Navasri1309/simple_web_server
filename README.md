# EX01 Developing a Simple Webserver

# Date:20.09.2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from django .shortcuts import render
from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''<html
><head>
    <title>Microsoft</title>
</head>
<body>
    <h2 align="centre">TCP/IP PROTOCOL SUITE</h2>
    <table border="1" bgcolor = "lavender" align="centre" cellpadding="20">
    <tr>
        <th bgcolor="pink">LAYER</th>
        <th bgcolor="pink">PROTOCOL</th>
    </tr>
    <tr>
        <td>Application layer</td>
        <td>HTTP,SMTP,DNS,FTP,RDP,DHCP,X Windows,Telnet,SSH,TFTP,SNMP</td>
    </tr>
    <tr>
        <td>Transport Layer</td>
        <td> TCP,UDP</td>
    </tr>
    <tr>
        <td>Internet Layer</td>
        <td>ICMP,IGMP,ARP,IPv4/IPv6</td>
    </tr>
    <tr>
        <td>Network Access Layer</td>
        <td>Ethernet,FDDI,Frame Relay,Token Ring</td>
    </tr>
    </table>
</body>
</html>'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
# OUTPUT:

![alt text](<Screenshot 2025-09-19 204621.png>)

![alt text](<Screenshot 2025-09-19 211903.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
