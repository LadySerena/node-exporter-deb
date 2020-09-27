# node-exporter-deb

This gradle script will create a debian package for [node_exporter](https://github.com/prometheus/node_exporter).

## Releasing

to create a new package update the `gradle.properties` and change the `node_exporter_version` variable to point to the 
new version of node_exporter you wish to download and package. Test the variable change by running `./gradlew build` so 
that you can verify that url and version is correct. If the build works upload the changed files to github and then 
create a new git tag targeting the new commit (`git tag Major.Minor.Patch-Release`). The `Major`, `Minor`, `Patch` 
versions should correspond to the node_exporter version that you downloaded. The `Release` variable should be a unique 
number within your Google Cloud Storage bucket. This creates a unique package to allow different configurations of 
node_exporter packages existing in the same bucket.