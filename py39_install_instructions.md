# To manually install Python 3.9 on Ubuntu 22.04 and use update-alternatives to switch between versions, follow these steps:

#### Step 1: Install dependencies

```bash
sudo apt update
sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev libgl1 libxkbcommon0 libegl1
```

#### Step 2: Download and build Python 3.9

```bash
cd /tmp
wget https://www.python.org/ftp/python/3.9.18/Python-3.9.18.tgz
tar -xf Python-3.9.18.tgz
cd Python-3.9.18
./configure --prefix=/usr/local/python/3.9.18 --enable-optimizations --with-ensurepip=install
make -j$(nproc)
sudo make install
```

#### Step 3: Add Python 3.9 to alternatives

```bash
sudo update-alternatives --install /usr/bin/python3.9 python3.9 /usr/local/python/3.9.18/bin/python3.9 1
```

#### Step 4: Switch between Python versions

```bash
sudo update-alternatives --config python3
```

Choose the desired version from the list.



##### *Note:* 
Do not overwrite python3 directly, as it may break system tools.
Use update-alternatives to safely switch between installed Python versions.
For pip, you can similarly add alternatives if needed.
Let me know if you need instructions for pip or want to undo previous manual installs.