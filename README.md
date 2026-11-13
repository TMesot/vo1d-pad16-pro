# A cheap tablet that fakes almost all of its hardware, and ships with a botnet

Relatives bought a "2026 Pad 16 PRO" on AliExpress and asked me to take a look before using it. The specs were fake, and the firmware ships with a Vo1d-family bot linked into `libandroid_runtime.so`.

The write-up is in [`index.html`](index.html), served through GitHub Pages.

## Short version

- Sold as a Snapdragon 8 Gen 3 with 16 GB RAM, 1 TB storage and Android 15. It is a 2016 MediaTek MT6750 with 23 GB of usable storage, running Android 10.
- `libandroid_runtime.so` carries a bot that Zygote starts inside every app. Its bootstrap server, `3.132.75.97`, is listed on ThreatFox as a Vo1d command server.
- The firmware blocks CPU-Z and rewrites what about 17 benchmark apps display, including AnTuTu's "genuine device" check.
- The preinstalled updater can silently install any APK its server sends.

## Samples

Both libraries are on MalwareBazaar:

- arm64: [`04e6f503542e4bcf0e8dc51bc97c9698f2c212c664549ebed225ca92e497dc1a`](https://bazaar.abuse.ch/sample/04e6f503542e4bcf0e8dc51bc97c9698f2c212c664549ebed225ca92e497dc1a/)
- arm32: [`5bc0839e87e68f192f90c6f2923bea7f739690a412b4b054118107c331119581`](https://bazaar.abuse.ch/sample/5bc0839e87e68f192f90c6f2923bea7f739690a412b4b054118107c331119581/)

## Reference

- XLab, [Long Live The Vo1d Botnet](https://blog.xlab.qianxin.com/long-live-the-vo1d_botnet/)

Personal research, done in my own time. Questions or corrections: open an issue here, or reach me on [LinkedIn](https://www.linkedin.com/in/titouan-mesot-b45b3115a/).
