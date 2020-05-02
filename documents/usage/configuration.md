# 配置文件说明

## 配置文件位置

运行包版：在 `yobot.exe` 同目录下的 `yobot_config.json`

源码版：在 `src/client/yobot_config.json`

插件版：在 `<插件目录>/yobot/src/client/yobot_data/yobot_config.json`

## 配置格式

目前只支持 json 格式

## 示例

高亮部分必要，其他部分供参考，详细说明参考[httpapi文档](https://cqhttp.cc/docs/#/Configuration)

不懂就全部复制

```json {2-7}
{
    "use_http": false,
    "use_ws": false,
    "use_ws_reverse": true,
    "ws_reverse_api_url": "ws://127.0.0.1:9222/ws/api/",
    "ws_reverse_event_url": "ws://127.0.0.1:9222/ws/event/",
    "access_token": "your-token",
    "host": "[::]",
    "port": 5700,
    "ws_host": "[::]",
    "ws_port": 6700,
    "ws_reverse_url": "ws://127.0.0.1:9222",
    "ws_reverse_reconnect_interval": 4000,
    "ws_reverse_reconnect_on_code_1000": true,
    "post_url": "",
    "secret": "",
    "post_message_format": "string",
    "serve_data_files": false,
    "update_source": "github",
    "update_channel": "stable",
    "auto_check_update": false,
    "auto_perform_update": false,
    "show_log_console": true,
    "log_level": "info"
}
```

## 配置项说明

`host` 服务绑定的地址，默认值 `0.0.0.0`（插件版沿用主配置）

`port` 服务绑定的地址，默认值 `9222`（插件版沿用主配置）

`public_address` web 模式可以被访问的地址（如 nginx 代理后的地址），如`https://robot.yobot.xyz:9222/`，默认自动检测

`public_basepath` web 模式使用的目录，如 `/`，默认值 `/yobot/`（如果使用了反向代理则视情况而定）

`show_icp` 是否在主页显示 icp 备案信息，默认值`false`（如果需要展示备案信息，需要将 `port` 设置为 `80`、`public_basepath` 设置为 `/`，如果使用了反向代理则视情况而定）

`icp_info` icp 备案信息

`gongan_info` 公安备案信息

`web_mode_hint` web 模式使用提示，默认值 `true`，在 web 模式下进行一次设置后自动修改为 `false`

`clan_battle_mode` 公会战统计方式，可选`web` `chat` `none`，默认值 `web`

`access_token` 与 httpapi 通信的 token，默认值 `null`（插件版沿用主配置）

`client_salt` 客户端盐，自动生成，请勿修改

`super-admin` 管理员 qq号 列表

`black-list` 黑名单 qq号 列表

`black-list-group` 黑名单 qq群 列表

`setting-restrict` 更新和重启指令需要的权限，`0`仅主人，`1`群主，`2`管理员，`3`所有人，默认值 `3`

`auto_update` 自动更新，默认值 `true`

`update-time` 自动更新时间，如 `03:30`，默认为随机的凌晨时间

`gacha_on` 开启群聊抽卡功能，默认值 `false`

`gacha_private_on` 开启私聊抽卡功能，默认值 `false`

`news_jp_official` 开启日服官网新闻推送，默认值 `true`

`news_jp_twitter` 开启日服推特新闻推送，默认值 `true`

`news_tw_official` 开启台服官网新闻推送，默认值 `true`

`news_tw_facebook` 开启台服 FaceBook 新闻推送，默认值 `true`

`news_cn_official` 开启国服官网新闻推送，默认值 `true`

`news_cn_bilibili` 开启国服 Bilibili 动态新闻推送，默认值 `true`

`news_interval_auto` 自动优化新闻推送检测时间，默认值 `true`

`news_interval_minutes` 新闻推送检测间隔分钟，默认值 30，当 `news_interval_auto` 启用时此项不生效

`calender_region` 日程表地区，可选`jp` `tw` `cn`

`calender_on` 每日提醒日程，默认值 `true`

`calender_time` 每日提醒日程时间，默认值 `08:00`

`notify_groups` 每日提醒与新闻推送群组

`notify_privates` 每日提醒与新闻推送私聊

`preffix_on` 指令前缀开关（提高性能，防止误触发），默认值 `false`

`preffix_string` 指令前缀字符串

`zht_in` 接受繁中输入（降低性能），默认值 `false`

`zht_out` 输出转化为繁中，默认值 `false`

`zht_out_style` 输出转化为繁中风格，可选`s2t` `s2tw` `s2hk` `s2twp`，默认值 `s2t`
