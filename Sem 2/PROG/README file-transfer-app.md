## File Transfer App


This application allows users to send and receive files over a local network using a client-server architecture.

### Components

1. **Server (`server.py`):**
   - Manages connections between senders and receivers
   - Generates unique connection codes for each file transfer
   - Handles file transfer between clients

2. **Client (`client.py`):**
   - Provides an easy-to-use graphical user interface (GUI) for sending and receiving files
   - Connects to the server and manages file transfer operations

### How to Use

1. **Start the Server:**
   - Run `server.py` on a machine that will act as the server
   - The server will start listening for connections on port 8000

2. **Launch the Client Application:**
   - Run `client.py` on any machine that wants to send or receive files
   - The main window will appear with "Send" and "Receive" options

3. **Sending a File:**
   - Click the "Send" button
   - In the new window, click "Browse" to select a file
   - Click "Send" to initiate the transfer
   - A unique connection code will be displayed

4. **Receiving a File:**
   - Click the "Receive" button
   - Enter the connection code provided by the sender (externally)
   - Click "Connect" to start receiving the file

> The usage would be different if the server and two clients were on different networks
### Key Features

- **Unique Connection Codes:** Ensures secure and targeted file transfers
- **Threaded Connections:** Allows multiple simultaneous transfers
- **GUI Interface:** User-friendly design for easy file selection and transfer
- **Error Handling:** Robust error checking and reporting

### Technical Details

- **Socket Programming:** Uses Python's `socket` library for network communications
- **Threading:** Implements `threading` to handle multiple connections concurrently
- **Tkinter GUI:** Utilizes `tkinter` for creating the graphical user interface

### Requirements

- Python 3.x
- Tkinter
- Requests

### Note

Ensure that the server and clients are on the same local network for successful file transfers. The server's IP address will need to be configured in the client code if not running on the same machine.

This application is designed for local network use and does not include internet-facing security measures. Use caution when transferring sensitive files.

Some print functions are left uncommented for better understanding

There could be some remaining redundant functions or variables as the model of the function changed during development

