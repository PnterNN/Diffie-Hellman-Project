# Diffie-Hellman Chat Application

This project uses the Diffie-Hellman Key Exchange Algorithm to establish secure communication between clients and a server. After connecting to the server, clients can message other users and save their messages. Additionally, the project provides a console command to test brute force attacks.

## Features

### Diffie-Hellman Key Exchange:
- Key exchange is performed between the client and the server.
- Keys are generated and used securely.

### Messaging:
- Messages can be sent to all users using the "Everyone" option.
- Direct messages can be sent to specific users.

### Registration and Login System:
- Users can register and log in.
- After logging in, users receive messages sent to them previously.

### Server Features:
- Stores incoming messages.
- Messages can be sent to clients via the server.

### Brute Force Test:
- By typing `bruteforce` in the console, the system's performance against brute force attacks can be tested.

# Setup and Running the Application

## Requirements
- .NET Framework or .NET Core SDK
- MySQL Database (for storing messages and user information)

## Steps

### Clone the Project Repository:
```
git clone https://github.com/PnterNN/Diffie-Hellman-Project
```
### Server Startup:

- Run the server project.
- The server runs on `Port: 900` by default.

### Client Connection:

- Run the client project.
- Enter the server's IP address and port to establish a connection.

### Messaging:

- Register or log in.
- Use the "Everyone" option to send messages to all users or send messages to a specific user.

### Brute Force Test:

- Run the MiddleMan project.
- Type `bruteforce` in the console to start the brute force test.

## Usage

### Server:

- **Message Sending**:
  - You can send messages to "Everyone" or a specific user.
  - Messages and user information are stored in the MySQL database.

### Client:

- **After Logging In**:
  - Previously received messages are delivered to the client.
  - You can chat with other users.
  - You can register as a new user if needed.

### Brute Force (MiddleMan):

- Type `bruteforce` in the console to test the security of the encryption algorithm.
- This process analyzes how quickly the Diffie-Hellman protocol can find specific keys.

## Project Architecture

### Client:

- User registration/login system.
- Message sending to other clients.
- Diffie-Hellman key exchange.

### Server:

- Manages user sessions and messages.
- Stores messages in the database.
- Handles key exchange.

### MiddleMan:

- Performs brute force attack testing.
- Analyzes the security of the Diffie-Hellman key exchange.

## Screenshots

### Server Interface

Displays server connections, messaging, and user management.

![image](https://github.com/user-attachments/assets/76d1f460-bdb5-407a-87cd-63be7a1f73a4)

### Client Interface

Includes user login/registration screen and messaging interface.

![image](https://github.com/user-attachments/assets/2eb550a2-529f-4ab7-a473-5451c3aa72e3)

## Important Notes

- The Diffie-Hellman algorithm is used for key exchange.
- The server securely stores user session data and messages.
- The MiddleMan application is for testing purposes only and should not be used for real attacks.

## Database Schema

<div>
  <h3>Database Schema</h3>

  <h4>Table: Users</h4>
  <table border="1">
    <thead>
      <tr>
        <th>Column</th>
        <th>Data Type</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Id</td>
        <td>INT</td>
        <td>User ID</td>
      </tr>
      <tr>
        <td>Username</td>
        <td>VARCHAR</td>
        <td>Username</td>
      </tr>
      <tr>
        <td>Email</td>
        <td>VARCHAR</td>
        <td>Email address</td>
      </tr>
      <tr>
        <td>Password</td>
        <td>VARCHAR</td>
        <td>Password (Hashed)</td>
      </tr>
    </tbody>
  </table>

  <h4>Table: Messages</h4>
  <table border="1">
    <thead>
      <tr>
        <th>Column</th>
        <th>Data Type</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Id</td>
        <td>INT</td>
        <td>Message ID</td>
      </tr>
      <tr>
        <td>Sender</td>
        <td>VARCHAR</td>
        <td>Message sender</td>
      </tr>
      <tr>
        <td>Receiver</td>
        <td>VARCHAR</td>
        <td>Message recipient</td>
      </tr>
      <tr>
        <td>Message</td>
        <td>TEXT</td>
        <td>Message content</td>
      </tr>
      <tr>
        <td>Timestamp</td>
        <td>DATETIME</td>
        <td>Message timestamp</td>
      </tr>
    </tbody>
  </table>
</div>

## Developer Notes

### Encryption:
- The Diffie-Hellman algorithm ensures secure communication.

### Testing:
- Brute force tests can be conducted using the MiddleMan application.

### Extensibility:
- The messaging protocol and registration system are designed to be expandable.
