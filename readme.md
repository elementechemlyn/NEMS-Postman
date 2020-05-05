# NEMS PostMan Collection
This PostMan Collection demonstrates the use of the NEMS/DCH service in OpenTest. OpenTest provides access to a full 
working version of the NEMS service to manage subscriptions as well as MESH mailboxes to recieve events. Access to NEMS/DCH in OpenTest does not require an HSCN Connection or any formal access processes such as the SCAL or testing evidence required for other NHS Path to Live environments and can be used for initial development and exploration work.

To use this collection you must first sign up for access to OpenTest and connect using the OpenVPN software.

Full details of OpenTest can be found here:

https://digital.nhs.uk/services/spine/open-access-test-environment-for-spine-opentest

You will need to ask for a MESH mailbox to be configured for you and for your ASID to be given permissions to use the NEMS service in OpenTest. The MESH mailbox will need to be configured for the workflow Ids listed here:

https://gist.github.com/elementechemlyn/61e55708602552254f6f6c801a6ee52a

You should also request access to the NEMS testing tool which is available as a web application on OpenTest at:

http://192.168.128.17

The testing tool allows events that cannot be published directly such as PDS events to be generated.

In return you should recieve:

* An OpenVPN profile configuration file.
* A client key and certificate.
* A MESH Mailbox ID
* An OpenTest ASID (Accredited System Identifier) for your endpoint
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

The Host field should be set to 192.168.128.11  - which is the host address for Spine Services in the OpenTest environment.

Once the environment is imported and your certifcates setup you can import the collection and run the requests (ensure you have selected the OpenTest environment in postman).

Whilst the MESH API is available in OpenTest this postman collection does not yet include example calls. Event Messages can be recived by downloading the MESH Client:

https://digital.nhs.uk/binaries/content/assets/website-assets/services/message-exchange-for-social-care-and-health-mesh/mesh-installation-pack-client-6-2-0.rar

It can be configured to access your MESH mailbox on Opentest using the Keystore available here:

https://digital.nhs.uk/services/path-to-live-environments/opentest-environment#message-exchange-for-social-care-and-health-mesh-keystore-files-to-download

The password for your Opentest MESH Mailbox will have been provded when you signed up for OpenTest access.
