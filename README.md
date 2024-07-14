Here's a `README.md` file and a shell script that you can include in your GitHub repository to allow users to easily set up and manage a Nubit light node. Users can simply clone the repository and follow the instructions.

### `README.md`
```markdown
# Nubit Light Node Setup

This repository contains a script to easily set up and manage a Nubit light node.

## Hardware Requirements

- 1 core CPU
- 500 MB RAM
- 40 GB storage

## Setup Instructions

1. **Clone this repository:**
   ```sh
   git clone https://github.com/yourusername/nubit-light-node.git
   cd nubit-light-node
   ```

2. **Make sure your system is up to date:**
   ```sh
   sudo apt update && sudo apt upgrade -y
   ```

3. **Run the setup script:**
   ```sh
   chmod +x setup-nubit.sh
   ./setup-nubit.sh
   ```

4. **View the mnemonic:**
   ```sh
   cd nubit-node && sudo cat mnemonic.txt
   ```
   Please make sure to save the MNEMONIC.

5. **Check the log:**
   ```sh
   screen -r nubit
   ```
   Press `Ctrl + A` followed by `D` to detach the screen.

6. **Stop and remove the node:**
   ```sh
   ./cleanup-nubit.sh
   ```

### `setup-nubit.sh`
```sh
#!/bin/bash

# Make sure the system is up to date
sudo apt update && sudo apt upgrade -y

# Start a new screen session
screen -S nubit -d -m

# Download and install Nubit
curl -sL1 https://nubit.sh | bash

# View the mnemonic
echo "To view your mnemonic, run the following commands:"
echo "cd nubit-node && sudo cat mnemonic.txt"
echo "Please make sure to save the MNEMONIC"

# Instructions to check the log
echo "To check the log, run the following command:"
echo "screen -r nubit"
echo "Press Ctrl + A followed by D to detach the screen."

# Instructions to stop and remove the node
echo "To stop and remove the node, run the cleanup-nubit.sh script"
```

### `cleanup-nubit.sh`
```sh
#!/bin/bash

# Stop the Nubit node
pkill -f nubit

# Remove Nubit node files
rm -rf nubit-node

# Remove Nubit data directory
rm -rf $HOME/.nubit-light-nubit-alphatestnet-1

echo "Nubit node stopped and removed."
```

To use this, users would:
1. Clone your repository.
2. Follow the instructions in the `README.md`.
