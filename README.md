# EX01 Developing a Simple Webserver

# Date:18.11.26
## REG NO:26005747
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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<html>
<head>
    <title>Sample Web Page</title>
</head>

<body>
    <h1>Mitula</h1>
    <h2>26005747</h2>

    <table border="2" cellpadding="10">
        <caption>My Laptop Configuration</caption>

        <tr>
            <th>s.no</th>
            <th>Device Type</th>
            <th>Device Info</th>
        </tr>

        <tr>
            <td>1.</td>
            <td>Device Name</td>
            <td>TL15-53M-G2</td>
        </tr>

        <tr>
            <td>2.</td>
            <td>Processor</td>
            <td>Intel(R) Core(TM)5 210H(2.20 GHz)</td>
        </tr>

        <tr>
            <td>3.</td>
            <td>Installed Ram</td>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>

        <tr>
            <td>4.</td>
            <td>Graphics Card</td>
            <td>Intel(R) Graphics (128 MB)</td>
        </tr>

        <tr>
            <td>5.</td>
            <td>Storage</td>
            <td>113 GB of 477 GB used</td>
        </tr>

        <tr>
            <td>6.</td>
            <td>Device ID</td>
            <td>5D1B48AB-7E01-41E4-8947-B1CD64B235BA</td>
        </tr>

        <tr>
            <td>7.</td>
            <td>Product ID</td>
            <td>00342-42954-08772-AAOEM</td>
        </tr>

        <tr>
            <td>8.</td>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>

        <tr>
            <td>9.</td>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>

    </table>
</body>
</html>        
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())
server_address =('',8000)
print("This is my webserver")
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

# OUTPUT:

![alt text](<Screenshot 2026-11-18 124054(1).png>)


![alt text](<Screenshot 2026-11-18 130440.png>)



# RESULT:
The program for implementing simple webserver is executed successfully.
