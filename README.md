# War Thunder 音频Mod注入工具

## 原理
游戏正常启动，使用原始文件通过启动器和 aces.exe 的双重校验
检测到游戏窗口标题从`Loading...`变为`War Thunder`后暂停 aces.exe 进程
将`sound/mod/`下的`.bank`文件覆盖到`sound/`目录（因当前版本音频引擎更新所以跳过masterbank相关文件）
恢复进程
游戏退出后自动还原原始文件

跳过`masterbank.bank`、`masterbank.strings.bank`、`masterbank.assets.bank`是因为当前版本的FMOD事件结构有变动，替换这些文件会导致进入对局时崩溃（错误码 8111000A）。

## 使用方法
1. 将音频Mod文件放入游戏目录下的`sound/mod/`文件夹
2. **右键以管理员身份运行** `wt_sound_mod.bat`
3. 正常启动游戏
4. 脚本自动完成注入，游戏退出后自动还原

脚本启动时会自动检查并还原上次运行可能残留的Mod文件，不用担心异常退出导致文件未还原。

## 许可证
MIT License
