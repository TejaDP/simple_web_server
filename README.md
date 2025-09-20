# EX01 Developing a Simple Webserver

# Date:19.09.2025
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
'''
from http.server import HTTPServer,BaseHTTPRequestHandler
content=''' <html>
    <head>
        <title>
            TCP / IP PROTOCOLS 
        </title>
        <h1 align="center">TCP / IP PROTOCOLS </h1>
        <h3> REGISTER NUMBER = 25018004</h3>
        <h3> NAME            = TEJA D P</h3>
        <br>
        <br>
    </head>
    <body>
        <table>
            <tr>
                <th></th>
                <th> LAYER</th>
                <th> </th>
                <th> DESCRIPTION </th>
            </tr>
            <tr>
                <td> </td>
                <td> APPLICATION </td>
                <td>  - </td>
                <td> Presents data to users ; encoding , session control , and data translation with protocols like HTTP(S), FTP , DNS , DHCP .</td>
            </tr>
            <tr>
                <td> </td>
                <td> TRANSPORT </td>
                <td> - </td>
                <td>End-to-end connection establishment , error control , and data delivery using TCP and UDP.</td>
            </tr>
            <tr>
                <td> </td>
                <td> NETWORK </td>
                <td>  - </td>
                <td>logical addressing and routing of data packets from source to destination.</td>
            </tr> 
            <tr>
                <td>  </td>
                <td> DATALINK </td>
                <td> - </td>
                <td>Combines raw data into frames , provides error recovery and retransmission.</td>
            </tr> 
            <tr>
                <td> </td>
                <td> PHYSICAL </td>
                <td> - </td>
                <td>Provides the physical interface for transmitting raw bits over the medium.</td>
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
server_address=('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
        
'''
# OUTPUT:

![alt text](<Screenshot (21).png>)

![alt text](<Screenshot (22).png>)



# RESULT:
The program for implementing simple webserver is executed successfully.
