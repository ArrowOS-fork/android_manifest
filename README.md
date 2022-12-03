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

```bash
# We took some of Code Linaro optimizations and ported it to AOSP,
# But due to some stuffs we were not able to make the system parse the device perfconfigstore.xml automatically
# builders might need to tune runtime properties listed below (with reference and CLO counterparts)

# Memory properties

# Max cached app processes in system, overrides "config_customizedMaxCachedProcesses"
persist.sys.fw.bg_apps_limit=96

# App compaction - refer to perfconfigstore.xml (if available) for tuning purposes
persist.sys.appcompact.enable_app_compact=false
persist.sys.appcompact.full_compact_type=2
persist.sys.appcompact.some_compact_type=4
persist.sys.appcompact.compact_throttle_somesome=5000
persist.sys.appcompact.compact_throttle_somefull=10000
persist.sys.appcompact.compact_throttle_fullsome=500
persist.sys.appcompact.compact_throttle_fullfull=10000
persist.sys.appcompact.compact_throttle_bfgs=600000
persist.sys.appcompact.compact_throttle_persistent=600000
persist.sys.appcompact.rss_throttle_kb=12000
persist.sys.appcompact.delta_rss_throttle_kb=8000
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
