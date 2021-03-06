## THIS REPO IS DEPRECATED, PLEASE SEND ALL PULL REQUESTS TO https://github.com/common-group/services-core INSTEAD.

# EFS123 - WMSEED
[![Circle CI](https://circleci.com/gh/catarse/wmseed/tree/master.svg?style=svg)](https://circleci.com/gh/wmseed/wmseed/tree/master)
[![Coverage Status](https://coveralls.io/repos/wmseed/wmseed/badge.svg?branch=master)](https://coveralls.io/r/wmseed/wmseed?branch=master)
[![Code Climate](https://codeclimate.com/github/wmseed/wmseed/badges/gpa.svg)](https://codeclimate.com/github/wmseed/wmseed)

The next version of crowdfunding platform from Brazil

## An open-source crowdfunding platform for creative projects

Welcome to WMseed's source code repository.
Our goal with opening the source code is to stimulate the creation of a community of developers around a high-quality crowdfunding platform.

You can see the software in action in http://efs123.xyz.
The official repo is https://github.com/wmseed/wmseed

WMSEED on Slack at https://Wmseed.slack.com 
WMSEED Development Community https://gitter.im/wmseen/community.

EFS123 on Slack https://Efs123.slack.com 
EFS123 Development Community https://gitter.im/EFS-123/community.

# Getting started
Dependencies
To run this project you need to have:

Ruby 2.4.1

Rails 4.2

postgREST 0.3

PostgreSQL 9.4

OSX - Postgres.app
Linux - $ sudo apt-get install postgresql
Windows - PostgreSQL for Windows
IMPORTANT: Make sure you have postgresql-contrib (Additional Modules) installed on your system.

Setup the project
Clone the project

  $ git clone https://github.com/wmseed/wmseed.git
Enter project folder

  $ cd wmseed
Create the wmseed.yml

  $ cp config/database.sample.yml config/database.yml
You must do this to configure your local database! Add your database username and password (unless you don't have any).

* Install the gems

        $ bundle install

* Install the front-end dependencies

        $ npm install

    Requires [Node.js](https://nodejs.org/download/) and its package manager, *npm*.

* Create and seed the database

        $ rake db:create db:migrate db:seed

* Configure the API server

	We provide authentication through JWT ([JSON Web Tokens](http://jwt.io/)) and it can be configured by `CatarseSettings` into rails console.

		$ bundle exec rails console
		> CatarseSettings[:api_host] = "http://localhost:3004" # postgREST server url
		> CatarseSettings[:jwt_secret] = "gZH75aKtMN3Yj0iPS4hcgUuTwjAzZr9C" # this token is just a valid example

If everything goes OK, you can now run the project!

### Running the project

* Run API server

	After downloading PostgREST 0.3.x you can unpack and run the executable as below.

		$ ./postgrest postgres://postgrest@localhost/catarse_development -a anonymous --jwt-secret gZH75aKtMN3Yj0iPS4hcgUuTwjAzZr9C -s 1 -p 3004

* Run Rails server
```bash
$ rails server
```

Open [http://localhost:3000](http://localhost:3000)

### Translations

We hope to support a lot of languages in the future, so we are willing to accept pull requests with translations to other languages.

Thanks a lot to Daniel Walmsley, from http://purpose.com, for starting the internationalization and beginning the English translation.

## Payment gateways

Currently, we support pagarme through our payment engines. Payment engines are extensions to Catarse that implement a specific payment gateway logic.

If you have created a different payment engine to Wmseed, please contact us so we can link your engine here.
If you want to create a payment engine, please join our mailing list at http://groups.google.com/group/wmseed-dev

  List of payment enginees that are being developed or need to be developed further

    https://github.com/wmseed/wmseed_pagarme (payment engine used by efs123.xyz)
    https://github.com/devton/wmseed_paypal_express (currently out of date and not maintained)
    https://github.com/sushant12/wmseedStripe (just starting to be developed and needs extra hands -- please pitch in...)

## How to contribute with code

Discuss your plans in our mailing list (http://groups.google.com/group/catarse-dev).

After that, just fork the project, change what you want, and send us a pull request.

### Best practices (or how to get your pull request accepted faster)

* Follow this style guide: https://github.com/bbatsov/ruby-style-guide
* Create one acceptance tests for each scenario of the feature you are trying to implement.
* Create model and controller tests to keep 100% of code coverage in the new parts you are writing.
* Feel free to add specs to committed code that lacks coverage ;)
* Let our tests serve as a style guide: we try to use implicit spec subjects and lazy evaluation wherever we can.

## Credits

Author: Daniel Weinmann / Jean Wallet

Contributors: You know who you are ;) The commit history can help, but the list was getting bigger and pointless to keep in the README.

## License

Copyright (c) 2016 AYCHDeveloper

Licensed under the AGPL and MIT license (see MIT-LICENSE file)
