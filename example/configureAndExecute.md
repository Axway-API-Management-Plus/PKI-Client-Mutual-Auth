# PKI-Client-Mutual-Auth
Sample to create PKI client authentication with validation and RBAC authorization with mutual authentication enforcement. This document shows an example of the setup and testing of this policy.

## Prerequisites

To follow this example you will need the following:

- A client public/private key pair with a single depth level.
- The issuer public certificate.
- A directory to lookup customer attributes.

A sample single depth client-issuer relationship can be seen here:
![alt text](https://github.com/dwille-axway/PKI-Client-Mutual-Auth/blob/master/example/src/certificateChain.png "Certificate and Issuer")

## Step By Step

1. In Policy Studio, navigate to 'Environment Configuration --> Certificates and Keys --> Certificates'. Select the 'CA' tab and choose the 'Create/Import' button in the bottom right of the interface. Click "Use Subject". Click "Ok".
![alt text](https://github.com/dwille-axway/PKI-Client-Mutual-Auth/blob/master/example/src/cacertImport.png "Configure CA Trust")
2. Navigate to 'Environment Configuration --> Listeners --> API Gateway --> Default Services --> Ports'. Click 'Add --> HTTPS Interface'. Fill out information on the Network tab and select a CA certificate. On the Mutual Auth tab choose to 'Require Client Certificates' with a depth of "1", then search for and select the issuer CA. This will allow the API Gateway to provide a CA list during the SSL handshake to give clients browsers/applications of trusted CAs, require submission of a client certificate on calls to protected resources on the associated port, and enforce issuance of the submitted certificate only to selected trusted CAs.
![alt text](https://github.com/dwille-axway/PKI-Client-Mutual-Auth/blob/master/example/src/mutualAuth.png "Configure Mutual Auth")


## API Management Version Compatibilty
This artefact was successfully tested for the following versions:
- V7.5.3

## Contributing

Please read [Contributing.md](https://github.com/Axway-API-Management/Common/blob/master/Contributing.md) for details on our code of conduct, and the process for submitting pull requests to us.


## Team

![alt text][Axwaylogo] Axway Team

[Axwaylogo]: https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png  "Axway logo"


## License
[Apache License 2.0](/LICENSE)
