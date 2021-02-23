# Strapi Heroku Application Template

This is a bare bones basic strapi template builder for Heroku.

This is set to be a simple deployable Strapi instance from git, this allows you to be in full control and have full source control of all the Strapi instance changes.

If it's just in Heroku that Content Types are made, then they are not stored in source control, with this version, it allows the use of a shared PostgreSQL database and to allow changes on a dev machine which is then pushed to the Heroku application instance.

**Note: If there are any Content Type changes made on the Heroku application and then it is deployed from git to Heroku instance it will overwrite what has been created on the Heroku instance**

## TODO: This to do in order for the instance to work

### Requirements:
- Heroku Account
- Cloudinary account
- Gitlab Account (if you want to use CI/CD via Gitlab)
- Heroku bare bones application
- Heroku PostgreSQL database attached to instance

#### (optional - for Production Environment)
- Heroku bare bones application
- Heroku PostgreSQL database attached to instance

### Local machine
- Create a copy of the `.env.example` file and change it to just `.env`
- fill all the fields with the corresponding credentials
  - You can attain the Cloudinary details at the top of the dashboard once you login to cloudinary.
  - Once the Heroku Database has been created, go to settings and view the Credentials and all the details should be listed there.
  - For DB creds in the `.env` it will be:
    - DATABASE_HOST
    - DATABASE_NAME
    - DATABASE_USERNAME
    - DATABASE_PASSWORD

### Gitlab
***There are 2 versions here (UAT and PROD) just in case you create 2 applications, 1 for testing and 1 for live, it's up to you if you want to maintain a testing environment or not.**
- Create 4 build variables in the repository CI/CD for:
  - HEROKU_API_KEY_UAT
  - HEROKU_API_KEY_PROD
  - HEROKU_UAT_APP_NAME
  - HEROKU_PROD_APP_NAME

### Heroku
- In Heroku, for the application to function you need to set the same variables as in the `.env` file on local machine (for production it will be different credentials).
- These values would be:
  - CLOUDINARY_CLOUD_NAME
  - CLOUDINARY_API_KEY
  - CLOUDINARY_API_SECRET

- If you are not using a Heroku based Database, then you will most likely need to add all the Database variables in the settings as well:
  - DATABASE_HOST
  - DATABASE_NAME
  - DATABASE_USERNAME
  - DATABASE_PASSWORD
  - DATABASE_PORT

## UPDATE:
- (24/02/2021) Updated to Strapi v 3.5.0
  - This new version also includes Sentry Plugin usage
    - To add Sentry error tracking follow this guide to add it, you will need a sentry account and project setup first
    - [introducing-sentry-plugin](https://strapi.io/blog/introducing-sentry-plugin)

Sqeel404
[@sqeel404](https://twitter.com/sqeel404)
