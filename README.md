# Demo Vapor Application

Vapor is a web framework for Swift. 

## Run the project on Ubuntu

* Setup swift and vapor if not setup.

* Clone the repository

    ```bash
    git clone https://github.com/ShriramShagri/demo-vapor-app.git
    cd demo-vapor-app
    ```

* Run the command
    ```bash
    swift run
    ```

    The command will build the project. Once running you should see the following in your command line:

    ```bash
    [ INFO ] Server starting on http://127.0.0.1:8080
    ```

## Setup swift and vapor on Ubuntu

### Install Dependencies
* First ensure that your package index and installed packages are up to date with the following command.

    ```bash
    sudo apt update && sudo apt upgrade
    ```

* Next, install the dependencies with the following command.

    ```bash
    sudo apt install binutils git gnupg2 libc6-dev libcurl4 libedit2 libgcc-9-dev libpython2.7 libsqlite3-0 libstdc++-9-dev libxml2 libz3-dev pkg-config tzdata zlib1g-dev
    ```

### Download Swift

* Download the swift for Ubuntu 20.04 from the [swift download page](https://swift.org/download/) with the following command.

    ```bash
    wget https://swift.org/builds/swift-5.4.1-release/ubuntu2004/swift-5.3.3-RELEASE/swift-5.3.3-RELEASE-ubuntu20.04.tar.gz
    ```

### Verifying the Download

* Download the PGP signature.

    ```bash
    wget https://swift.org/builds/swift-5.4.1-release/ubuntu2004/swift-5.3.3-RELEASE/swift-5.3.3-RELEASE-ubuntu20.04.tar.gz.sig
    ```

* Import Swift’s PGP keys using the following command.

    ```bash
    gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys '7463 A81A 4B2E EA1B 551F  FBCF D441 C977 412B 37AD' '1BE1 E29A 084C B305 F397  D62A 9F59 7F4D 21A5 6D5F' 'A3BA FD35 56A5 9079 C068  94BD 63BC 1CFE 91D3 06C6' '5E4D F843 FB06 5D7F 7E24  FBA2 EF54 30F0 71E1 B235' '8513 444E 2DA3 6B7C 1659  AF4D 7638 F1FB 2B2B 08C4' 'A62A E125 BBBF BB96 A6E0  42EC 925C C1CC ED3D 1561' '8A74 9566 2C3C D4AE 18D9  5637 FAF6 989E 1BC1 6FEA'
    ```

* Use the signature that you downloaded to verify the integrity of the tarball that you downloaded with the following command.

    ```bash
    gpg --verify swift-5.3.3-RELEASE-ubuntu20.04.tar.gz{.sig,}
    ```

    If the tarball was downloaded without any issues and is safe to be used then you should see the following line in the output `gpg: Good signature from "Swift 5.x Release Signing Key <swift-infrastructure@swift.org>"`.


### Install and setup

* Extract the tarball to your home directory.

    ```bash
    tar -xvzf swift-5.3.3-RELEASE-ubuntu20.04.tar.gz -C ~
    ```

* Add the swift executables to our PATH and update the PATH environment variable

    ```bash
    echo "PATH=~/swift-5.3.3-RELEASE-ubuntu20.04/usr/bin:$PATH" >> ~/.bashrc

    . ~/.bashrc
    ```

    To verify that this went through correctly enter `$ swift --version` and if you receive output similar to `Swift version 5.3.3 (swift-5.3.3-RELEASE) Target: x86_64-unknown-linux-gnu`

### Install Vapor Toolbox

* Get Vapor from Github

    ```bash
    git clone https://github.com/vapor/toolbox.git
    cd toolbox
    git checkout <desired version>
    make install
    ```

* Check the installation

    ```bash
    vapor --help
    ```
