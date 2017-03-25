# api documentation for  [supervisor (v0.12.0)](https://github.com/petruisfan/node-supervisor/)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-supervisor.svg)](https://travis-ci.org/npmdoc/node-npmdoc-supervisor)
#### A supervisor program for running nodejs programs

[![NPM](https://nodei.co/npm/supervisor.png?downloads=true)](https://www.npmjs.com/package/supervisor)

[![apidoc](https://npmdoc.github.io/node-npmdoc-supervisor/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-supervisor_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-supervisor/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-supervisor/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Isaac Z. Schlueter",
        "email": "i@izs.me"
    },
    "bin": {
        "node-supervisor": "lib/cli-wrapper.js",
        "supervisor": "lib/cli-wrapper.js"
    },
    "bugs": {
        "url": "https://github.com/petruisfan/node-supervisor/issues"
    },
    "contributors": [
        {
            "name": "Todd Branchflower",
            "email": "toddbran@stanford.edu"
        },
        {
            "name": "Giannis Dzegoutanis",
            "email": "erasmospunk@gmail.com"
        },
        {
            "name": "Brian Ehmann",
            "email": "behmann@gmail.com"
        },
        {
            "name": "Corey Jewett",
            "email": "cj@syntheticplayground.com"
        },
        {
            "name": "Taka Kojima",
            "email": "taka.kojima@ff0000.com"
        },
        {
            "name": "Aneil Mallavarapu",
            "email": "aneil@blipboard.com"
        },
        {
            "name": "Doug McCall",
            "email": "dhm116@psu.edu"
        },
        {
            "name": "Mathieu M-Gosselin",
            "email": "mathieumg@gmail.com"
        },
        {
            "name": "David Murdoch",
            "email": "hello@davidmurdoch.com"
        },
        {
            "name": "mx1700",
            "email": "mx1700@gmail.com"
        },
        {
            "name": "Michiel ter Reehorst",
            "email": "jm.ter.reehorst@jamiter.com"
        },
        {
            "name": "Jonathan 'Wolf' Rentzsch",
            "email": "jwr.git@redshed.net"
        },
        {
            "name": "John Roberts",
            "email": "jroberts@logitech.com"
        },
        {
            "name": "Scott Sanders",
            "email": "scott@stonecobra.com"
        },
        {
            "name": "Thomas Schaaf",
            "email": "schaaf@komola.de"
        },
        {
            "name": "Fernando H. Silva",
            "email": "ferhensil@gmail.com"
        },
        {
            "name": "Kei Son",
            "email": "heyacct@gmail.com"
        },
        {
            "name": "David Taylor",
            "email": "david@zensatellite.com"
        },
        {
            "name": "Antonio Touriño",
            "email": "atourino@gmail.com"
        },
        {
            "name": "Oliver Wong",
            "email": "oliver@owiber.com"
        },
        {
            "name": "Di Wu",
            "email": "dw323@cornell.edu"
        },
        {
            "name": "Jesse Yang",
            "email": "jyyjcc@gmail.com"
        },
        {
            "name": "Ian Young",
            "email": "ian.greenleaf@gmail.com"
        },
        {
            "name": "jazzzz",
            "email": "jazzzz@gmail.com"
        },
        {
            "name": "philpill",
            "email": "github@philpill.net"
        },
        {
            "name": "rma4ok",
            "email": "rma4ok@gmail.com"
        },
        {
            "name": "Petru Isfan",
            "email": "petru.isfan@gmail.com"
        }
    ],
    "dependencies": {},
    "description": "A supervisor program for running nodejs programs",
    "devDependencies": {
        "nodeunit": "~0.9.0"
    },
    "directories": {},
    "dist": {
        "shasum": "de7e6337015b291851c10f3538c4a7f04917ecc1",
        "tarball": "https://registry.npmjs.org/supervisor/-/supervisor-0.12.0.tgz"
    },
    "engines": {
        "node": ">=0.6.0"
    },
    "gitHead": "85d92db02a651d8523f1a787a5c474668afb97b3",
    "homepage": "https://github.com/petruisfan/node-supervisor/",
    "license": "MIT",
    "main": "lib/supervisor.js",
    "maintainers": [
        {
            "name": "iangreenleaf",
            "email": "ian.greenleaf@gmail.com"
        },
        {
            "name": "isaacs",
            "email": "isaacs@npmjs.com"
        },
        {
            "name": "petruisfan",
            "email": "petru.isfan@gmail.com"
        }
    ],
    "name": "supervisor",
    "optionalDependencies": {},
    "preferGlobal": true,
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/petruisfan/node-supervisor.git"
    },
    "scripts": {
        "test": "./node_modules/nodeunit/bin/nodeunit test/*.test.js"
    },
    "version": "0.12.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module supervisor](#apidoc.module.supervisor)
1.  [function <span class="apidocSignatureSpan">supervisor.</span>run (args)](#apidoc.element.supervisor.run)



# <a name="apidoc.module.supervisor"></a>[module supervisor](#apidoc.module.supervisor)

#### <a name="apidoc.element.supervisor.run"></a>[function <span class="apidocSignatureSpan">supervisor.</span>run (args)](#apidoc.element.supervisor.run)
- description and source-code
```javascript
function run(args) {
    var arg, next, watch, ignore, pidFilePath, program, extensions, executor, poll_interval, debugFlag, debugBrkFlag, debugBrkFlagArg
, harmony, inspect;
    while (arg = args.shift()) {
        if (arg === "--help" || arg === "-h" || arg === "-?") {
            return help();
        } else if (arg === "--quiet" || arg === "-q") {
            debug = false;
            log = function(){};
        } else if (arg === "--harmony") {
            harmony = true;
        } else if (arg === "--inspect") {
            inspect = true;
        } else if (arg === "--harmony_default_parameters") {
            harmony_default_parameters = true;
        } else if (arg === "--harmony_destructuring") {
            harmony_destructuring = true;
        } else if (arg === "--verbose" || arg === "-V") {
            verbose = true;
        } else if (arg === "--restart-verbose" || arg === "-RV") {
            restartVerbose = true;
        } else if (arg === "--watch" || arg === "-w") {
            watch = args.shift();
        } else if (arg == "--non-interactive" || arg === "-t") {
            interactive = false;
        } else if (arg === "--ignore" || arg === "-i") {
            ignore = args.shift();
        } else if (arg === "--save-pid" || arg === "-pid") {
            pidFilePath = args.shift();
        } else if (arg === "--ignore-symlinks") {
            ignoreSymLinks = true;
        } else if (arg === "--poll-interval" || arg === "-p") {
            poll_interval = parseInt(args.shift());
        } else if (arg === "--extensions" || arg === "-e") {
            extensions = args.shift();
        } else if (arg === "--exec" || arg === "-x") {
            executor = args.shift();
        } else if (arg === "--no-restart-on" || arg === "-n") {
            noRestartOn = args.shift();
        } else if (arg.indexOf("--debug") > -1 && arg.indexOf('--debug-brk') === -1) {
            debugFlag = arg;
        } else if (arg.indexOf('--debug-brk')>=0) {
            debugBrkFlag = true;
            debugBrkFlagArg = arg;
        } else if (arg === "--force-watch") {
            forceWatchFlag = true;
        } else if (arg === "--instant-kill" || arg === "-k") {
            instantKillFlag = true;
        } else if (arg === "--timestamp" || arg === "-s") {
            timestampFlag = true;
        } else if (arg === "--") {
            program = args;
            break;
        } else if (arg[0] != "-" && !args.length) {
            // Assume last arg is the program
            program = [arg];
        }
    }
    if (!program) {
        return help();
    }
    if (!watch) {
        watch = ".";
    }
    if (!poll_interval) {
        poll_interval = 1000;
    }

    var programExt = program.join(" ").match(/.*\.(\S*)/);
    programExt = programExt && programExt[1];

    if (!extensions) {
        // If no extensions passed try to guess from the program
        extensions = "node,js";
        if (programExt && extensions.indexOf(programExt) == -1) {
            // Support coffee and litcoffee extensions
            if(programExt === "coffee" || programExt === "litcoffee") {
                extensions += ",coffee,litcoffee";
            } else {
                extensions += "," + programExt;
            }
        }
    }
    fileExtensionPattern = new RegExp("^.*\.(" + extensions.replace(/,/g, "|") + ")$");

    if (!executor) {
        executor = (programExt === "coffee" || programExt === "litcoffee") ? "coffee" : "node";
    }

    if (debugFlag) {
        program.unshift(debugFlag);
    }
    if (debugBrkFlag) {
        program.unshift(debugBrkFlagArg);
    }
    if (harmony) {
        program.unshift("--harmony");
    }
    if (inspect) {
        program.unshift("--inspect");
    }
    if (harmony_default_parameters) {
        program.unshift("--harmony_default_parameters");
    }
    if (harmony_destructuring) {
        program.unshift("--harmony_destructuring");
    }
    if (executor === "coffee" && (debugFlag || debugBrkFlag)) {
        // coffee does not understand debug or debug-brk, make coffee pass opti ...
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
