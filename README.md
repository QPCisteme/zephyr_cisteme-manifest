# CISTEME Manifest

CISTEME ZephyrRTOS manifest to import all drivers, board and even CATIE module.

## Use with nRFConnect

**With VSCode only**, open the file : ncs/[version]/nrf/west.yml

In the remotes section add the following lines (line 42) :
```yaml
    - name: cisteme
        url-base: https://github.com/QPCisteme
```

Then in the projects section (line 297) add :
```yaml
    - name: zephyr_cisteme-manifest
      remote: cisteme
      revision: main
      import:
        true
```

Open VSCode and the "nRFConnect for VSCode" extension. Click on the search bar and select "Show and Run command -> nRFConnect : West Update"

## Content

- 6tron Module : boards and modules from CATIE
- BME280 driver

## STM32 Development

To use the nRFConnect Extension with STM32 boards, edit the same west.yml and add in the "name-allowlist" section (line 96) : 
```yaml
    - hal_stm32
```