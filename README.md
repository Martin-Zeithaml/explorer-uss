# explorer-uss

Requires access to npm registry with orion-editor-component
https://gizaartifactory.jfrog.io/gizaartifactory/webapp/#/artifacts/browse/tree/General/npm-release

**Pre reqs**
```
npm install
```
Update npm.rc or run 
```
npm config set registry https://gizaartifactory.jfrog.io/gizaartifactory/api/npm/npm-release/
npm login
```

**Development:**
```
npm run dev 
GOTO: localhost:8080
```
**Production:**
```
npm run prod
```

### Prepare PAX Packaging Workspace

```
./scripts/prepare-pax-workspace.sh
```

## Start With explorer-ui-server

After preparing PAX workspace, you can serve the explorer UI with explorer-ui-server:

```
node pax-workspace/ascii/server/src/index.js --config pax-workspace/ascii/server/configs/config.json
```
