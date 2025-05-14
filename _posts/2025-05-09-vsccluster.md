---
title: 'A guide to connecting VSCode to a remote cluster'
date: 2025-05-09
permalink: /posts/2025/05/blog-post-vsccluster/
tags:
  - Computing
  - Cluster
---

Working on a remote cluster is a common task in many scientific fields. Here, I will show how to connect VSCode to a remote cluster. I take the [LRZ cluster](https://doku.lrz.de/access-and-login-to-the-linux-cluster-10745974.html) as an example.

Suppose your LRZ-username (LRZ-Kennung) is "username".
Our goal is to connect to LRZ without having to type our password each time.
You cannot avoid 2FA! Everytime you will have to give 2FA.

1. Manually download the extension [Remote-SSH](hhttps://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh). It doesn't seem to be automatically downloaded although VSCode claims so.

2. Open Windows Powershell with admin rights

    ```sh
    ssh-keygen -t ed25519 -C "username@lrz"
    ```
    (press `<Enter>` three times for defaults)

    ```powershell
    type $env:USERPROFILE\.ssh\id_ed25519.pub | ssh -Y username@cool.hpc.lrz.de "umask 077 && mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
    ```

3. Create a local .ssh config file. Stored in `C:\Users\<WindowsUser>\.ssh\config`

    ```bash
    # ensure the ~/.ssh directory exists
    mkdir -p ~/.ssh

    # write the configuration
    cat > ~/.ssh/config <<'EOF'
    Host lrz-hpc
        HostName cool.hpc.lrz.de
        Port 2222
        User username
        IdentityFile ~/.ssh/id_ed25519
        IdentitiesOnly yes
        ForwardX11 yes
        ServerAliveInterval 60
    EOF

    # secure the file
    chmod 600 ~/.ssh/config
    ```

4. Enable the Windows SSH agent (optional but convenient)

    ```powershell
    Set-Service ssh-agent -StartupType Automatic
    Start-Service ssh-agent
    ssh-add $env:USERPROFILE\.ssh\id_ed25519
    ```

5. **In VSCode:**
    `Ctrl + Shift + P` → `Remote-SSH: Add New SSH Host…`
    Enter: `ssh lrz-hpc`
    The first connection installs the VS Code Server in `$HOME/.vscode-server/` on the cluster and takes long.
    Enter passwords or 2FA when prompted.

6. **Note:** You get logged in to the login node, and heavy computation is prohibited there! If you hit the "Run python code" button, the code will be executed in the current terminal, i.e. login node. You need to start an interactive session each time.

7. Configure your `.vscode` folder so that you get an interactive session easily.
    **In `.vscode/launch.json`:**
    ```json
    {
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Python on compute node",
                "type": "python",
                "request": "launch",
                "program": "${file}",
                "console": "integratedTerminal",
                "preLaunchTask": "slurm-srun"
              }
        ]
    }
    ```
    **In `.vscode/tasks.json`:**
    ```json
    {
        "version": "2.0.0",
        "tasks": [
          {
            "label": "slurm-srun",
            "type": "shell",
            "command": "if [[ -z $SLURM_JOB_ID ]]; then srun -M inter -p cm4_inter -n 1 -c 4 --mem=32G -t 03:00:00 --pty bash -l; fi",
            "problemMatcher": []
          }
        ]
    }
    ```
    *Modify the parameters in the `slurm-srun` task command as you need!*

8. To use, i.e. to start an interactive session, press `Ctrl + F5`

