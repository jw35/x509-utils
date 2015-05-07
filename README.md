# x509-utils

A collection of scripts for working with x509 certificate and certificate requests.

Script                | Description
--------------------- | -----------------------------------------
display-certificate   | Read PEM-formatted certificate data from the supplied file, or stdin. Remove leading/trailing blanks, append/prepend BEGIN/END lines if missing, and lob the result at 'openssl x509' with some helpful formatting options. Particularly handy for displaying certificate blocks extracted from Shibboleth configuration files.
display-csr           | Read CSR data from the supplied file, or stdin. Append/prepend BEGIN/END lines if missing, and lob the result at 'openssl req' with some helpful formatting options
get-certificate       | Connect to a remote SSL-capable server and extract its certificate 
get-chain             | Connect to a remote SSL-capable server and display the chain of certificates that it supplies
get-sha1              | Connect to a remote SSL-capable web server, extract its certificate and display its SHA-1 --> SHA-2 transition status
sumarise-certificate  | As 'display-certificate' but only show selected information from the certificate
make-csr              | Wrapper around 'openssl req' to aid generating keys and CSR's from the command line. In particular allows SANs to be supplied without having to write an openssl config file. 

These scripts all just wrap the `openssl` command-line tool which must be available on PATH. Most error handling (like feeding a CSR to `display-certificate`) is left to `openssl`, with predictable results...

