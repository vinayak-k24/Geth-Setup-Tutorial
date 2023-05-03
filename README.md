## Geth Installation Tutorial

This tutorial will guide you through the installation process for Geth 1.11.6 on Ubuntu Linux.

### Step 1: Update the repositories

To update the repositories, run the following commands:

```
sudo apt update
sudo apt upgrade
```
This will update the repositories and upgrade any packages that need to be upgraded on your Linux machine.

**Note:** It is recommended to keep your system up-to-date to ensure the latest security patches are installed.



### Step 2: Download the latest stable version of Geth

Download the Geth 1.11.6 stable file (.tar.gz) from the official website or GitHub repository.

You can download the latest stable version of Geth for Linux 64-bit directly from the official Geth website. Here's how:

1. Go to the Geth website at https://geth.ethereum.org/downloads/
2. Scroll down to the "Stable Releases" section.
3. Find the "Geth & Tools 1.11.6" release and click on the "Linux (64-bit)" link next to it.
4. The download will start automatically.



### Step 3: Extract the Geth file

Extract the downloaded file using the following command:

```
sudo tar xvf geth-alltools-linux-amd64-{version number}.tar.gz
```

For Example :

```
sudo tar xvf geth-alltools-linux-amd64-1.11.6-ea9e62ca.tar.gz
```
This command will extract the Geth file that you downloaded earlier. You should replace {version number} with the actual version number of the file that you downloaded.



### Step 4: Navigate to the extracted folder

```
cd geth-alltools-llinux-amd64-1.11.6-ea9e62ca
```
This will change your current directory to the `geth-alltools-llinux-amd64-1.11.6-ea9e62ca` directory.



### Step 5: Make the Geth file executable

Make the `geth` file executable with the following command:

```
sudo chmod +x geth
```
This will give the `geth` file executable permission.



### Step 6: Copy the Geth file to /usr/local/bin

```
sudo cp geth /usr/local/bin/
```



### Step 7: Verify the Geth version

Verify that the Geth version is installed correctly by running the following command:

```
geth version
```
This will copy the `geth` file to the `/usr/local/bin/` directory, which is included in the `PATH` variable, making it easier to run `geth` from anywhere in the terminal.



### Step 8: Create a new directory

Make a new directory for your single node setup with the following command:

```
mkdir singlenode
```

Navigate to the newly created directory with the following command:

```
cd singlenode
```

### Step 9: Create a genesis file

Create a new file named genesis.json in the singlenode directory using a text editor such as `nano` or `gedit`. For example, to create the file using gedit, run the following command:

```
gedit genesis.json
```
This will open a blank file in the terminal window. You can then add the necessary content to the file, which defines the initial configuration for the blockchain network.

### Step 10: Add content to the Genesis file

Open the `genesis.json` file with your preferred text editor and add the following content to the file:

```
{
    "config": {
        "chainId": 4321,
        "homesteadBlock": 0,
        "eip150Block": 0,
        "eip155Block": 0,
        "eip158Block": 0,
        "byzantiumBlock": 0,
        "constantinopleBlock": 0
    },
    "alloc": {},
    "difficulty" : "0x20000",
    "gasLimit"   : "0x8880000"
}
```
Save the file and close the text editor.

### Step 11: Create a directory for the node

Create a new directory for your first node using the following command:

```
mkdir node1
```


### Step 12: Initialize the genesis file

Navigate back to the singlenode directory and Initialize Node 1 with the Genesis file using the following command:

```
cd ..
```

In your singlenode directory run the following command:
```
geth --datadir node1 init genesis.json
```

This will create the necessary files for the blockchain network in the `node1` directory.

### Step 13: Start the node

To start the node, enter the following command:

```
geth --http --http.corsdomain http://remix.ethereum.org --allow-insecure-unlock --http --http.port 8545 --http.addr 127.0.0.1 --http.corsdomain "*" --http.api "eth,net,web3,personal,miner" --datadir node1 --nodiscover --networkid 4321 --port 30303 console --rpc.enabledeprecatedpersonal
```
This command will start the node and provide access to the Geth console.


### Additional Instructions :

In order to start the Geth console, you first need to initialize the genesis block using the command in Step 12, and then start the node using the command in Step 13. You will need to repeat these steps every time you want to start the console.

You can simplify the process and avoid having to copy and paste the same commands every time by creating aliases for them. This will allow you to easily work with Geth without having to remember or type out the entire commands every time.

For aliasing follow the steps below:

1. Open your `.bashrc` file with the following command:
```
gedit ~/.bashrc
```

2. Scroll to the bottom of the file and add the following line:
```
alias mygeth='geth --http --http.corsdomain http://remix.ethereum.org --allow-insecure-unlock --http --http.port 8545 --http.addr 127.0.0.1 --http.corsdomain "*" --http.api "eth,net,web3,personal,miner" --datadir ~/singlenode/node1 --nodiscover --networkid 4321 --port 30303 console --rpc.enabledeprecatedpersonal'
```

3. Save the file and exit the editor.

4. Reload the `.bashrc` file with the following command:
```
source ~/.bashrc
```
5. Now you can start the Geth console with the following command:
```
mygeth
```

With aliasing, you can easily start the Geth console by simply typing `mygeth` in the terminal instead of running the lengthy command every time.
