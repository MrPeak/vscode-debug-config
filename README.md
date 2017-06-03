# vscode-debug-config
VSCode editor `Debug config` collection

## Mocha

```
{
  // Use IntelliSense to learn about possible Node.js debug attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "mocha",
      "type": "node",
      "request": "launch",
      "program": "${workspaceRoot}/node_modules/mocha/bin/_mocha",
      "stopOnEntry": false,
      "args": [
        "--no-timeouts",
        "--colors"
      ], //you can specify paths to specific tests here
      "cwd": "${workspaceRoot}",
      "runtimeExecutable": null,
      "env": {
        "NODE_ENV": "unittest"
      }
    }
  ]
}
```

## Egg

```
{
  // Use IntelliSense to learn about possible Node.js debug attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "node",
      "request": "attach",
      "name": "Attach Remote Worker",
      "address": "11.160.112.155",
      "port": 5859,
      "localRoot": "${workspaceRoot}",
      "remoteRoot": "/home/admin/work/intl-finance-mo-nodejs"
    },
    {
      "name": "Start Egg",
      "type": "node",
      "request": "launch",
      "program": "${workspaceRoot}/index.js",
      "cwd": "${workspaceRoot}",
      "runtimeArgs": [
        "--debug"
      ],
      "port": 5858
    },
    {
      "name": "Attach Agent", // 对5856端口进行调试
      "type": "node",
      "request": "attach",
      "port": 5856
    },
    {
      "name": "Attach Worker", // 对5859端口进行调试
      "type": "node",
      "request": "attach",
      "port": 5859
    }
  ],
  "compounds": [ // 将三个任务组合一起运行
    {
      "name": "Debug Egg",
      "configurations": [
        "Start Egg",
        "Attach Agent",
        "Attach Worker"
      ]
    }
  ]
}
```

## Chrome

