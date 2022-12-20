# NPM Commands

- Get npm config list
```
npm config list
```

- Set @sap:registry
```
npm config set @sap:registry="https://registry.npmjs.org/"
```

- Set BAS registry
```
npm config set registry "http://nginx-redirector.repo-cache.svc.cluster.local/repository/appstudio-npm-group/"
```

- Install node module defined in package.json
```
npm install
```

- Install node modules excluding devDependencies defined in package.json
```
npm install --production
```

```
npm install --package-lock-only
```

- Install sqlite3
```
npm install sqlite3 -D
```

- Install UI5 cli - [https://sap.github.io/ui5-tooling/pages/CLI/](https://sap.github.io/ui5-tooling/pages/CLI/)
```
npm install --global @ui5/cli
```

- Install CDS - [https://cap.cloud.sap/docs/get-started/in-a-nutshell](https://cap.cloud.sap/docs/get-started/in-a-nutshell)
```
npm install --global @sap/cds-dk
```

- Install yeoman - [https://yeoman.io/](https://yeoman.io/)
```
npm install --global yo
```

- Install the MTA build tool mbt - [https://sap.github.io/cloud-mta-build-tool/](https://sap.github.io/cloud-mta-build-tool/)
```
npm install --global mbt
```

- Install SAPUI5 tooling - [https://www.npmjs.com/package/@sap/ux-ui5-tooling](https://www.npmjs.com/package/@sap/ux-ui5-tooling)
```
npm install --global @sap/ux-ui5-tooling
```

- Install SAP Fiori application generator - [https://www.npmjs.com/package/@sap/generator-fiori](https://www.npmjs.com/package/@sap/generator-fiori)
```
npm install --global @sap/generator-fiori
```

- Install MTA - [https://www.npmjs.com/package/mta](https://www.npmjs.com/package/mta)
```
npm install --global mta
```