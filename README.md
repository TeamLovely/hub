## Lovely Hub

The Lovely Hub is a fork of [The 18F Hub](https://18f.gsa.gov/hub), a 
[Jekyll](http://jekyllrb.com/)-based documentation platform that aims to help
[18F](https://github.com/18F) and other development teams organize and easily
share their information, and to enable easy exploration of the connections
between team members, projects, and skill sets. It aims to serve as the go-to
place for all of a team's working information, whether that information is
integrated into the Hub directly or provided as links to other sources. It
also serves as a lightweight tool that other teams can experiment with and
deploy with a minimum of setup.

See the [18F blog post announcing the
Hub](https://18f.gsa.gov/2014/12/23/hub/) for more details about the vision
behind the Hub and the goals it aims to achieve.

The main 18F Hub Git repository is https://github.com/18F/hub and the primary
maintainer (for now) is [@mbland](https://github.com/mbland). The goal is to
eventually hand ownership over to the [Documentation Working
Group](https://18f.gsa.gov/hub/wg/documentation), or to the 18F team as a
whole.

Team Lovely's Hub repository is https://github.com/TeamLovely/hub, and the primary
maintainer (for now) is [@coderkat](https://github.com/coderkat). Please use 
our Hub [trello board](https://trello.com/b/zBFrfrLN/hub) to report any
issues or feature requests, or feel free to make changes and open a PR!

### Generating the site/hosting locally

It takes less than a minute to set up a local version of the Hub.

You will need [Ruby](https://www.ruby-lang.org) version 2.1.5 or greater. To
run your own local instance at `http://localhost:4000`:

```
$ git clone git@github.com:TeamLovely/hub.git
$ cd hub

# Lovely team members only: initialize private submodules
$ git submodule update --init 

$ ./go init
$ ./go serve
```

See the "Hub 101" docs either [in this repository](pages/101/), [served
locally](http://localhost:4000/101/), or on the [18F Public
Hub](https://18f.gsa.gov/hub/101/) for details and tips on how to set up and
work with the Hub development environment.

### Contributing

1.  Clone the repo (`git clone --recursive git@github.com:TeamLovely/hub.git`). The recursive clone ensures that you'll grab the contents of private submodules.
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

Feel free to ping [Kat](mailto:kat@livelovely.com) with any questions you
may have about our LovelyHub, especially if the current documentation should've addressed your
needs, but didn't.

### Deploying
Our S3 bucket lives at: http://hub.livelovely.com.s3-website-us-east-1.amazonaws.com/
To deploy your changes, make sure you have the latest changes to master locally and run:
    `./go init` and
    `./go serve`
    These will build out a local _site directory.
Then:

1. cd to the hub/_site directory
2. copy files to AWS:
    $ aws s3 cp . s3://hub.livelovely.com --recursive

### Public domain

This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright
> and related rights in the work worldwide are waived through the [CC0 1.0
> Universal public domain
> dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be released under the CC0 dedication.
> By submitting a pull request, you are agreeing to comply with this waiver of
> copyright interest.
