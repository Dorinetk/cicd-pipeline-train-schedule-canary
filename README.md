# cicd-pipeline-train-schedule-canary

This is a simple train schedule app written using nodejs. It is intended to be used as a sample application for a series of hands-on learning activities.

## Running the app

You need a Java JDK 7 or later to run the build. You can run the build like this:

    ./gradlew build

You can run the app with:

    ./gradlew npm_start

Once it is running, you can access it in a browser at http://localhost:8080

## Notes

<p>This is a sample canary deployement of an app to fix a bug after it has been deployed to prod.
Deploy to pro using train-schedule-kube.yml before adding train-schedule-kube-canary.yml for the canary version.</p>

Edit the initial Jenkinsfile to add stage CanaryDeploy, env CANARY_REPLICAS & canary deployment yml file in deployProduction stage.

Check running pods using <em>kubectl get pods -w</em>. Use <em>cat ~/.kube/config</em> to get content of kubeconfig credentials for Jenkins set-up.

