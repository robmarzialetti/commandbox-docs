# Installation

Regardless of where you place the **box** binary, the first time you execute it, a `.CommandBox` folder will be created in your user's home directory and CommandBox will be extracted into that location. If you delete this directory, it will be replaced the next time the CommandBox executable is run.

You can specify a different install location by adding `-commandbox_home=E:\CommandBox` when you run the box binary.

To avoid specifying the commandbox\_home variable every time you can create a file called `commandbox.properties` \(case sensitive\) in the same directory as the binary, and fill it with this line:

```bash
commandbox_home=E:\\CommandBox
```

The CommandBox home can also be a path relative to the location of the `commandbox.properties` file.

```bash
commandbox_home=../boxHome
```

## Windows

Unzip the executable **box.exe** and just double click on it to open the shell. When you are finished running commands, you can just close the window, or type `exit`.

> **Hint** You can make the `box.exe` available in any Windows terminal by adding its location to the `PATH` system environment variable. See [http://www.computerhope.com/issues/ch000549.htm](http://www.computerhope.com/issues/ch000549.htm)

## Mac/  \*Unix

### Homebrew \(Mac\)

[Homebrew](http://brew.sh) is a great Mac package manager, it can easily install and keep your CommandBox installation up to date \(even binary releases\), just run the following for stable releases:

```bash
brew install commandbox
```

To stay with current bleeding edge releases use the following:

```bash
brew tap ortus-solutions/homebrew-boxtap
brew install --head ortus-solutions/homebrew-boxtap/commandbox
```

Then run the `box` binary to begin the one-time unpacking process.

Versions will be installed in `/usr/local/Cellar/commandbox`. To switch between versions, simply use `brew switch commandbox [version number]`

If you want to use a `commandbox.properties` file as mentioned above, your `box` _binary_ file will be in the `/usr/local/Cellar/commandbox/<version>/bin/libexec/bin/` directory where you should place your `commandbox.properties` file. There will also be a `box` _alias_ in the `/usr/local/bin/` directory where you should place the `jre` if you want CommandBox to use a version of Java that is different from your default version reported by `java -version`.

When using Homebrew to install CommandBox you must use Homebrew for any upgrade, minor or major. To upgrade CommandBox with Homebrew:

```bash
brew upgrade commandbox
```

NOTE: If you use Homebrew to upgrade your version of CommandBox it will erase your `commandbox.properties` file. So before upgrading, take a copy of your `commandbox.properties` file to drop back into `/usr/local/Cellar/commandbox/<version>/bin/libexec/bin/` before running `box` for the first time after upgrading.

### Manual Installation

Unzip the binary **box** and just double click on it to open the shell terminal. When you are finished running commands, you can just close the window, or type `exit`.

> **Hint** You can place the binary in your `/usr/bin` directory so it can be available system-wide via the `box` command in any terminal window.

## Linux apt-get

> **Please note** that if you are running Ubuntu 18.04 or greater, or Debian 8 \(Jessie\) or greater, it's necesarry to have the `libappindicator-dev` package in order to have the tray icon working correctly.

```bash
sudo apt install libappindicator-dev
```

Run the following series of commands to add the Ortus signing key, register our Debian repo, and install CommandBox.

### Stable

```bash
curl -fsSl https://downloads.ortussolutions.com/debs/gpg | sudo apt-key add -
echo "deb https://downloads.ortussolutions.com/debs/noarch /" | sudo tee -a /etc/apt/sources.list.d/commandbox.list
sudo apt-get update && sudo apt-get install apt-transport-https commandbox
```

Then run the `box` binary to begin the one-time unpacking process.

## Linux yum

### Stable

Add the following to: `/etc/yum.repos.d/commandbox.repo`

```text
[CommandBox]
name=CommandBox $releasever - $basearch
failovermethod=priority
baseurl=http://downloads.ortussolutions.com/RPMS/noarch
enabled=1
metadata_expire=7d
gpgcheck=0
```

Then run:

```bash
sudo yum update && yum install commandbox
```

## Debian Linux manual install

After you have downloaded the `commandbox.deb` file, install it using the `dpkg` command.

```bash
sudo dpkg -i commandbox-debian-1.2.3.deb
```

Run the `box` binary to begin the one-time unpacking process.

## Redhat Linux manual install

After you have downloaded the `commandbox.rpm` file, install it using the `rpm` command.

```bash
rpm –ivh commandbox-rpm-1.2.3.rpm
```

