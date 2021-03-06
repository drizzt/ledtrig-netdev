# ledtrig-netdev

**Kernel module to drive LEDs based on network activity**

Forked from [OpenWrt][] and distributed as standalone package.

[OpenWrt]: https://github.com/openwrt/openwrt

## Installation

 1. Install Linux headers **and** sources (required for `drivers/leds/leds.h`):

    ```sh
    sudo apt-get install linux-headers-$(uname -r) linux-source
    ```

 2. Extract the Linux sources:

    ```sh
    (cd /usr/src && sudo tar -xJf linux-source-*.tar.xz)
    ```

 3. Clone and install this module's sources:

    ```sh
    git clone https://github.com/qu1x/ledtrig-netdev.git
    sudo mv ledtrig-netdev /usr/src/ledtrig-netdev-1.0.0
    ```

 4. Build and install this module:

      - Either via Make (must be manually rebuilt for each kernel update):

        ```sh
        sudo make -C /usr/src/ledtrig-netdev-1.0.0 install
        ```

      - Or via DKMS (will be automatically rebuilt for each kernel update):

         1. Install DKMS:

            ```sh
            sudo apt-get install dkms
            ```

         2. Install this module:

            ```sh
            sudo dkms install ledtrig-netdev/1.0.0
            ```
