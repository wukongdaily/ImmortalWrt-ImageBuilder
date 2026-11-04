## ImmortalWrt for 斐讯N1
#### luci版本 24.10.2 固件不是传统ext4和squashfs格式 而是btrfs格式 支持快照
#### 后台地址 `没有没有没有,需查询` 详见下文
#### 用户名 `root` 密码：password
#### 是否带docker: 根据用户选择
#### 默认软件包大小 1GB
#### 内核版本:根据用户选择
#### 晶晨宝盒：✅ 自带 用于写入emmc （这一步等以后稳定再考虑写入 非必要不写入 其实用U盘很自由）
#### rootfs.tar.gz 构建采用ImmortalWrt的ImageBuilder
#### 打包img 采用`onhub/amlogic-s9xxx-openwrt` 或 `flippy-openwrt-actions`
#### 默认底包位置：https://github.com/wukongdaily/AutoBuildImmortalWrt/releases/tag/rootfs


### 斐讯N1为单网口设备 网线接上路由器 启动后默认是自动获取ip的模式<br> 请在上级路由器的dhcp列表中查询具体的局域网ip
### 若后续想设置其他ip或者旁路 请在web页面自行设置即可 <br> 总之 这个逻辑就是默认让它有网 和 普通电脑、NAS 无异
### 一定要阅读清楚 再刷机 推荐使用U盘做测试（0风险） 不建议一开始就写入EMMC
## 各位尽量不要直接使用项目中的release 要自己fork项目后自行构建  <br> 本项目中的release仅用于作者测试 且会定期删除
##### 若release中下载吃力 可在国内加速站下载 
[![Github](https://img.shields.io/badge/Release文件可在国内加速站下载-FC7C0D?logo=github&logoColor=fff&labelColor=000&style=for-the-badge)](https://wkdaily.cpolar.top/archives/1) 
---

### 📌 晶晨 S905X3 等外贸盒子（非 N1）使用必看

本项目镜像底层基于通用晶晨全家桶打包，**支持 S905X3 / S905X2 / S922X 等全系外贸盒子**。  
因出厂默认预设为 N1 设备树，**S905X3 刷写 U 盘后必须修改一次设备树，否则无法开机！**

#### 极速启动 4 步走（只需 30 秒）：

1. **写盘**：将生成的 `.img.gz` 固件用 Rufus 或 Etcher 写入 U 盘。
2. **改设备树**：
   * 写盘完成后，打开电脑里多出来的 **`BOOT`** 分区。
   * 用记事本打开根目录下的 **`uEnv.txt`**。
   * 找到 `dtb_name=` 这一行，默认是 N1 的配置。
   * **对照项目里的 `box.md`**，将名称改为你的 S905X3 对应型号，例如：
     * **X96 Max+ / 常见 S905X3 千兆版**：`dtb_name=/dtb/amlogic/meson-sm1-x96-max-plus.dtb`
     * **HK1 Box / VONTAR X3**：`dtb_name=/dtb/amlogic/meson-sm1-hk1box-vontar-x3.dtb`
   * 按 `Ctrl + S` 保存并安全弹出 U 盘。
3. **点火开机**：
   * U 盘插在盒子的 USB 3.0 接口（通常是蓝色口）。
   * 用牙签顶住盒子背面的 **AV 孔（内部复位键）** 不放，插上电源。
   * 电视画面亮起或网口灯闪烁后松开牙签，即可顺利由 U 盘引导。
4. **进后台**：
   * 默认通过 DHCP 自动获取 IP，请在**主路由器的设备列表**中查看分配给盒子的新 IP。
   * 浏览器输入该 IP 即可进入后台（用户名：`root`，密码：`password`）。
  
5. 
