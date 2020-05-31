## Docker setup on Amazon Linux

```
sudo yum update -y
sudo yum install -y docker
sudo service docker start
```

## Allow ec2-user access
```
sudo usermod -a -G docker ec2-user
```
