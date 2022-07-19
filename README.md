# webrtc_build_methods
This is one of the easiest ways to compile WebRTC

https://webrtc.github.io/webrtc-org/native-code/development/

# 下载src
```sh
mkdir webrtc
cd webrtc
fetch --nohooks webrtc_ios
#or
fetch --nohooks webrtc_android
gclient sync
cd src/
# 如果你想同步最新源码的话
git config branch.autosetupmerge always
git config branch.autosetuprebase always

# 查看当前分支版本
git branch
# 创建新的分支
git checkout -b <ios>
# 编译出xcodeproject
gn gen out/xcode --args='target_os="ios" target_cpu="x64" rtc_include_tests=false ios_enable_code_signing=false' --ide=xcode
# 使用xcode打开all.xcodeproj,targets选择'framework_objc_signed_bundle'进行编译运行。如果成功在`out/xcode`目录会得到WebRTC.framework动态库

```
# error handle
Showing Recent Messages
The Legacy Build System will be removed in a future release. You can configure the selected build system and this deprecation message in File > Project Settings.


重新手动操作一次这个操作:在打开Xcode->file->Project Settings...->Build System:New Build System(Default)->Done
