# RL78_F24_Basic_Boot_loader_app_e2

RL78/F24 Basic App example. Software CRC32; includes e2 studio project configuration.
Basic describes the example's integration scope, not its ROM footprint.

## Project and paired source

- CS+ project: `RL78_F24_Basic_Boot_loader_app_e2.mtpj`.
- Paired project: [RL78_F24_Basic_Boot_loader_UART_e2](https://github.com/released/RL78_F24_Basic_Boot_loader_UART_e2), checked out as a sibling directory with this exact name.
- Boot reserve: 20 KiB; App starts at `0x5000`. Partition/checksum settings are in `user_def.h` (Boot) and `ftable.inc` (Boot/App).
- Build Boot first so `copy_fsy.bat` supplies its linker symbols to the paired App; then build App. The `_e2` pair also includes e2 studio configuration.

## Guide

[Basic UART / I2C / XMODEM examples](https://released.github.io/slide_boot_loader_for_RL78/basic_uart_i2c/)
contains configuration, startup, manual IRQ forwarding and checksum packaging steps.
[Basic and CAN golden sample comparison](https://released.github.io/slide_boot_loader_for_RL78/#basic-vs-golden)
describes the different image and update contracts. Use this pair's downloader and fixed-range image files; its BIN is not a CAN golden-sample update image.

[Flash execution from RAM](https://released.github.io/slide_boot_loader_for_RL78/#flash-ram-execution)
and [CRC backends](https://released.github.io/slide_boot_loader_for_RL78/#crc-backends)
cover the execution constraints and checksum parameters.