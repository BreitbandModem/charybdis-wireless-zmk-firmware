# How to Flash the Nordic Dongle

1. Install nrfutil (Python tool) and nrfutil device
2. Generate a DFU package from your hex file:

    ```bash
    nrfutil pkg generate --hw-version 52 --sd-req=0x00 --application charybdis_dongle.hex --application-version 1 charybdis_dongle.zip
    ```

3. Flash the package (replace /dev/ttyACM0 with your dongle's port):

```bash
    sudo nrfutil dfu usb-serial -pkg charybdis_dongle.zip -p /dev/ttyACM0
```
