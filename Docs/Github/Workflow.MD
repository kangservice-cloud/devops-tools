
Checking the History of the Deployment Rollout


The output gives us a Revision column and the Change-Cause column. Whenever there’s a new change to the same Deployment resource, the controller increments the Revision value by one.

Besides that, the Change-Cause column is a column that displays the kubernetes.io/change-cause annotation on our application. The kubernetes.io/change-cause annotation is a way for us to document the changes we apply to the Deployment resource.


Rolling Back a Deployment Rollout

One advantage of having historical records of all the deployment rollouts is that we can roll back our Deployment resources to any previous revisions


 Pausing and Resuming a Deployment Rollout

 The Deployment controller always monitors and triggers a rollout whenever it detects any specification drift between the running pods and the backing definition. In other words, applying an update to the Deployment resource causes the controller to instantly perform a rolling update to the pods.

To prevent the controller from automatically rolling out the updates, we can issue the kubectl rollout pause command on our Deployment resource. By marking our Deployment resource as paused, the controller won’t automatically roll out the changes on the Deployment level to the pods.