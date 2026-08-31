Update Steps

- `./gradlew clean assemble`
- Update `gradle.properties`. Set `production=true`. Set `disableUiModule=true`.
- `./gradlew clean`.
- Update `versions.props` as appropriate for the correct remediation versions
- `./gradlew --write-locks`
- `./gradlew updateLicenses`
- Update `de.thetaphi.forbiddenapis` version in `/build.gradle` if necessary to cover newer signatures for third party dep updates
- `./gradlew check` to run the test suite (optional. expensive.)
- `./gradlew clean assemble`
- `./gradlew dockerWolfiBuildxBakeAndTagMulti -Psolr.docker.dist=slim -Psolr.docker.imageName=repository.broadleafcommerce.com:5001/broadleaf/solr:9.10.2-wolfi-7` (Increment the `r1` to a higher value if only changing java or os deps without changing app, jre, or os versions).