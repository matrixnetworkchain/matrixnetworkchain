Enabling SSL on original client daemon
======================================
By default, MatrixNetwork allows JSON-RPC commands to be sent to http://localhost:22617
and accepts connections only from the localhost.

JSON-RPC Over SSL Setup
-----------------------
It can be configured to allow HTTPS connections.  You must follow the steps below
for this to work properly.

1. Setup a certificate and private key.  A self signed certificate will work.
    * cd ~/.MatrixNetwork
    * openssl genrsa -out server.pem 4096
    * openssl req -new -x509 -nodes -sha1 -days 3650 -key server.pem > server.cert
    (NOTE: you should NOT enter a passphrase)

2. Configure MatrixNetwork to use SSL
    * Stop your current matrixnetworkd or MatrixNetwork-Qt
    * Edit the matrixnetwork.conf and add
      rpcssl=1

3. Restart MatrixNetwork to make these changes take effect.

4. Optionally you can test SSL functionality using the openssl s_client command
    * openssl s_client -connect localhost:15004
