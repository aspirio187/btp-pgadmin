# pgAdmin on SAP BTP using PostgreSQL service

## Description

This is a simple example of deploying pgAdmin on SAP BTP Cloud Foundry environment using PostgreSQL service instance. Doing that, you can easily access the database using pgAdmin web interface instead of having to install DBeaver or pgAdmin locally and having to ssh tunnel into your app using its credentials and certificates.

## Prerequisites

- An SAP BTP account with Cloud Foundry environment enabled
- PostgreSQL service instance created in your Cloud Foundry space
- Cloud Foundry CLI installed and configured to use your SAP BTP account
- Basic knowledge of Cloud Foundry and PostgreSQL

## Deployment

1. Clone this repository to your local machine.
2. Navigate to the cloned directory.
3. Update the `manifest.yml` file with your PostgreSQL service instance name and desired pgAdmin credentials.
4. Run the following command to deploy the application `bash cf push -f manifest.yml`
5. Once the deployment is complete, you can access pgAdmin using the URL provided in the Cloud Foundry application summary.
6. Log in to pgAdmin using the credentials you specified in the `manifest.yml` file.
7. Add a new server in pgAdmin using the PostgreSQL service instance credentials.

## Shoutout

This example was inspired by the blog post from SAP Community: [PostgreSQL on SAP BTP - (how-to) deploy and use pgAdmin web version](https://community.sap.com/t5/technology-blog-posts-by-sap/postgresql-on-sap-btp-how-to-deploy-and-use-pgadmin-web-version/ba-p/13788231).

This LinkedIn post also helped me into understand this and setting it up: [Thinking of using PostgreSQL on SAP BTP? Here is some help to get you on the way!](https://www.linkedin.com/posts/shaunbradridge_demystify-postgresql-for-sap-btp-and-deploy-activity-7252170557557727232-fAeh/). This post was referencing this post: [Demystify PostgreSQL for SAP BTP and Deploy pgAdmin4](https://www.betadigital.com.au/post/demystify-postgresql-for-sap-btp-and-deploying-pgadmin4)

The other way of logging into the PostgreSQL service instance is described in the blog post: [SAP BTP PostgreSQL Database import to pgAdmin with SSH Tunnel (Local Access)](https://community.sap.com/t5/technology-blog-posts-by-members/sap-btp-postgresql-database-import-to-pgadmin-with-ssh-tunnel-local-access/ba-p/13574449).

This community blog also explains the same principle as the one above but it is instead working with pgadmin installed on the local machine and using ssh tunneling. **I would NOT recommend this method as pgadmin is not the most efficient tool. Rather use pgadmin in the web for simple operations or use DBeaver**: [PostgreSQL on SAP BTP - Activate (create) an extension using pgAdmin tool](https://community.sap.com/t5/technology-blog-posts-by-sap/postgresql-on-sap-btp-activate-create-an-extension-using-pgadmin-tool/ba-p/13723425)

Many thanks to all the authors above for sharing their knowledge!
