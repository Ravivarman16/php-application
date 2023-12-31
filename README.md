# **EFFICIENT THREE-TIER APPLICATION DEPLOYMENT ON AWS WITH EC2 AND RDS**

## **PROBLEM STATEMENT:**
The current infrastructure faces challenges handling increased user traffic, impacting overall performance. Deploying a three-tier architecture on AWS is essential for optimizing scalability, reliability, and resource utilization. The objective is to enhance the user experience by leveraging EC2 for presentation, Apache server for application logic, and MySQL RDS for database storage.

## **USE CASE - SCENARIO:**
The web application experiences fluctuations in user traffic, leading to performance degradation. The deployment of a three-tier architecture on AWS involves utilizing Amazon EC2 instances for the presentation layer, an Apache server for application logic, and MySQL RDS for efficient and secure database storage. This approach ensures scalability and effective data management tailored to the specific technology stack without incorporating S3 or Lambda.

## **TASKS TO BE PERFORMED:**
1. Create a MySQL database on Amazon RDS:
   - Database Name: php
   - Database Password: phpapplication123
   - Table: data
   - Execute table.sql to create the necessary table structure.

2. Connect to the EC2 instance and deploy the application with Apache.
3. Verify the application output to ensure proper functionality.

---


## **SOLUTION:**
### **PRE-REQUIREMENTS:**
- Cloud           : **AWS**
- Server          : **EC2**
- Database        : **RDS MySQL**

**GitHub repository:** [https://github.com/Ravivarman16/php-application.git](https://github.com/Ravivarman16/php-application.git)

---


### **STEPS TO IMPLEMENT:**

**STEP:1 - CREATING AN AWS MYSQL DATABASE AND CREATING A TABLE:**

- **Database Name:** php
  
- **Database Password:** phpapplication123
- **Table Name:** data

- After creating a database, connect it with the command either on EC2 instance or on MySQL Workbench:
    ```bash
    mysql -u admin -p <databasename> -h <database endpoint>
    ```

- After connecting to the database, execute the SQL query named table.sql which is provided in the above repository.

---

**STEP:2 - CREATING AN EC2 INSTANCE AND INSTALLING REQUIRED PACKAGES & SOFTWARES:**

- After launching an instance, connect it with **Instance Connect.**

- Clone the GitHub repository:
    ```bash
    git clone https://github.com/Ravivarman16/php-application.git 
    cd php-application
    ```

- Execute the `package.sh` script by changing its file permission.
    ```bash
    chmod +x package.sh
    ./package.sh
    ```

- Check the versions of the following packages using the command:
    ```bash
    apache2 --version
    mysql --version
    php --version
    ```

**Note:** Ensure security groups are configured accordingly for database connection.

---

**STEP:3 - ALTERING register.php AND loginprocess.php FILES BY INSERTING DATABASE INSTRUCTIONS:**

- Open `register.php` using the vi editor:
    ```bash
    vi register.php
    ```

- Insert the following database instructions:
    ```php
    $host = 'database endpoint';
    $username = 'database_username';
    $password = 'database password';
    $database = 'database name';
    ```

- Save and exit the file.

- Open `loginprocess.php` using the vi editor:
    ```bash
    vi loginprocess.php
    ```

- Insert the same database instructions:
    ```php
    $host = 'database endpoint';
    $username = 'database_username';
    $password = 'database password';
    $database = 'database name';
    ```

- Save and exit the file.

---

**STEP:4 - DEPLOYING THE APPLICATION ON APACHE SERVER:**

- Move the application codes to the `/var/www/html` location:
    ```bash
    mv * /var/www/html/
    ```

- Check the output by pasting the public IP address of the instance in a web browser:
    ```
    http://<public_ip>:80
    ```

- Ensure that the application is accessible by navigating to the provided public IP address on port 80.

---

## APPLICATION OUTPUT:

![image](https://github.com/Ravivarman16/php-application/assets/129171351/9dc4aa58-93a0-45b1-ab27-96e79cee228e)


![image](https://github.com/Ravivarman16/php-application/assets/129171351/6ce6ddbb-b19b-42fe-a7ba-c41155deed27)


![image](https://github.com/Ravivarman16/php-application/assets/129171351/f89415f4-4643-4cb2-847e-0183484dd666)


![image](https://github.com/Ravivarman16/php-application/assets/129171351/d6e302f3-091f-4b8e-9695-ba8988fdc9ac)


![image](https://github.com/Ravivarman16/php-application/assets/129171351/bcc69638-9153-433f-b269-fce5d849608c)


---

## BENEFITS OF DOING ABOVE TASK:

- **Scalability with EC2:**
  - Horizontally scale the presentation layer using Amazon EC2 instances to handle varying user loads.

- **Application Logic with Apache Server:**
  - Leverage the Apache server for application logic, ensuring efficient processing of user requests.

- **Reliable Database Storage with MySQL RDS:**
  - Ensure high availability and data integrity using MySQL RDS for efficient and secure database storage.

- **Resource Optimization:**
  - Efficiently manage resources with a dedicated architecture for presentation, application, and database layers.

- **Cost-Effective Solution:**
  - Pay only for the utilized resources, optimizing costs based on actual demand.

---

### ALL THE STEPS AND SOLUTION HAVE BEEN UPLOADED IN THIS PDF FILE:

[Efficient Three-Tier Application Deployment on AWS with EC2 and RDS.pdf](https://github.com/Ravivarman16/php-application/files/13792065/Efficient.Three-Tier.Application.Deployment.on.AWS.with.EC2.and.RDS.pdf)

