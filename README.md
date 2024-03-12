# EX01 Developing a Simple Webserver
## Date:20.02.24

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
<!DOCTYPE html>
<html>
<head>
<title>
Software Companies
</title>
</head>
<body>

<table align="center" border="10" cellspacing="0" cellpadding="20" >
<caption><h2>Top 5 Revenue Generating software Companies</h2></caption>
<tr bgcolor="yellow">
<th><h3>Rank</h3></th>
<th><h3>Company</h3></th>
<th><h3>Revenue</h3></th>
</tr>

<tr>
<td>1</td>
<td>Apple</td>
<td>$394.3 billion</td>
</tr>

<tr>
<td>2</td>
<td>Google</td>
<td>$279.8 billion</td>
</tr>

<tr>
<td>3</td>
<td>Microsoft</td>
<td>$198.2 billion</td>
</tr>

<tr>
<td>4</td>
<td>Meta</td>
<td>$116 billion</td> 
</tr>

<tr>
<td>5</td>
<td>Dell Technologies</td>
<td>$101.1 billion</td>
</tr>

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
```

## OUTPUT:
![alt text](<Screenshot 2024-03-12 113109.png>)
![alt text](<Screenshot 2024-03-12 113340.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
