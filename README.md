# explorer-uss

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=zowe_explorer-uss&metric=alert_status)](https://sonarcloud.io/dashboard?id=zowe_explorer-uss)

The issues for the USS explorer are tracked under the Zowe Zlux repository, https://github.com/zowe/zlux and tagged accordingly with the 'explorer-uss' label. Open issues tagged with 'explorer-uss' can be found [here](https://github.com/zowe/zlux/issues?q=is%3Aissue+is%3Aopen+label%3Aexplorer-uss).

## Build 

### Install Dependencies

```
npm install
```

Update npm.rc or run 

```
npm config set registry https://zowe.jfrog.io/zowe/api/npm/npm-release/
npm login
```

### Build for Development

```
npm run dev 
```

Then you can visit http://localhost:8080 to test.

### Build for Production

```
npm run prod
```

### Prepare PAX Packaging Workspace

```
./.pax/prepare-workspace.sh
```

## Start With explorer-ui-server

After preparing PAX workspace, you can serve the explorer UI with explorer-ui-server:

```
node .pax/ascii/server/src/index.js --config .pax/ascii/server/configs/config.json
```

## Run SonarQube Code Analysis

Install [SonarQube Scanner](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner).

If you are using Mac, try install with [HomeBrew sonar-scanner formula](https://formulae.brew.sh/formula/sonar-scanner), then update the configuration of SonarQube server at `/usr/local/Cellar/sonar-scanner/<version>/libexec/conf/sonar-scanner.properties`.

Example scanner configurations:

```
sonar.host.url=https://jayne.zowe.org:9000
sonar.login=<hash>
```

Then you can run `sonar-scanner` to start code analysis.

Build pipeline has embedded the SonarQube code analysis stage.
