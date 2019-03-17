# Recon cli
Recon command line interface (cli) for stock estimates

## About
This cli is used to predict the next five day estimates for some underlying asset.

## Acquiring the Image from AWS Marketplace
Coming soon! We are in the process of getting listed in the [AWS Marketplace](https://aws.amazon.com/marketplace).
### Launch and Connect to your Image
- Launch an EC2 instance from the previously acquired Amazon Machine Image (AMI) with your favorite configurations. You should at least allow incoming connections on port 22 for ssh access.
- Once the instance is up and running, connect using your favorite ssh client.
- You're now connected!

[This AWS guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html) provides general knowledge related to launching a new EC2 instance in AWS.

## Usage
### Configure the Recon cli
- From the previous step, you should be connected to `ubuntu@<my-ip>`.
- Because the Recon cli is written in [the Go programming language](https://golang.org/), we need to set our gopath so we can use the application:
  - execute this command to configure your `path` variable for use with go: `export PATH=$PATH:$(go env GOPATH)/bin`
- You're image is now configured!

### Run the Recon cli
- Now that you're all set up, you can execute the following commands:
  - `recon --help` for general information
  - `recon --version` to get the version number
  -  `recon <input-your-ticker-symbol>` to get the next five day estimates for the ticker yor provided.
  - For a complete example, see below:
```
ubuntu@<my-ip>:~$ ls
go
ubuntu@<my-ip>:~$ export PATH=$PATH:$(go env GOPATH)/bin
ubuntu@<my-ip>:~$ recon -v
Recon CLI, By Annual Computers, LLC version 0.0.1
ubuntu@<my-ip>:~$ recon spy
Getting data for symbol: spy
The five day estimates for that symbol are:  [["Day 1","282.4"],["Day 2","282.58"],["Day 3","282.76"],["Day 4","282.94"],   ["Day 5","283.13"]]
ubuntu@<my-ip>:~$ 
```

### Notes
Currently, only support for `recon spy` is enabled. "SPY" is the [S&P 500 etf](https://finance.yahoo.com/quote/SPY?p=SPY).

We are adding additional APIs regularly for your favorite companies. Feel free to open an issue here with a company you'd like to see added.
