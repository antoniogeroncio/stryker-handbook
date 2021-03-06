# Getting started

Stryker4s is a mutation testing framework for Scala. It allows you to test your tests by temporarily inserting bugs.

Currently, the only way to get started with Stryker4s is to use the [command test-runner](https://github.com/stryker-mutator/stryker4s/blob/master/docs/CONFIGURATION.md#test-runner).
 The `command` test-runner is build tool agnostic and can be used by every build tool that supports Scala. For example, the `sbt test` and `mvn test` both run the specified unit tests in your codebase. This will put you as a user in full control! 

 ## Quickstart

The command test-runner is designed to be able to work with any build tool that supports Scala. This is done by directly executing a command on a terminal.  
To get started you need to clone the [Stryker4s repository](https://github.com/stryker-mutator/stryker4s). 

## Configuration

After cloning the repository, create a `stryker4s.conf` file in the root of the Stryker4s repository. 
The configuration below shows all the default options Stryker4s uses. You can edit ones you want to change, or remove the ones that look good for your project. The default configuration will start a command test-runner for sbt. 
You will have to edit the `base-dir` to match the codebase you want to mutate. 
Also, make sure the `test-runner` is configured with the commands you need to run your unit tests.    
```conf
stryker4s {
    log-level=INFO
    mutate=[
        "**/main/scala/**/*.scala"
    ]
    reporters=[
        console
    ]
    test-runner {
        args=test
        command=sbt
        type=commandrunner
    }
}
```
