# Create Portal Keycloak Client

## Prerequisites

- Ansible installed >= v2.7
    -   Mac: `brew install ansible`

## How-to

The shell script in this repo calls the "create-keycloak-client.yaml" playbook. This playbook uses the variables defined in keycloak-vars.yaml

*prior to running ensure you are logged into your k8s cluster and is set as your current context*

1. Define variables
```bash
$ cat > keycloak-vars.yaml <<EOF
keycloak_url: "https://keycloak.example.com:8080/auth" 
keycloak_client_id: test-client
portal_redirect_uris: ["https://portal.mycompany.corp/callback", "http://portal.mycompany.corp/callback"]
portal_namespace: petstore
EOF
```

2. Run shell script
```bash
./register-portal-keycloak.sh
```