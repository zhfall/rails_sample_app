# Ruby on Rails Tutorial: sample application

This is the sample application for [*Ruby on Rails Tutorial: Learn Rails by Example*](http://railstutorial.org/) by [Michael Hartl](http://michaelhartl.com/).

This sample has been modified to run on Cloud Foundry. The `cf-autoconfig` gem was added to enable auto-configuration of database connections as described in the [Cloud Foundry documentation](http://docs.cloudfoundry.com/docs/using/services/ruby-service-bindings.html). The `pg` gem was also added to support connection to PostgreSQL database. 

## Running the application on Cloud Foundry

After installing in the 'cf' [command-line interface for Cloud Foundry](http://docs.cloudfoundry.com/docs/using/managing-apps/cf/),
targeting a Cloud Foundry instance, and logging in, the application can be pushed using these commands:

~~~
$ cf push 
Using manifest file manifest.yml

Creating rails_sample... OK

Creating route rails_sample_aa552.cfapps.io... OK
Binding rails_sample_aa552.cfapps.io to rails_sample... OK
Creating service rails_postgres... OK
Binding rails_postgres to rails_sample... OK
Uploading rails_sample... OK

Starting rails_sample... OK
...
Checking rails_sample...
Staging in progress...
...
  1/1 instances: 1 running
OK

$ cf app
Using manifest file manifest.yml

rails_sample: running
  usage: 256M × 1 instance
  urls: rails_sample-e3605.cfapps.io
  services: rails_postgres
~~~

The application will be pushed using settings in the provided `manifest.yml` file. The settings include some random 
characters in the host to make sure the URL for the app is unique in the Cloud Foundry environment. The output of the
`cf app` command shows the URL that was assigned. Using the provided URL in the `urls` field displayed, you can browse 
to the running application.
