## Pipelines developer for non-admin user

You can use `create_user.sh` script available in this directory
to enable developer console for a non-admin user.

Before running the script, ensure you have set `KUBECONFIG`
environment variable pointing to the Kubernetes configuration file.
```bash
    export KUBECONFIG=/path/to/kubeconfig
```
Also, ensure you have the latest `oc` command (minimum version: 4.1)
available in the `PATH` environment, so that the script can use it.

You can invoke the script like this:
```bash
   chmod +X create_user.sh  
  ./create_user.sh
```
The script does the following things:

1. Creates a non-admin user named `pipelinesdeveloper` with the password
   as `developer`.  The user gets `basic-user`
   cluster roles.


After the script completes execution, you can see the message to login
as the `pipelinesdeveloper` user:
```bash
    oc login -u pipelinesdeveloper -p developer
```
After logged in as the `pipelinesdeveloper` user

When you open the UI, you can now see the `pipelinesdeveloper` user
along with `kubeadmin` user.  Select `pipelinesdeveloper` user to
proceed with login.  Enter the password as `developer`.  Now you
should be able to view the Developer perspective.

## Developer console for non-admin users

You can use `pipelinesdeveloper.sh` script available in this directory
to enable developer console for a non-admin user.

Before running the script, ensure you have set `KUBECONFIG`
environment variable pointing to the Kubernetes configuration file.
```bash
    export KUBECONFIG=/path/to/kubeconfig
```
Also, ensure you have the latest `oc` command (minimum version: 4.1)
available in the `PATH` environment, so that the script can use it.

You can invoke the script like this:
```bash
    ./pipelinesdeveloper.sh
```
The script does the following things:

1. Installs the DevConsole operator.  You can see a message if it
   already exists.
2. Creates a non-admin user named `pipelinesdeveloper` with the password
   as `developer`.  The user gets `basic-user`
   cluster roles.


After the script completes execution, you can see the message to login
as the `pipelinesdeveloper` user:
```bash
    oc login -u pipelinesdeveloper -p developer
```
After logged in as the `pipelinesdeveloper` user, you can create a new
project and run `oc get csvs` in to see the installed operators.

When you open the UI, you can now see the `pipelinesdeveloper` user
along with `kubeadmin` user.  Select `pipelinesdeveloper` user to
proceed with login.  Enter the password as `developer`.  Now you
should be able to view the Developer perspective.

