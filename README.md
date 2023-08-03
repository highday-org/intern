# intern
Internship Highday

# HighDay
![](https://img.shields.io/badge/Ruby-informational?style=flat&logo=ruby&logoColor=white&color=A61414) ![](https://img.shields.io/badge/-Vue-4fc08d?style=flat&logo=vuedotjs&logoColor=fff)

Share your professional stories

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

```
### ruby 2.7.5
use rbenv on MacOS or Linux

### bundle 2.0.2
gem install bundler
rbenv rehash

### postgresql > 9.6
use brew on MacOS

### nodes.js > 10
use brew on MacOS

### yarn
see official website

### mkcert (https://blog.filippo.io/mkcert-valid-https-certificates-for-localhost/)
mkcert -install
```

## Windows OS Setup instruction

Install Ruby 2.7 and Rails

Install NodeJS, VueCLI, PostgreSQL

Install SSL and add highday.kinoba domain

Install RedisServer on WSL

Run the App and test it

Rbenv-ruby-install
https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-18-04

wsl-2-install
https://docs.microsoft.com/fr-fr/windows/wsl/install

redis-server-install-in-wsl
https://anggo.ro/note/installing-redis-in-ubuntu-wsl/

Doc
https://github.com/highday-org/intern/blob/main/README.md

hosts:
c:\Windows\System32\Drivers\etc
127.0.0.1       highday.kinoba
========================================


### Installing and running the app

#### HTTPS

```
./scripts/setup-local-ssl-env.sh
./scripts/dev-ssl
```

➡️ [https://highday.kinoba:5100](https://highday.kinoba:5100)

#### HTTP (for when HTTPS doesn't work for you)

```
./scripts/dev
```

➡️ [http://localhost:5100](http://localhost:5100)


## Running the tests

Tests can be run locally or on Docker

### Locally

Run the command from the `api` folder:

```
bundle exec rspec
```

To view the acceptance tests:

```
HEADLESS=0 bundle exec rspec
```

### Docker

Docker tests are run on Jenkins following the pipeline `Jenkinsfile`

### And coding style tests

Rubocop tests are run after functional tests

```
bundle exec rubocop
```

Also TypeScript code is linted with es-lint and SASS code with sass-lint.

## Deployment

app.highday.fr is hosted on OVH VPS.

To deploy, simply `git push`

Jenkins will run the tests and push to staging if everything is green.

After that, to deploy to production, run the Jenkins job called `deploy-highday`.

This job merges the content of the staging branch with the master, builds the production Docker images
and pushes everything on the production servers.

### SSL Certificates

Generated with Letsencrypt directly on the server with Docker:

```
cd /var/www/letsencrypt
docker-compose up -d
```

## Built With

* [Ruby on Rails](https://rubyonrails.org/) - The framework used to build the API
* [VueJS](https://vuejs.org/) - The framework to build the web app

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/Kinoba/highday/tags).

## Authors

* **Sharon Tordjman** - *Front* - [sharontrdjmn](https://github.com/orgs/Kinoba/people/sharontrdjmn)
* **Émilie Marjollet** - *Api* - [Emilie-thp](https://github.com/Emilie-thp)
* **François Loupias** - *Api & front* - [fralps](https://github.com/fralps)
* **Grégoire Willmann** - *Devops* - [GWillmann](https://github.com/orgs/Kinoba/people/GWillmann)

See also the list of [contributors](https://github.com/Kinoba/highday/graphs/contributors) who participated in this project.

## License

This project is licensed under a proprietary License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used

