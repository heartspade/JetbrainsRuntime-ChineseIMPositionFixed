# 最新版本的 JetbrainsRuntime 已经修复了候选框不跟随的问题

# JetbrainRuntime-ChineseIMPositionFixed
A patch to JetbrainsRuntime to fix fcitx popup window does not show near text cursor

## 克隆官方库和补丁
```shell
git clone https://github.com/JetBrains/JetBrainsRuntime
git clone https://github.com/uLxy/JetbrainsRuntime-ChineseIMPositionFixed.git
```

## 安装补丁
```shell
cd JetBrainsRuntime
git checkout jbr17
git apply ../JetbrainsRuntime-ChineseIMPositionFixed/fix-fcitx-window-position.patch
```

## (Optional) 安装必要的依赖 (for openSUSE Leap 15.4)
``` shell
sudo zypper install autoconf make zip gcc gcc-c++ libX11-devel libXext-devel libXrender-devel libXrandr-devel libXtst-devel libXt-devel libXi-devel cups-devel fontconfig-devel alsa-devel
```

## 构建 OpenJDK
``` shell
bash configure --with-boot-jdk=/opt/java/jdk-17.0.4.1
make images
```

## 使用构建产物替换 Jetbrains 的 jbr 目录
使用构建好的 OpenJDK (`build/linux-x86_64-server-release/jdk`) 替换 Jetbrains 的 jbr 目录, 如果 jdk 的 lib 目录存在软链接指向 support 目录, 需要连同 support 目录一起复制

```shell
sudo mv /opt/intellij-idea/jbr /opt/intellij-idea/jbr.bak
sudo mv build/linux-x86_64-server-release/jdk /opt/intellij-idea/jbr
sudo mv build/linux-x86_64-server-release/support /opt/intellij-idea/support
```
