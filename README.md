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

```
from http.server import HTTPServer, BaseHTTPRequestHandler
content= '''
<html>
    <head>
        <title>
            TCP / IP PROTOCOLS 
        </title>
        <h1>TCP / IP PROTOCOLS </h1>
        <h3> REGISTER NUMBER = 25018004</h3>
        <h3> NAME            = TEJA D P</h3>
        <br>
        <br>
    </head>
    <style>
    h1{ text-align: center; -webkit-text-fill-color: blueviolet;}
      table { width: 100%; height: 75%; background-color: antiquewhite; border-top-color: collapse;}
      td{ background-color: blue ; -webkit-text-fill-color: aquamarine; border: 1px solid skyblue;}
    </style>
    <body>
        <table>
            <tr style="background-color :goldenrod">
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
</html>

'''
class MyServer ( BaseHTTPRequestHandler):
    def do_GET (self):
        print(" Get request recived...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print(" This is my webserver")
server_address=('',8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```

# OUTPUT:
<img width="1920" height="1080" alt="Screenshot (50)" src="https://github.com/user-attachments/assets/50f8d560-6522-4184-bcea-fc9bb70a926e" />
<img width="1920" height="1080" alt="Screenshot (51)" src="https://github.com/user-attachments/assets/4c9c300d-e678-4a97-b7e9-62f81096ba53" />


# RESULT:
The program for implementing simple webserver is executed successfully.
