📊 Data Ingestion from S3 to RDS with Fallback to AWS Glue

This project implements a Dockerized Python application that ingests data from a CSV file in Amazon S3, attempts to push it into an RDS MySQL-compatible database, and automatically falls back to AWS Glue if the RDS operation fails.

📦 Goal
🔸Read CSV file from Amazon S3

🔸Attempt to push to Amazon RDS (MySQL- compatible)

🔸If the RDS connection/upload fails:

🔸Automatically fall back to AWS Glue Data Catalog Register the dataset and schema based on S3 file

🧰 AWS Services Used

🔸Amazon S3: Source for the CSV file

🔸Amazon RDS: MySQL-compatible database

🔸AWS Glue: Backup ingestion mechanism and catalog registration

🔸IAM: Role-based access to S3 and Glue

🔸Docker: Containerization of the Python app

🚀 Step 1: Set up AWS Services (S3, RDS, Glue)

✅ S3 Bucket

1)Create bucket my-s3-data-bucket.

2)Upload data.csv or data.xlsx

✅ RDS MySQL

1)Create RDS MySQL database mydb.

2)Enable public access.

✅ AWS Glue

1)Create Glue Database.

2)Create Crawler for S3 data.

🚀 Step 2: Launch EC2 Instance

1)Go to AWS EC2 Console.

2)Click Launch Instance.

3)Select Amazon Linux 2 AMI.

4)Choose t2.micro (Free Tier).

5)Configure Security Group:

6)Allow SSH (port 22), HTTP (80), and MySQL/Aurora (port 3306).

7)Create a key pair (download my-key.pem).

8)Launch.

🛠️ Install Docker

sudo yum update -y

sudo amazon-linux-extras install docker -y

sudo service docker start

sudo usermod -a -G docker ec2-user

🛠️ Install Python 3

sudo apt install python3 -y

🐳 Build Docker Image

docker build -t s3-rds-glue-ingestion .

▶️ Run Docker Container

(in run docker file changes add your access key, secret key,region,rds host,rds db,rds user,rds password,s3 bucket name,s3 file key according then run the file and see the output)



