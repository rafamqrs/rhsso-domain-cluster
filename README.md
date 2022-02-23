# rhsso-domain-cluster
Sample of RHSSO DOMAIN on Ubuntu Server


### Download the RHSSO
```console
  wget ....
```

### Install Postgresql
```console

```

### Package de JDBC Driver
https://access.redhat.com/documentation/en-us/red_hat_single_sign-on/7.5/html/server_installation_and_configuration_guide/database-1

Or using the interface
....


### Start the RHSSO Master
```console
  ./bin/domain.sh --host-config=host-master.xml -b 0.0.0.0 -bmanagement 0.0.0.0
```

### Start the Slave 
```console
  ./server-one/bin/domain.sh --host-config=host-slave.xml -b 0.0.0.0 -bmanagement 0.0.0.0
```
### Disable HTTPS(I'm using the AWS EC2 and I haven't setup the certificate).
```console
$ ./kcadm.sh config credentials --server http://localhost:8080/auth --realm master --user admin
-- Apply sslRequired to none
$ ./kcadm.sh update realms/master -s sslRequired=NONE
```




