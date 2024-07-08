# go-tcp-vm

A TCP echo server deployed on an EC2 VM, demonstrating cross-platform Go compilation, secure file transfer, and remote execution tested with netcat.

## Project Setup and Execution

a step-by-step process to run this project on an EC2 instance:

### 1. Build the binary locally:

```
go build -o go-tcp-vm
```
You may need to cater your build env to the EC2 instance environment: 
```
GOOS=linux GOARCH=amd64 go build -o go-tcp-vm
```

### 2. Copy the binary to the EC2 instance:

```
scp -i /path/to/your-key.pem go-tcp-vm ec2-user@your-ec2-public-dns:/home/ec2-user/
```

### 3. ssh into your EC2 instance and prepare the binary:

```
ssh -i ...
```
```
chmod +x go-tcp-vm
```

### 4. Run the binary on the EC2 instance:

```
./go-tcp-vm
```

### 5. Configure any security measures on EC2 dashboard to open port 8080 and test the connection:

```
nc your-ec2-public-dns 8080
```
