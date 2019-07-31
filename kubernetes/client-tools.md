# Installing the Client Tools
In this lab you will install the command line utilities required to complete this tutorial: [cfssl,](https://github.com/cloudflare/cfssl) [cfssljson](https://github.com/cloudflare/cfssl), and [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl).

## Install CFSSL
The `cfssl` and `cfssljson` command line utilities will be used to provision a [PKI Infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure) and generate TLS certificates.

Download and install `cfssl` and `cfssljson` from the cfssl [repository:](https://pkg.cfssl.org/)
### Linux 

```wget -q --show-progress --https-only --timestamping \
  https://pkg.cfssl.org/R1.2/cfssl_linux-amd64 \
  https://pkg.cfssl.org/R1.2/cfssljson_linux-amd64```<\br>
  
```chmod +x cfssl_linux-amd64 cfssljson_linux-amd64```

```sudo mv cfssl_linux-amd64 /usr/local/bin/cfssl```

```sudo mv cfssljson_linux-amd64 /usr/local/bin/cfssljson``` 

### Verification

Verify `cfssl` version 1.2.0 or higher is installed:

`cfssl version`
>output

```Version: 1.2.0
Revision: dev
Runtime: go1.6```

>The cfssljson command line utility does not provide a way to print its version.
