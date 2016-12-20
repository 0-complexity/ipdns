# ipdns
Stateless dns server serving ip addresses based on parsing the domain

## description
ipdns takes the domain and calculates an IPAddress out of it.

The domain names should be formatted as follows:
```
mylittleserver-2130706433.mydomain.ext
```
ipdns will serve **127.0.0.1** as a result, because ipdns parsed the number **2130706433**, which represents the ip, in the domain from its decimal representation in the more familiar IPv4 string format.

## installation

```
sudo pip install ipdns
```

## running ipdns

ipdns is witten as a twistd plugin. See https://twistedmatrix.com for more information on Twisted and the twistd daemon.

### parameters

ipdns only needs one parameter which can only passed on the command line.
```
Usage: twistd [options] ipdns [options]
Options:
-d, --domain=  The top domain serving ipdns for. (required)
-s, --server=  DNS for this mail server. (required)
-e, --email=   Email address of domain admin. (required)
    --version  Display Twisted version and exit.
    --help     Display this help and exit.
```

Use the following command to make ipdns serve ipaddresses for **yourdomain.foo**:
```
twistd ipdns --domain=yourdomain.foo
```
