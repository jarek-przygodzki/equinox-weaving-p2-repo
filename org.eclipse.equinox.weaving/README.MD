# p2 repository for Equinox Weaving


## Follow these steps if you want to release a new version

* Manually change the /repository/features/feature.xml file. Replace 1.0.0.qualifier by 1.0.0
* Set project version to release version with the Tycho Versions plugin
```
mvn org.eclipse.tycho:tycho-versions-plugin:set-version -DnewVersion=1.0.0
```
* Commit the changed files
```
git commit -a -m "Prepare for release"
```
*  Create release
```
mvn clean install
```
* Create a release tag with pattern v<version>
```
git tag v1.0.0
```
*  Increment to next development version
```
mvn org.eclipse.tycho:tycho-versions-plugin:set-version -DnewVersion=1.1.0-SNAPSHOT
```
* Manually change the /repository/features/feature.xml file. Replace 1.0.0 by 1.1.0.qualifier
* Commit the changes
```
git commit -a -m "Increment to next development version"
```
* Push the changes including the tag to the server
git --tags push origin master
* Share p2 repository
