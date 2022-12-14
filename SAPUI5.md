# SAPUI5

## Structuring: Components and Descriptor

- SAPUI5 provides Components as independent and reusable parts of UI5 applications. They facilitate the encapsulation of closely related parts of an application, thus enabling developers to structure and maintain their applications more easily.
- Components are independent and reusable parts used in SAPUI5 applications.
- SAPUI5 provides the following two types of components:
    - Faceless components (class: sap.ui.core.Component)
        - Faceless components do not have a user interface and are used for coding where no UI elements are needed. Please consider that a faceless component can't be added to a ComponentContainer.
    - UI components (class: sap.ui.core.UIComponent)
        - UI components extend components and add rendering functionality to the component. They represent a screen area or element on the user interface, for example, a button or a shell, along with the respective settings and metadata. sap.ui.core.UIComponent extends sap.ui.core.Component and adds rendering functionality to the component.
- The sap.ui.core.Component class is the base class and provides the metadata for both types of components. To extend the functionality, components can inherit from their base class or from another component.

**Descriptor for Applications, Components, and Libraries (manifest.json)**

- In general, the app descriptor describes the behavior of an app through attributes. It doesn't directly influence that behavior itself for the most part. 
- The data of the app descriptor is stored in JSON format in the manifest.json file. The developer creates the file with attributes in different namespaces. It contains, for example, the app ID, the version, the data sources used, along with the required components and libraries. The existence of the manifest.json file must be declared in the component metadata, which is then delivered as part of the application archive. After delivery, the file is read-only.

Sample manifest.json
```json
{
    "_version": "1.48.0",
 
    "start_url": "index.html",
 
    "sap.app": {
        "id": "sap.fiori.appName",
        "type": "application",
        "i18n": "",
        "applicationVersion": {
            "version": "1.2.2"
        },
        "embeds": ["mycomponent1", "subpath/mycomponent2"],
        "embeddedBy": "../../",
        "title": "{{title}}",
        "subTitle": "{{subtitle}}",
        "shortTitle": "{{shorttitle}}",
        "description": "{{description}}",
        "info": "{{info}}",
        "tags": {
            "keywords": ["{{keyWord1}}", "{{keyWord2}}"],
            "technicalAttributes": ["ATTRIBUTE1", "ATTRIBUTE2"]
        },
        "ach": "PA-FIO",
        "dataSources": {
            "equipment": {
                "uri": "/sap/opu/odata/snce/po_s_srv;v=2/",
                "type": "OData",
                "settings": {
                    "odataVersion": "2.0",
                    "annotations": ["equipmentanno"],
                    "localUri": "model/metadata.xml",
                    "maxAge": 360
                }
            },
            "equipmentanno": {
                "uri": "/sap/bc/bsp/sap/nscbn_anf_eam/bscbn_equipment_srv.anno.xml",
                "type": "ODataAnnotation",
                "settings": {
                    "localUri": "model/annotations.xml"
                }
            },
            "cdsService": {
                "uri": "/sap/bc/ina/ina1/sap/example_cds",
                "type": "INA",
                "settings": {
                    "localUri": "localService/metadata.xml",
                    "objects": {
                        "assets": {
                            "objectName": "SAPFinAssets",
                            "objectType": "cdsprojectionview",
                            "packageName": "package",
                            "schemaName":  "schema"
                        },
                        "liabilities": {
                            "objectName": "SAPFinLiabilities",
                            "objectType": "cdsprojectionview"  
                        }
                    }
                }
            }
        },
        "cdsViews": [
            "VIEW1", "VIEW2"
        ],
        "resources": "resources.json",
        "offline": true,
        "sourceTemplate": {
            "id": "sap.ui.ui5-template-plugin.1worklist",
            "version": "1.0.0",
            "toolsId": "C12345678"
        },
        "destination": {
            "name": "SAP_ERP_FIN"
        },
        "openSourceComponents": [{
            "name": "D3.js",
            "packagedWithMySelf": false
        }],
        "crossNavigation": {
            "scopes": {
                "sapSite": {
                    "value": "123"
                }
            },
            "inbounds": {
                "contactCreate": {
                    "semanticObject": "Contact",
                    "action": "create",
                    "icon": "sap-icon://add-contact",
                    "title": "{{title}}",
                    "subTitle": "{{subtitle}}",
                    "shortTitle": "{{shorttitle}}",
                    "info": "{{info}}",
                    "displayMode": "HeaderMode",
                    "indicatorDataSource": {
                        "dataSource": "equipment",
                        "path": "TaskListSet/$count",
                        "refresh": 5
                    },
                    "deviceTypes": {
                        "desktop": true,
                        "tablet": true,
                        "phone": false
                    },
                    "signature": {
                        "parameters": {
                            "id": {
                                "required": true
                            },
                            "ContactName": {
                                "defaultValue": {
                                    "value": "anonymous"
                                },
                                "required": false,
                                "renameTo": "NAME2"
                            },
                            "Gender": {
                                "filter": {
                                    "value": "(male)|(female)",
                                    "format": "regexp"
                                },
                                "required": true,
                                "renameTo": "SEX",
                                "launcherValue": {
                                    "value": "female",
                                    "format": "plain"
                                }
                            }
                        },
                        "additionalParameters": "ignored"
                    }
                },
                "contactDisplay": {
                    "semanticObject": "Contact",
                    "action": "display",
                    "signature": {
                        "parameters": {
                            "id": {
                                "required": true
                            },
                            "Language": {
                                "filter": {
                                    "value": "EN"
                                },
                                "required": true
                            },
                            "SomeValue": {
                                "filter": {
                                    "value": "4711"
                                }
                            },
                            "GLAccount": {
                                "defaultValue": {
                                    "value": "1000"
                                },
                                "filter": {
                                    "value": "(1000)|(2000)",
                                    "format": "regexp"
                                }
                            }
                        },
                        "additionalParameters": "allowed"
                    }
                },
                "contactDisplayAlt": {
                    "semanticObject": "Contact",
                    "action": "display",
                    "hideLauncher": true,
                    "signature": {
                        "parameters": {
                            "GLAccount": {
                                "defaultValue": {
                                    "value": "UserDefault.GLAccount",
                                    "format": "reference"
                                },
                                "filter": {
                                    "value": "\\d+",
                                    "format": "regexp"
                                },
                                "required": true
                            },
                            "SomePar": {
                                "filter": {
                                    "value": "UserDefault.CostCenter",
                                    "format": "reference"
                                },
                                "required": true
                            }
                        },
                        "additionalParameters": "allowed"
                    }
                }
            },
            "outbounds": {
                "addressDisplay": {
                    "semanticObject": "Address",
                    "action": "display",
                    "additionalParameters": "ignored",
                    "parameters": {
                        "CompanyName": {
                            "value": {
                                "value": "companyName",
                                "format": "plain"
                            },
                            "required": true
                        }
                    }
                },
                "companyDisplay": {
                    "semanticObject": "Company",
                    "action": "display",
                    "additionalParameters": "allowed",
                    "parameters": {
                        "CompanyName": {
                            "value": {
                                "value": "companyName",
                                "format": "plain"
                            },
                            "required": true
                        }
                    }
                }
        }
        }
    },
 
    "sap.ui": {
        "technology": "UI5",
        "icons": {
            "icon": "sap-icon://add-contact",
            "favIcon": "icon/F1373_Approve_Purchase_Orders.ico",
            "phone": "icon/launchicon/57_iPhone_Desktop_Launch.png",
            "phone@2": "icon/launchicon/114_iPhone-Retina_Web_Clip.png",
            "tablet": "icon/launchicon/72_iPad_Desktop_Launch.png",
            "tablet@2": "icon/launchicon/144_iPad_Retina_Web_Clip.png"
        },
        "deviceTypes": {
            "desktop": true,
            "tablet": true,
            "phone": false
        },
        "fullWidth": true
    },
 
    "sap.ui5": {
        "resources": {
            "css": [{
                "uri": "component.css",
                "id": "componentcss"
            }]
        },
        "dependencies": {
            "minUI5Version": "1.108.0",
            "libs": {
                "sap.m": {
                    "minVersion": "1.34.0"
                },
                "sap.ui.commons": {
                    "minVersion": "1.34.0",
                    "lazy": true
                }
            },
            "components": {
                "sap.ui.app.other": {
                    "minVersion": "1.1.0",
                    "lazy": true
                }
            }
        },
        "componentUsages": {
            "myusage": {
                "name": "my.used",
                "lazy": false,
                "settings": {},
                "componentData": {}
            }
        },
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "uri": "i18n/i18n.properties",
                "settings": {
                    "enhanceWith": [{
                        "bundleUrl": "i18n/i18n.properties",
                        "bundleUrlRelativeTo": "manifest"
                    }]
                }
            },
            "equipment": {
                "preload": true,
                "dataSource": "equipment",
                "settings": {}
            }
        },
        "rootView": {
            "viewName": "sap.ui.test.view.Main",
            "id" : "rootView",
            "async": true,
            "type": "XML"
        },
        "handleValidation": true,
        "config": {
 
        },
        "routing": {
 
        },
        "extends": {
            "component": "sap.fiori.otherApp",
            "minVersion": "0.8.15",
            "extensions": {}
        },
        "contentDensities": {
            "compact": true,
            "cozy": false
        },
        "resourceRoots": {
            ".myname": "./myname"
        },
        "componentName": "sap.fiori.appName",
        "autoPrefixId": true,
        "appVariantId": "hcm.leaverequest.oil",
        "appVariantIdHierarchy": [
            {"layer": "VENDOR", "appVariantId": "abc", "version": "1.0.0"}
        ],
        "services": {
            "myLocalServiceAlias": {
                "factoryName": "sap.ushell.LaunchPadService",
                "optional": true
            }
        },
        "library": {
            "i18n": true
        },
        "flexEnabled": true,
        "flexExtensionPointEnabled": true,
        "commands": {
            "Save": {
                "shortcut": "Ctrl+S"
            }
        }
	    },
 
    "sap.platform.abap": {
        "uri": "/sap/bc/ui5_ui5/sap/appName",
        "uriNwbc": ""
    },
 
    "sap.platform.hcp": {
        "uri": "",
        "uriNwbc": "",
        "providerAccount": "fiori",
        "appName": "sapfioriappName",
        "appVersion": "1.0.0",
        "multiVersionApp": true
    },
 
    "sap.fiori": {
        "registrationIds": [
            "F1234"
        ],
        "archeType": "transactional",
        "abstract": false
    },
 
    "sap.mobile": {},
    "sap.flp": {},
    "sap.ui.generic.app": {},
    "sap.ovp": {},
    "sap.ui.smartbusiness.app": {},
    "sap.wda": {},
    "sap.gui": {},
    "sap.cloud.portal": {},
    "sap.apf": {},
    "sap.platform.cf": {},
    "sap.copilot": {},
    "sap.map": {},
    "sap.url": {},
    "sap.platform.sfsf": {},
    "sap.wcf": {},
    "sap.cloud": {},
    "sap.integration": {},
    "sap.platform.mobilecards": {},
    "sap.artifact": {},
    "sap.package": {},
    "sap.insights": {},
    "sap.fe": {},
    "sap.card": {}
}
```


Sample manifest.json
```json
{
    "_version": "1.35.0",
	
	"start_url": "<startUrl>",
	
    "sap.app": {
        "id": "<id>",
        "type": "application",
        "i18n": "<i18nPathRelativeToManifest>",
        "applicationVersion": {
            "version": "<version>"
        },
        "title": "{{<title>}}",
        "tags": {
            "keywords": [
                "{{<keyword1>}}", "{{<keyword2>}}"
            ]
        },
        "dataSources": {
            "<dataSourceAlias>": {
                "uri": "<uri>",
                "settings": {
                    "localUri": "<localUri>"
                }
            }
        }
    },
    "sap.ui": {
        "icons": {
            "icon": "<icon>",
            "favIcon": "<favIcon>",
            "phone": "<phone>",
            "phone@2": "<phone@2>",
            "tablet": "<tablet>",
            "tablet@2": "<tablet@2>"
        },
        "deviceTypes": {
            "desktop": true,
            "tablet": true,
            "phone": true
        },
        "supportedThemes": [
            "sap_hcb",
            "sap_belize"
        ]
    },
    "sap.ui5": {
        "resources": {
            "css": [
                {
                    "uri": "<uri>",
                    "id": "<id>"
                }
            ]
        },
        "dependencies": {
            "minUI5Version": "<minUI5Version>",
            "libs": {
                "<ui5lib1>": {                   
                    "minVersion": "<minVersion1>"
                },
                "<ui5lib2>": {                   
                    "minVersion": "<minVersion2>"
                }
            },
            "components": {
                "<ui5component1>": {
                    "minVersion": "<minComp1Version>"
                }
            }
        },
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "uri": "<uriRelativeToManifest>"
            },
            "": {
                "dataSource": "<dataSourceAlias>",
                "settings": {}
            }
        },
        "rootView": "<rootView>",
        "handleValidation": <true|false>,
        "config": {
          
        },
        "routing": {
          
        },
        "extends": {
            "component" : "<extendedComponentId>",
			"minVersion": "<minComp1Version>",
			"extensions": {}
        }
        "contentDensities": {
            "compact": <true|false>,
            "cozy": <true|false>
        }
    },

    "sap.platform.abap": {
        "uri": "<uri>"
    },
    "sap.platform.hcp": {
        "uri": "<uri>"
    }
}

```

## Routing and Navigation

- SAPUI5 offers hash-based navigation, which allows you to build single-page apps where the navigation is done by changing the hash. In this way the browser does not have to reload the page; instead there is a callback to which the app and especially the affected view can react. A hash string is parsed and matched against patterns which will then inform the handlers.

**Routing Patterns**

Whenever a hash is added to a URL, the router checks whether there is a route with a matching pattern. The first matching route is taken and the corresponding target view is called. The data provided with the hash are passed on to the target.

- Hard-coded pattern:
    - The pattern matches the hash exactly.
- Route with mandatory parameter:
    - You can define mandatory parameters for the pattern by placing the parameter in curly brackets ({parameter ID}).
- Route with optional parameter:
    - You can define optional parameters for the pattern by placing the parameter between colons (:parameter ID:).
- Route with query parameter:
    - The query parameter allows you to pass on queries with any parameter. A query parameter starts with ?, and you can either define it as mandatory (product/{?query}) or optional (product/:?query:). The matched value will be converted into an object saved with the parameter name as the key when passed to the event handler.
- "rest as string" parameter:
    - A parameter that ends with an asterisk (*) is called a "rest as string" parameter. Such a parameter matches as much as possible. It can be combined with the syntax of mandatory or optional parameters.