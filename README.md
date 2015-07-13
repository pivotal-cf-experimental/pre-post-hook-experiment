# Usage

```
cd nodejs-buildpack
BUNDLE_GEMFILE=cf.Gemfile bundle install
BUNDLE_GEMFILE=cf.Gemfile bundle exec buildpack-packager uncached
cf create-buildpack nodejs-test-buildpack nodejs_buildpack-v1.4.1.zip 1

cd ../sample-nodejs
cf push sample-nodejs

# output from staging log

Starting app sample-nodejs in org pivotal / space integration as admin...
-----> Downloaded app package (4.0K)
-----> Downloaded app buildpack cache (4.0K)
pre-hook called!
-------> Buildpack version 1.4.1
-----> Creating runtime environment
       NPM_CONFIG_LOGLEVEL=error
       NPM_CONFIG_PRODUCTION=true
       NODE_MODULES_CACHE=true
-----> Installing binaries
       engines.node (package.json):  unspecified
       engines.npm (package.json):   unspecified (use default)
       Resolving node version (latest stable) via semver.io...
       Downloading and installing node 0.12.7...
       Using default npm version: 2.11.3
-----> Restoring cache
       Loading 1 from cacheDirectories (default):
       - node_modules (not cached - skipping)
-----> Building dependencies
       Pruning any extraneous modules
       Installing node modules (package.json)
-----> Caching build
       Clearing previous node cache
       Saving 1 cacheDirectories (default):
       - node_modules (nothing to cache)
-----> Build succeeded!
post-hook called
       └── (empty)

-----> Uploading droplet (9.7M)

1 of 1 instances running

App started


OK

```
