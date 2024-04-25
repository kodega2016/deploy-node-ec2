First of all we need to create a EC2 instance in the AWS console with a key-pair. Then we need to connect to the EC2 instance and install the required packages.
we can run the following commands to install docker in the EC2 instance.

```bash
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo usermod -a -G docker ec2-user
```

It will install docker in the EC2 instance. Now we can verify the installation by running the following command.

```bash
docker version
```
