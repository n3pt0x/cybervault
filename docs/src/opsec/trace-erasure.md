# ⛔ Trace Erasure

- [r/antiforensics/](https://www.reddit.com/r/antiforensics/) - Reddit antiforensics.

## 🚫 Forensic

> [!DANGER]
> - The **best option** is to use **SSD encryption**. However, if you want to add an extra layer of security, you can also erase your SSD beforehand.
> - Erase with `/dev/zero`: On SSDs, simple overwriting may not erase all blocks due to compression and wear leveling. Using `/dev/urandom` fills the disk with random data, reducing this risk.

- [Awesome Anti Forensic](https://github.com/shadawck/awesome-anti-forensic) - Resources list.
- [Anti Forensic](https://hackers-arise.com/category/anti-forensics/) - Articles about anti forensic.
- [Anti Forensic](https://belkasoft.com/countering-anti-forensic-efforts-part-2) - Disk encryption.

## 🛠️ Tools

- [VeraCrypt](https://veracrypt.jp/en/Home.html) - Linux, Windows, Mac.
- [TrueCrypt](https://truecrypt.fr/) - Linux, Windows, Mac.

### 🐧 Linux

- [DBAN](https://dban.org/) - For HDD only.
- [How to erase securely disk with Hdparm ?](https://www.putorius.net/securely-erase-a-sata-hard-drive-hdparm-linux.html)
- [How to hard disk encryption with cryptsecure ?](https://www.cyberciti.biz/security/howto-linux-hard-disk-encryption-with-luks-cryptsetup-command/).

### 🪟 Windows

- [ERASER](https://eraser.heidi.ie/)

## ⚡ Fast Commands

Encrypt SSD quickly.

```bash
cryptsetup luksFormat /dev/sdX --key-file <(head -c 64 /dev/urandom)
```

Some tools for erasing data.

```bash
shred -v -n 3 -z /dev/sdX
blkdiscard blkdiscard /dev/sdX
hdparm --user-master u --security-erase NULL /dev/sdX
dd if=/dev/urandom of=/dev/sdX bs=1M status=progress
```
