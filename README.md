# strapi-connector-mongodb-atlas

MongoDB Atlas hook for the Strapi framework v3. Forked from the original Strapi mongoose hook to make it work with MongoDB Atlas.

**Note: USE WITH CAUTION!**

### This connector works with Strapi V3 only

## Setup guide

### Install npm package
```
npm install --save strapi-connector-mongodb-atlas
```

### Update config
/config/database.js
```
module.exports = ({ env }) => ({
  defaultConnection: 'default',
  connections: {
    default: {
      connector: 'mongoose',
      settings: {
        host: env('DATABASE_HOST', 'cluster-uri'),
        srv: env.bool('DATABASE_SRV', true),
        port: env.int('DATABASE_PORT', 27017),
        database: env('DATABASE_NAME', 'db_name'),
        username: env('DATABASE_USERNAME', 'db_user'),
        password: env('DATABASE_PASSWORD', 'db_pass'),
      },
      options: {
        authenticationDatabase: env('AUTHENTICATION_DATABASE', null),
        ssl: env.bool('DATABASE_SSL', true),
        useCreateIndex: false
      },
    },
  },
});
```