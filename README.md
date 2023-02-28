# DID-SSH
A DID for SSH to support and supported by the DID:GIT for document storage.

## STATUS
init.  only just begun, and work is incomplete - indeed, its only just started.

## Description

1. Generate an SSH key pair: First, you'll need to generate an SSH key pair, consisting of a public key and a private key. The public key will be used as the method-specific identifier for your DID:SSH.

2. Create a DID document: Next, you'll need to create a DID document that includes your SSH public key fingerprint as the method-specific identifier. The DID document can also include other information, such as your public DID, verification methods, and service endpoints. You will then use the DID:GIT method to publish this document to a git repository.

3. Publish the DID document using the DID:GIT method: To publish the DID document, you will create a new git repository and commit the DID document to the repository using the DID:GIT method. The repository should be publicly accessible so that other users and applications can resolve and authenticate your DID using the SSH protocol.

4. Authenticate with the SSH protocol: To authenticate with the SSH protocol using your DID:SSH, you can use your private key to sign a challenge provided by the remote server or service. The remote server or service can then verify your identity by checking your SSH public key fingerprint against the one listed in your DID document.

5. Update or deactivate the DID:SSH record as needed: If you need to update or deactivate your DID:SSH record, you can update or remove the associated SSH public key from your DID document, commit the changes to the git repository using the DID:GIT method, and then publish the updated document to the network.


## incomplete example;

[x] Generate an SSH key pair: Using a tool such as ssh-keygen, generate an SSH key pair consisting of a public key (e.g., id_rsa.pub) and a private key (e.g., id_rsa).

[x] Create a DID document: Create a JSON file that includes your SSH public key fingerprint as the method-specific identifier. Here's an example of what the file could look like:

Document Format:
``json
{
  "@context": "https://w3id.org/did/v1",
  "id": "did:ssh:github",
  "publicKey": [
    {
      "id": "did:ssh:github#keys-1",
      "type": "RsaVerificationKey2018",
      "controller": "did:ssh:github",
      "publicKeyPem": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDAAsJVjKo9qZsGzN2Q1+dRjwlv8Tfn0o0zr6TxUhU"
    }
  ]
}
``

### note
this method is intended to require [DID:GIT](https://github.com/WebCivics/did-method-git)

## SSH Specs
https://www.openssh.com/specs.html

### PubKey in DNS 
https://www.rfc-editor.org/rfc/rfc4255
