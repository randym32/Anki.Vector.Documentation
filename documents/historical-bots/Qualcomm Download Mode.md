# Qualcomm Download Mode

Qualcomm Download Mode, also known as QDL, EDL, QCOM_BLK, or HS_USB, is a mode many Qualcomm devices can be booted into which allows full programs and reads of the flash. Before you get excited, this is not something we can feasibly use on production Vectors, DVT4s, or Whiskeys at the moment. We can only use it on DVT1-3 heads, which is why it is under the Historial Bots section.

QDL can be launched by raising the F_USB pad on the headboard to 1.8v, then turning the bot on. The bot will show up as QCOM_BLK or "Qualcomm HS_USB Diagnostics 8009" through USB. On DVT1-3, you can use this [loader](https://wire.my.to/8909.mbn) and [tool](https://github.com/bkerler/edl) to make use of this mode. You can read the whole flash or specific partitions, as well as write. Any bot above DVT3 requires a different Anki-specific loader, which we don't have.

DVT1-2 heads can be upgraded to a newer partition table with this method. None of their CPU fuses are set, so they don't really care about what is on the flash. A DVT3 can also be put on old DVT1-2 software with it.

