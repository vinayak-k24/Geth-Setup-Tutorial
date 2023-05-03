## Geth Installation Tutorial

This tutorial will guide you through the installation process for Geth 1.11.6 on Ubuntu Linux.

### Step 1: Update the repositories

```
sudo apt update
sudo apt upgrade
```

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

### Step 4: Navigate to the extracted folder

```
cd geth-alltools-llinux-amd64-1.11.6-ea9e62ca
```

### Step 5: Make the Geth file executable

Make the `geth` file executable with the following command:

```
sudo chmod +x geth
```

### Step 6: Copy the Geth file to /usr/local/bin

```
sudo cp geth /usr/local/bin/
```

### Step 7: Verify the Geth version

Verify that the Geth version is installed correctly by running the following command:

```
geth version
```

### Step 8: Create a new directory

Make a new directory for your single node setup with the following command:

```
mkdir singlenode
```

### Step 9: Navigate to the new directory

Navigate to the newly created directory with the following command:

```
cd singlenode
```

### Step 10: Create a genesis file

Create a genesis file with the following command:

```
gedit genesis.json
```

Add the following content to the file:

```
"config":{
"chainId":
"homesteadBlock":
"eip150Block":
"eip155Block":
"eip158Block":
"byzantiumBlock":
"constantinopleBlock": 0
},"alloc":
"difficulty" : "
"gasLimit" : "
```




