# cf-dotnet-environment-viewer

To push this app, you need to download the diego plugin and deploy to
an environment with .NET support.
[Instructions Here.](https://github.com/cloudfoundry-incubator/diego-cli-plugin)

The command to push.

From within the repo directory, push the app with no-start:
```
cf push demoapp -s windows2012R2 -b binary_buildpack --no-start -p ./ViewEnvironment/
```

Enable diego:
```
cf enable-diego demoapp
```

Then Start:
```
cf start demoapp
```

Once your app is pushed, you can navigate to the route and you will
see all the VCAP variables.  Add ?all= to get all the system variables
too.

After your first push, you can then rely on the manifest to provide
the parameters and only assign the stack when you push changes:

```
cf push demoapp -s windows2012R2
```
