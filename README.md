
---

# SausageManGameInfo

适用于香肠人正式服的基础信息配置文件，供开发者参考及二次使用。

## 文件说明

| 文件 | 适用平台 |
|------|----------|
| game_info_win | Windows 客户端 |
| game_info_ios | 苹果客户端 |
| game_info_android | 安卓客户端 |

## 基础信息的用途

游戏在 Loading 页面加载时，会加载基础信息中的信息。

## 主要配置模块

| 模块 | 说明 |
|------|------|
| 版本控制 | 客户端、服务器、PC启动器等版本号，用于匹配与强制更新 |
| 网络地址 | 登录服、网关、测速、排行榜、战史等核心服务器地址 |
| CDN资源 | 主资源CDN、视频CDN、许可文件等静态资源地址 |
| 活动系统 | 游戏内活动页面及外部跳转链接配置 |
| 社交功能 | 论坛、好友、组队邀请分享等社交相关地址 |
| 支付系统 | 支付服务器、商店开关、防沉迷等支付与合规配置 |
| PC端专属 | 安全校验地址、启动器版本、更新器版本等PC特有字段 |
| 功能开关 | 改名、敏感内容、热更新、调试模式等大量功能开关 |
| AB测试 | 客户端A/B测试分组相关参数 |
| 性能与日志 | 日志采样率、错误追踪、性能采样等开关与配置 |
| 推送服务 | 推送开关及FCM相关配置 |

## 数据类型说明

| 类型 | 默认值 | 说明 |
|------|--------|------|
| 字符串 | "" | 空字符串 |
| 数字 | 0 | 零值 |
| 布尔 | false | 默认关闭 |
| 数组 | [] | 空数组 |
| 对象 | 保留结构 | 内部值同样清空 |

---

## 字段详细说明

### 版本控制

| 字段 | 类型 | 说明 |
|------|------|------|
| client_version | 数字 | 客户端版本号，服务端下发最低要求版本，低于此版本强制更新 |
| server_version | 数字 | 服务器版本号，用于匹配客户端与后端的协议兼容性 |
| pc_version | 字符串 | PC客户端当前版本号 |
| pc_security_version | 字符串 | PC安全模块版本号 |
| pc_version_min | 字符串 | PC客户端最低允许版本，低于此版本无法登录 |
| pc_launcher_version | 字符串 | PC启动器版本号 |
| pc_updater_version | 字符串 | PC更新器版本号 |

### 网络地址

| 字段 | 类型 | 说明 |
|------|------|------|
| login_url | 字符串 | 登录服务器地址，多个地址用逗号分隔，用于容灾切换 |
| gateway_proxy | 字符串 | 游戏网关地址，客户端通过此网关与游戏服务器通信 |
| ping_host | 字符串 | 测速服务器地址，用于客户端网络延迟检测 |
| war_history | 字符串 | 战史服务器地址，用于查询玩家历史对战记录 |
| rankings_url | 字符串 | 排行榜服务器地址 |
| geo_coding_url | 字符串 | 地理编码服务地址，用于反查地理位置 |
| newest_msg_id | 字符串 | 最新消息ID，用于消息同步或公告拉取 |
| rtm_router | 字符串 | 实时消息路由地址，基于LeanCloud的推送服务 |
| friend_addr | 字符串 | 好友系统WebSocket地址 |
| chat_ots_addr | 字符串 | 聊天服务器地址 |
| store_service_url | 字符串 | 商店服务后端地址 |
| data_info_url | 字符串 | 数据信息服务地址 |
| payment_server_url | 字符串 | 支付服务器地址 |
| tv_url | 字符串 | 赛事或直播事件API地址 |

### CDN资源

| 字段 | 类型 | 说明 |
|------|------|------|
| cdn | 字符串 | 主资源CDN地址 |
| video_cdn | 字符串 | 视频资源CDN地址 |
| license_file_url | 字符串 | 许可文件存放地址 |
| grass_ver | 字符串 | 草丛资源版本号 |
| grass_size | 数字 | 草丛资源大小（KB） |
| smbook_url | 字符串 | 图鉴系统H5页面地址 |
| cartoon_url | 字符串 | 赛季漫画/动画H5页面地址 |

### 活动系统

| 字段 | 类型 | 说明 |
|------|------|------|
| activity_url | 字符串 | 活动主页面地址，拼接token参数传递用户标识 |
| activity_urls | 对象 | 包含多个子活动页面配置 |
| activity_urls.traffic_permit | 对象 | "活动"页面的标题和URL |
| activity_urls.pizza_coupon_url | 对象 | 必胜客联名订餐页面的标题和URL |
| activity_urls.pizza_reward_url | 对象 | 必胜客联名兑换页面的标题和URL |

### 社交功能

| 字段 | 类型 | 说明 |
|------|------|------|
| bbs_url | 字符串 | 游戏论坛地址（TapTap社区） |
| groupinvite_shareurl | 字符串 | 组队邀请分享链接 |
| share_ver | 数字 | 分享功能版本号 |
| poster_api | 对象 | 海报生成API分区域地址 |
| poster_api.tw_url | 字符串 | 台湾地区海报API |
| poster_api.cn_url | 字符串 | 大陆地区海报API |
| poster_api.ot_url | 字符串 | 海外其他地区海报API |

### 支付系统

| 字段 | 类型 | 说明 |
|------|------|------|
| shop | 布尔 | 商店功能总开关 |
| shop_pay | 布尔 | 商店支付功能开关 |
| payment_server_url | 字符串 | 支付服务器地址 |
| fcm | 对象 | 防沉迷（FCM）相关配置 |
| fcm.hard_mode | 布尔 | 是否开启严格防沉迷模式 |
| fcm.ex_time | 数字 | 防沉迷检查间隔时间（秒） |
| fcm.get_remain_time | 字符串 | 查询剩余游戏时间API地址 |
| fcm.check_charge | 字符串 | 检查充值限制API地址 |
| sensitive | 布尔 | 敏感内容开关 |

### PC端专属

| 字段 | 类型 | 说明 |
|------|------|------|
| pc_security_url | 字符串 | PC安全校验服务地址 |
| pc_security_config_url | 字符串 | PC安全配置获取地址（HTTPS） |
| pc_version | 字符串 | PC客户端版本 |
| pc_version_min | 字符串 | PC最低版本要求 |
| pc_security_version | 字符串 | PC安全模块版本 |
| pc_launcher_version | 字符串 | 启动器版本 |
| pc_updater_version | 字符串 | 更新器版本 |
| download_www | 布尔 | PC端网页下载开关 |
| download_type | 数字 | 下载方式类型 |

### 功能开关

| 字段 | 类型 | 说明 |
|------|------|------|
| rename | 布尔 | 改名功能开关 |
| data_info_open | 布尔 | 数据信息功能开关 |
| cdkey_enable | 布尔 | 兑换码功能开关 |
| push_enable | 布尔 | 推送功能开关 |
| file_check_function | 布尔 | 文件校验功能开关 |
| login_debug | 布尔 | 登录调试模式开关 |
| gateway_debug | 布尔 | 网关调试模式开关 |
| gf_notice | 布尔 | 官服公告开关 |
| themis_enable | 布尔 | Themis反作弊/安全模块开关 |
| high_frame_whitelist | 布尔 | 高帧率白名单开关 |
| is_test_mod | 布尔 | 是否为测试模式 |
| use_wechat | 布尔 | 微信相关功能开关 |
| ad_crate | 布尔 | 旧版广告宝箱开关 |
| ad_crate_new | 布尔 | 新版广告宝箱开关 |
| sec_sdk_open | 数字 | 安全SDK开关（1开启/0关闭） |
| sentry_enable | 布尔 | Sentry错误追踪开关 |
| patch_enable | 数字 | 热补丁功能开关 |
| funnydb_open | 数字 | FunnyDB功能开关 |
| acereportdata_enable | 布尔 | ACE数据上报开关 |
| acereportdata2_enable | 布尔 | ACE数据上报2开关 |
| acereportdata4_enable | 布尔 | ACE数据上报4开关 |

### AB测试

| 字段 | 类型 | 说明 |
|------|------|------|
| abver | 数字 | AB测试版本号 |
| abidx | 字符串 | AB测试索引标识 |
| abdiff | 字符串 | AB测试差异标识 |

### 性能与日志

| 字段 | 类型 | 说明 |
|------|------|------|
| log_sampling | 数字 | 日志采样率（百分比） |
| perf_random | 数字 | 性能数据采样率（百分比） |
| ping_timeout | 数字 | 网络测速超时时间（毫秒） |
| timestamp_diff | 数字 | 客户端与服务器时间戳允许的最大偏差（秒） |

### 更新相关

| 字段 | 类型 | 说明 |
|------|------|------|
| update_url | 字符串 | 游戏更新页面地址 |
| update_store_url | 字符串 | 应用商店更新跳转链接 |
| hotupdate | 数组 | 热更新配置列表 |
| hotupdate[].client_version | 数组 | 适用客户端版本范围 |
| hotupdate[].abver | 数字 | 热更新AB版本号 |
| hotupdate[].abidx | 字符串 | 热更新AB索引 |
| hotupdate[].abdiff | 字符串 | 热更新AB差异标识 |

### 其他配置

| 字段 | 类型 | 说明 |
|------|------|------|
| maintain_info | 字符串 | 停服维护公告内容 |
| error | 字符串 | 错误信息占位符 |
| lc_appid | 字符串 | LeanCloud应用ID |
| lc_appkey | 字符串 | LeanCloud应用密钥 |
| agreement_ver | 字符串 | 用户协议版本号 |
| privacy_policy_ver | 字符串 | 隐私政策版本号 |
| unets | 对象 | UNET网络配置 |
| gateway_micro_info | 对象 | 微服务网关配置 |
| gateway_micro_info.enable | 字符串 | 微服务网关开关 |
| gateway_micro_info.connect_addr | 字符串 | 微服务网关连接地址 |
| gateway_micro_info.backend_addr | 字符串 | 微服务后端地址 |
| gateway_micro_info.service_name_list | 字符串 | 微服务名称列表 |
| ios_shenhe_ver | 数字 | iOS审核版本号 |
| strategy-station-url | 字符串 | 攻略站地址 |
| voice_room_type | 数字 | 语音房间类型 |

---

## 免责声明

本项目仅提供配置文件模板用于学习与参考，配置文件中的字段与结构可能随游戏版本更新而变化，请以实际下发为准。

---
