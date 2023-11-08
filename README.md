# EX01 Developing a Simple Webserver
## Date:
01/11/2023

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
`````
from http.server import HTTPServer,BaseHTTPRequestHandler
content = """
<html>
     <title> Image Map </title>
     <body>
          <table border = "2" cellspacing = "10" cellpading = "6">
               <caption> Top five revenue generating software companies</caption>
               <tr>
                    <th>S.no</th>
                    <th>Company</th>
                    <th>Revenue</th>
               </tr>
               <tr>
                    <td>1</td>
                    <td>Microsoft</td>
                    <td>65 Billion</td>
               </tr>
               <tr>
                    <td>2</td>
                    <td>Oracle</td>
                    <td>29.6 Billion</td>
               </tr>
               <tr>
                    <td>3</td>
                    <td>IBM</td>
                    <td> 29.1 Billion</td>
               </tr>
               <tr>
                    <td>4</td>
                    <td>SAP</td>
                    <td>6.4 Billion</td>
               </tr>
               <tr>
                    <td>5</td>
                    <td>Syamtec</td>
                    <td>5.6Billion</td>
               </tr> 
          </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

`````

## OUTPUT:
![Screenshot 2023-11-08 095539](https://github.com/Preethijgan/simplewebserver/assets/144870652/aa5df53a-e3a8-4d8a-b3dc-25c8a0775884)
![Screenshot (8)](https://github.com/Preethijgan/simplewebserver/assets/144870652/163effed-5cda-4fbd-8b63-e895ee0735e9)


## RESULT:
The program for implementing simple webserver is executed successfully.
