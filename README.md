# GOTHKIT
Create interactive applications with Golang, HTMX, and Templ

> The project (for now) is in the **experimental** phase.

## Table of content
- [GOTHKIT](#gothkit)
	- [Table of content](#table-of-content)
- [Installation](#installation)
- [Getting started](#getting-started)
	- [Application structure](#application-structure)
		- [assets](#assets)
		- [conf](#conf)
		- [db](#db)
		- [events](#events)
		- [handlers](#handlers)
		- [types](#types)
		- [views](#views)
	- [Development server](#development-server)
	- [Hot reloading the browser](#hot-reloading-the-browser)
- [Migrations](#migrations)
	- [Create a new migration](#create-a-new-migration)
	- [Migrate the database](#migrate-the-database)
	- [Reset the database](#reset-the-database)
	- [Seeds](#seeds)
- [Creating views with Templ](#creating-views-with-templ)
- [Validations](#validations)
- [Testing](#testing)
	- [Testing handlers](#testing-handlers)
- [Create a production release](#create-a-production-release)

# Installation
```
go install github.com/anthdm/gothkit@master
```

After installation you can create a new project by running: 
```
gothkit [myprojectname]
```

You can now navigate to your project:
```
cd [myprojectname]
```

# Getting started
## Application structure
### assets
### conf
### db
### events
### handlers
### types
### views

## Development server
You can run the development server with the following command:
```
make dev 
```

## Hot reloading the browser
Hot reloading is configured by default when running your application in development.

> NOTE: on windows or on in my case (WSL2) you might need to run `make watch-assets` in another terminal to watch for CSS and JS file changes.

# Migrations
## Create a new migration
```
make db-mig-create add_users_table
```

The command will create a new migration SQL file located at `app/db/migrations/add_users_table.sql`

## Migrate the database 
```
make db-up
```

## Reset the database 
```
make db-reset
```

## Seeds
```
make db-seed
```
This command will run the seed file located at `cmd/scripts/seed/main.go`

# Creating views with Templ 
Gothkit uses Templ as its templating engine. Templ allows you to create type safe view components that renders fragments of HTML. In-depth information about Templ can be found here:
[Templ documentation](https://templ.guide)

# Validations
todo

# Testing
## Testing handlers

# Create a production release
Gothkit will compile your whole application including its assets into a single binary. To build your application for production you can run the following command:
```
make build
```
This will create a binary file located at  `/bin/app_prod`.

Make sure you also set the correct application environment variable in your `.env` file.
```
APP_ENV	= production
```


