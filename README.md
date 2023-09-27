# debug-accel-sim-framework
Run and debug Accel-Sim framework in VSCode through remote SSH.

# Scenario
Host: Windows/Linux machine
Guest/Server: Ubuntu server in which you installed the simulator

# Steps
1) Install `openssh-server` in the server.
2) Obtain IP of the server.
3) Install `Remote Development` extension in VSCode in the host. [link](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
4) Click icon on the bottom-left of VSCode to initialize an SSH connection.
5) Browse for directories.
6) Install `gdb` extension, which installs in your server.
7) Go to `Run and Debug` window (CTRL+SHIFT+D), then create a launch.json and select GDB.
8) Use below setting as an example. Check if the path of executable (`program` field) and config (`cwd` for example) of below to be correct.
```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "cppdbg",
      "request": "launch",
      "name": "gaussian",
      "program": "/home/MY_USERNAME/gpu-app-collection-1.0.1/bin/11.0/release/gaussian-rodinia-3.1",
      "cwd": "/home/MY_USERNAME/gpu-app-collection-1.0.1/bin/11.0/release",
      "args": ["-s", "16"]
    }
  ]
}
```
9) Set break points. Run. Enjoy!
