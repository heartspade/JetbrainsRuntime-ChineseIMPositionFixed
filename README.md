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

## 构建 OpenJDK
``` shell
bash configure # --with-boot-jdk=/opt/java/jdk-17.0.4.1
make images
```

## 使用构建产物替换 Jetbrains 的 jbr 目录
使用构建好的 OpenJDK (`build/linux-x86_64-server-release/jdk`) 替换 Jetbrains 的 jbr 目录, 如果 jdk 的 lib 目录存在软链接指向 support 目录, 需要连同 support 目录一起复制
