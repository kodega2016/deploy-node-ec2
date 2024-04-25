First of all we need to create a EC2 instance in the AWS console with a key-pair. Then we need to connect to the EC2 instance and install the required packages.
we can run the following commands to install docker in the EC2 instance.

```bash
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo usermod -a -G docker ec2-user
```

we have to add a security group to the EC2 instance to allow the port 80. We can do this by going to the security group of the EC2 instance and add a new inbound rule with the port 80.

It will install docker in the EC2 instance. Now we can verify the installation by running the following command.

```bash
docker version
```

Now we need to create a docker image and push the image to the docker hub.

```bash
docker image build -t <dockerhub-username>/<image-name>:<tag> .
docker login
docker image push <dockerhub-username>/<image-name>:<tag>
```

So after that we can run the following command to run the docker container.

```bash
docker container run -d -p 80:80 <dockerhub-username>/<image-name>:<tag>
```
