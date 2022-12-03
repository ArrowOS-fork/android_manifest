<img src="https://github.com/ArrowOS-fork/getting_started/blob/main/misc/logo.png?raw=true">

# ArrowOS Fork

 Getting Started
---------------
To get started with the ArrowOS sources, you'll need to get
familiar with [Git and Repo](https://source.android.com/setup/build/downloading).

To initialize your local repository, use command:

```bash
repo init --depth=1 -u https://github.com/ArrowOS-fork/android_manifest.git -b arrow-13.0
```

Then sync up:

```bash
repo sync -c -j$(nproc --all) --no-clone-bundle --no-tags --force-sync
```

Building the System
-------------------
 Initialize the ROM environment with the envsetup.sh script.

```bash
. build/envsetup.sh
```

Lunch your device after cloning all device sources if needed.

```bash
lunch arrow_devicecodename-buildtype
```

Start compilation

```bash
m otapackage
```

OR

```bash
m bacon
```

Credits
---------------
* [**ArrowOS**](https://github.com/ArrowOS)
