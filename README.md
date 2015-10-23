# pcf-dotnet-environment-viewer

To push this app, you need to download the diego plugin and deploy to
an environment with .NET support.
[Instructions Here.](https://github.com/cloudfoundry-incubator/diego-cli-plugin)

The command to push.

Push the app with no-start:
```
cf push environment -s windows2012R2 -b binary_buildpack --no-start -p ./ViewEnvironment/
```

Enable diego:
```
cf enable-diego environment
```

Then Start:
```
cf start environment
```

Once your app is pushed, you can navigate to the route and you will
see all the VCAP variables.  Add ?all= to get all the system variables
too.

After your first push, you can then rely on the manifest to provide
the parameters and only assign the stack when you push changes:

```
cf push environment -s windows2012R2
```
