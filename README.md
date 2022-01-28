# JetbrainRuntime-ChineseIMPositionFixed
A patch to JetbrainsRuntime to fix fcitx popup window does not show near text cursor

```shell
git clone https://github.com/JetBrains/JetBrainsRuntime

git clone https://github.com/uLxy/JetbrainsRuntime-ChineseIMPositionFixed.git

cd JetBrainsRuntime

git checkout d9366800c84eb5cddac8966ea3e246ef0cfff2bc

git patch apply ../JetbrainsRuntime-ChineseIMPositionFixed/0001-fix-fcitx-window-position-issue.patch

bash configure #args

make images
```
