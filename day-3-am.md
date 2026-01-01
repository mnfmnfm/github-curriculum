# Day 3 Morning Session

## Agenda

* Completing the Software Development Lifecycle
    * Build & Test
    * Deployment
    * Monitoring

## Build & Test

At most companies, you'll have automated build processes that run either with each merge that you do to the main branch, or at predefined time intervals, like once per day or once per week. This process is called Continuous Integration, or CI. (It's also sometimes combined with Continuous Deployment, CD, which we'll talk about next!)

A CI system will usually hook in with GitHub (or whatever version control system you're using) to automatically pull the latest code changes into its build system, which generally runs in the cloud. When you set up a CI system, you specify which repo/branch(es) to use, and what commands the CI system will use to build the application - usually, installing dependencies and running any compiling or other steps to turn your code into something that's ready to run.

CI systems will then usually run tests on your code, including integration tests - that's where the name CI comes from. The idea is that, every time new code is included in your team's repo, it is immediately tested to ensure that it builds and runs correctly - and if anything goes wrong along the way, the entire team is notified so that development can pause while the problem is identified and fixed.

Another part of this process (again depending on the company) is that these automated builds might be sent to Quality Assurance (QA) for manual, human testing as well as automated testing. Just one more way of testing our applications to make sure they're still working correctly at this stage of the process.

## Deployment

Deployment is the process of making the new code you've written available to users/the public. The process of deployment is very different depending on the exact type of application you're developing:

* Web application: deployment is about updating the version of code available on your servers, so that the next users who connect to your website get the new version of the site.
* Mobile applications: deployment involves submitting your built application to the App Store/Play Store, where it will be reviewed, and eventually be made available for users to update the app on their devices.
* Installed/desktop applications: lots of options, but most commonly, deployment will look like making the newest version of your code available to be installed in the same way you initially made it available, and maybe prompting users within your application that a new version is available.

We'll look at an example of deploying a web application together.

## Monitoring

Once your application is available to users, as a developer, you'll generally move on to working on the next set of features, going back through the software development lifecycle again from planning onwards. But, there's one other critical step - ensuring that your deployed application continues to function correctly into the future.

Monitoring is the process by which you make this happen. The easy-but-bad form of monitoring is to check the logs manually yourself and gain insight from those logs - ideally, you want to set up your application so that you will be notified automatically if something is going wrong in the running of your application.

As an example of what setting that up looks like, you can check out [OTEL](https://opentelemetry.io/docs/languages/) or Open Telemetry, which is a vendor-neutral set of instrumentation libraries that can plug into your project to automatically report metrics. At most companies, that'll be hooked up to a backend like DataDog, New Relic, or Splunk, which are examples of platforms that allow you to set up alerts based on the metrics that your application reports.