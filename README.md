# grunt-mongo-backup

Import and export data into mongodb using mongobackup.  This grunt task is a simple wrapper around mongodump and mongorestore.  It's a great way to configure your backups and share data.

## Getting Started
This plugin requires Grunt `~0.4.5

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```bash
npm install grunt-mongo-backup --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```bash
grunt.loadNpmTasks('grunt-mongo-backup');
```

## The mongobackup task

### Overview
In your project's Gruntfile, add a section named `mongobackup` to the data object passed into `grunt.initConfig()`.  This is a multi-task, so feel free to add as many configurations as you want.

```javascript
grunt.initConfig({
  mongobackup: {
    local: {
      options: {
        host: 'localhost',
        port: '27017',
        db: 'database-dev',
        dump:{
          out: './dump',
        },    
        restore:{
          path: './dump/database-dev',
          drop: true
        }
      }
    }
  }
});
```

## Basic Usage

### Mongodb Dump 
```bash
grunt mongobackup:db:dump
```

### Mongodb Restore 
```bash
grunt mongobackup:db:restore
```

## Options

Consult mongodb docs - mongodump and mongorestore for optional params.  

NOTE: NOT ALL OPTIONS ARE AVAILABLE.  Change to suit your needs.

