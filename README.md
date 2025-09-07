# secure-api-with-java-keystore
Tosca API Automation using Java Keystore Authentication
Project: Secure REST API using Java Keystore Authentication

🔒 Overview

This project demonstrates how to secure a RESTful API using two-way SSL (mutual TLS) authentication implemented with Java Keystore (JKS).

It provides a practical example of how client-server communication can be secured by using certificates and keystores, ensuring that both parties are authenticated before any data is exchanged.

This is particularly useful in enterprise applications, microservices, and any system that requires secure communication between trusted services.

🛠️ Project Structure

Language & Framework: Java with Spring Boot

Security Layer: Mutual SSL/TLS using Java Keystore and Truststore

Executable: A ready-to-run JAR file with all dependencies bundled

Files Included:

server-keystore.jks: Keystore file used to identify the server

server-truststore.jks: Truststore that contains the client's certificate

client-keystore.jks: Keystore file used to identify the client

client-truststore.jks: Truststore that contains the server's certificate

Sample REST controller (DemoApplication.java)

📦 How to Run the JAR. 

Download the project in Zip file. Unzip it and execute run.bat

By default, the server runs on HTTPS (https://localhost:8443) and is configured to only accept requests from authenticated clients with valid certificates.

🔐 What is Java Keystore Authentication?

Java Keystore (JKS) is a secure repository used to store cryptographic keys, X.509 certificates, and private keys. In the context of API security:

Keystore contains the server’s (or client’s) private key and certificate.

Truststore contains the certificates that are trusted by the server (or client).

🔁 Mutual TLS (Two-Way SSL) in This Project

Server Authentication
The client validates the server’s certificate using the client-truststore.

Client Authentication
The server validates the client’s certificate using the server-truststore.

This ensures that both sides are verified, which is much more secure than just one-way SSL.

✅ Use Cases

Securing internal APIs

B2B service integrations

Banking/Finance APIs

Microservices in zero-trust environments

🧪 Test the API

You can test the API using Tosca:

Endpoint: https://localhost:8443/employee

Authentication: Java Keystore

Keystore: Pass the path of client-keystore.jks [available in the downloaded project]

Keystore Password: changeit

Certificate: Client

Certificate Password: changeit

curl -k --cert client.pem --key client.key https://localhost:8443/hello
