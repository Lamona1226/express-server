# Express server


1.To run this code use 
      
      git clone https://github.com/Lamona1226/express-server.git
2.Run the command
    
    cd/express-server-keylogger-basic
3.Run the command 
    
    python3 setup.py.
This will do the basic setup on the Ubuntu server. It will install NodeJS, Node Package Manager (NPM) and also install all the modules required such as the Express web framework, the body-parser middleware used by Express.
4.Run the command 
    
    node server.js
to start the server on port 8080
# How to Use the Node.js Server Code

This Node.js script sets up an Express server to capture and log keyboard data sent via HTTP POST requests. The data is saved to a text file (keyboard_capture.txt) and can be viewed via a GET request to the server. Below are the steps to set up and use the code:
Prerequisites

   1. Install Node.js and npm (Node Package Manager) on your system.

   2. Install the required dependencies (express and body-parser) using npm:

    npm install express body-parser

Code Overview

    The script uses the express framework to create a web server.

    It listens for POST requests to log keyboard data into a file (keyboard_capture.txt).

    It responds to GET requests by displaying the logged data in a simple HTML format.

    The server runs on port 8080 by default.

Steps to Run the Code

   1. Save the Code:
    Save the provided code in a file, e.g., server.js.

   2. Run the Server:
    Start the server using Node.js:
   

    node server.js

  3.  View Logged Data:
    Open a browser and navigate to http://localhost:8080. This will display the logged keyboard data (if any) or a message indicating no data has been logged yet.

   4. Send Keyboard Data:
    Use a tool like Postman or write a simple script to send a POST request to http://localhost:8080 with a JSON payload containing the keyboard data. Example payload:
    

    {
        "keyboardData": "This is a test keystroke."
    }

   5. Check the Log File:
    The server saves the received keyboard data to a file named keyboard_capture.txt in the same directory as the script.

Example Usage
Sending Data via POST Request

You can use the following curl command to send a POST request to the server:


    curl -X POST http://localhost:8080 -H "Content-Type: application/json" -d '{"keyboardData": "Hello, world!"}'

Viewing Logged Data

After sending data, visit http://localhost:8080 in your browser to see the logged data displayed in HTML format.
Customization

   . Change Port:
    Modify the port variable in the script to use a different port.
    Example:
    

    const port = 3000; // Change to your desired port

  .  Change Log File:
    Update the file name in the fs.writeFileSync and fs.readFileSync functions to use a different file for logging.
    Example:
   

    fs.writeFileSync("custom_log_file.txt", req.body.keyboardData);





