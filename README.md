# Deploying-Multi-Tier-Website-Using-AWS-EC2

Project Overview
This project demonstrates how to deploy a multi-tier website using Amazon Web Services (AWS) EC2 instances and Amazon RDS for a scalable, high-availability architecture. The project covers launching EC2 instances, configuring Auto Scaling for high availability, and setting up a MySQL database on RDS. The website runs PHP and connects to the RDS instance for backend data storage.

Problem Statement
Company ABC is migrating its product to AWS and needs to ensure the product is highly available. They currently have:

A MySQL database.
A website built using PHP.
To ensure high availability, we will implement Auto Scaling on the website hosted on EC2 instances and connect the website to an Amazon RDS MySQL database.

Solution Architecture
EC2 Instances: Amazon EC2 will be used to host the website.
Auto Scaling: Auto Scaling will be configured to maintain at least 2 EC2 instances running at all times, ensuring high availability.
RDS MySQL Database: An Amazon RDS instance will be created for the MySQL database, which the website will use for persistent data storage.
Steps to Deploy the Website
1. Launch EC2 Instances
Launch at least two EC2 instances to host the PHP-based website.
Ensure proper security groups are in place to allow HTTP/HTTPS traffic.
2. Configure Auto Scaling
Set up an Auto Scaling group for the EC2 instances.
Configure Auto Scaling to maintain a minimum of 2 instances at all times.
Adjust the scaling policy to increase the number of instances during high traffic and reduce them during low traffic.
3. Set Up Amazon RDS MySQL
Create an Amazon RDS instance with MySQL as the database engine.
Set the database name as intel and configure the user credentials with:
Username: admin
Password: intel123
4. Configure Database
After creating the RDS instance, connect to it and create a table named data under the intel database using the following SQL query:
sql

CREATE TABLE data (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    email VARCHAR(255)
);
5. Update PHP Website to Connect to RDS
Modify the PHP code in your website to connect to the RDS instance.
Update the database hostname, username, and password in the PHP configuration to point to the RDS endpoint.
6. Configure EC2 Security Groups
Ensure traffic is allowed between the EC2 instances and the RDS instance.
Open necessary ports (3306 for MySQL) for the EC2 instances to communicate with the RDS instance.
7. Allow All Traffic to EC2 Instances
Set up security groups to allow all incoming traffic to the EC2 instances on ports 80 (HTTP) and 443 (HTTPS) to serve the website.
Technologies Used
Amazon EC2: To host the website.
Amazon RDS (MySQL): For the relational database.
Auto Scaling: For automatic scaling of EC2 instances.
Security Groups: For managing inbound and outbound traffic to instances.
Conclusion
By following these steps, we deployed a scalable and highly available multi-tier web application using AWS services like EC2 and RDS. Auto Scaling ensures that the website remains available even during traffic spikes, and Amazon RDS provides a reliable and scalable database solution.
