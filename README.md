# .NET Sample App

Push the app with no-start:
```
cf push environment -s windows2012R2 -b hwc_buildpack --no-start -p ./ViewEnvironment/
```

If Diego is enabled by default on your CF deployment, you can omit the `--no-start` flag.

If it's not, or if you're not sure, you'll need to install the [Diego Enabler](https://github.com/cloudfoundry-incubator/diego-enabler) CLI plugin:
```
cf add-plugin-repo CF-Community http://plugins.cloudfoundry.org/
cf install-plugin Diego-Enabler -r CF-Community
```

Enable diego and start your app:
```
cf enable-diego environment
cf start environment
```

Once your app is pushed, you can navigate to the app's URL and you will
see all the VCAP variables.  Add ?all= to get all the system variables
too.

After your first push, you can simply push your updates without any additional command line arguments:

```
cf push environment
```
