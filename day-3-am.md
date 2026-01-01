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