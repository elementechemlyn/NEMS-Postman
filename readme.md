# NEMS PostMan Collection
        
To use this collection you must first sign up for access to OpenTest and connect using the OpenVPN software.

Full details of OpenTest can be found here:

https://digital.nhs.uk/services/spine/open-access-test-environment-for-spine-opentest

You will need to ask for a MESH mailbox to be configured for you and for your ASID to be given permissions to use the NEMS service in OpenTest. The MESH mailbox will need to be configured for the workflow Ids listed here:

https://gist.github.com/elementechemlyn/61e55708602552254f6f6c801a6ee52a

In return you should recieve:

* An OpenVPN profile configuration file.
* A client key and certificate.
* A MESH Mailbox ID
* An OpenTest ASID (Accredited System Identifer) for your endpoint
* An OpenTest ODS Code for your endpoint
* An OpenTest domain name for your endpoint
* An OpenTest Party Key for your endpoint

You will then need to import the OpenTest postman environment and adjust the variables to include:

* The ASID sent to you upon creation of your OpenTest endpoint. This goes in the toASID variable.
* The MESH mailbox ID sent you upon creation of your OpenTest endpoint. This goes in the MESHBOXID variable.
* The ODS code sent to you upon creation of you OpenTest endpoint. This goes in the REQUESTERODS variable.
* The URL of your Opentest endpoint sent you you on creation of your OpenTest endpoint. This goes in the ISSUERURI.

Calls to Spine services are authenticated using a client certficiate. The certificate and key sent to you on creation of your OpenTest account need to be set up in Postman as described here:
https://learning.postman.com/docs/postman/sending-api-requests/certificates/

The Host field should be set to 192.168.128.11  - which is the endpoint for Spine Services in the OpenTest environment.

Once the environment is imported and your certifcates setup you can import the collection and run the requests (ensure you have selected the OpenTest environment in postman).

