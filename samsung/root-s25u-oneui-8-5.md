# Samsung S25 Ultra 保数据保 ROOT 升级 OneUI 8.5

## 前提

在 OneUI 7上已解锁 BL

## 简要步骤

- 从 OneUI7 的 BL 文件中提取 abl.elf.lz4（S9380ZCU5AYHA）
- 从 OneUI 8.5 BL 中提取出 vbmeta.img.lz4 
- 从 OneUI 8.5 AP 文件中提取出 init_boot.img.lz4
- 将 init_boot.img.lz4 和 vbmeta.img.lz4 打包成 tar 文件，使用 Magisk 修补
- 从 Magisk 修补的文件中提取出 vbmeta.img 文件
- 将 BL 中的 abl.elf.lz4 和 vbmeta.img.lz4 文件删掉，然后替换成从 OneUI 7 中提取的 abl.elf.lz4 和 Magisk 修补过的 vbmeta.img 文件

接下来就是常规保数据刷机流程
- BL 放替换之后的 BL
- AP 放官方 AP
- CP 放官方 CP
- CSC 放 HOME_CSC 开头的
- USERDATA 放 Magisk 修补过的 init_boot.tar
- PIT 放从 CSC_xxx 提取的 pit 文件


## 注意
- BL 千万不能升级到 OneUI 8 及之后的版本，否则永久散失解锁能力