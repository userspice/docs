<h1 align="center">UserSpice Documentation</h1>
<p align="center">
  <a href="https://github.com/userspice/docs/actions?query=workflow%3ABuild+branch%3Amain"><img src="https://github.com/userspice/docs/workflows/Build/badge.svg?branch=main" alt="Build Status"></a>
</p>

Resources & Links
--------------------
* [Documentation](https://userspice.github.io/docs/)
* [Bug Reports](https://userspice.com/bugs)
* [Discord & Support](https://discord.gg/j25FeHu)

Contributions Guidelines & Info
--------------------
Our documentation improves when our community comes together to fill in the gaps. As our developers focus their time on the core code of UserSpice, it is important to have some backup from incredible people, like yourself, in ensuring we keep this data up to date. If you wish to contribute, which we would appreciate greatly, please follow a few guidelines:

* If you wish to have a section added, please open an issue prior to completing a pull request, we may opt for you to follow a different route
* You will submit new documentation in the form of a pull request as raw files, do not submit the built files in your pull request
* Follow the format included in [source/includes/_sample.md](source/includes/_sample.md)
* Additional tables and data can be included if they are useful to the documentation
* No data is to be added to [source/index.html.md](source/index.html.md)
* You are expected to follow our basic [Code of Conduct](CODE_OF_CONDUCT.md)

Running the Documentation Locally
--------------------
UserSpice uses [Slate](https://github.com/slatedocs/slate) for a documentation template

To run the documentation locally, follow their [Native Guideline](https://github.com/slatedocs/slate/wiki/Using-Slate-Natively)

If you already have Ruby and NodeJS installed, you will run the following commands in the directory you cloned your forked repo to:

```
gem install bundler
bundle install
bundle exec middleman server
````

Have questions?
--------------------
Please reach out in [Discord](https://discord.gg/j25FeHu)
