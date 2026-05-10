# 综合私有IPIV播放源

融合两位公众号作者的技术方案：

| 作者 | 公众号 | 核心技术 |
|------|--------|---------|
| **医工学习日志** | cqmedical | migu_video M3U生成、PHP测速优选(migu_ip.php) |
| **网络志** | net_notes | IPTV架构、M3U/EPG标准格式、部署方案 |

## 文件说明

| 文件 | 说明 |
|------|------|
| `网络志×医工日志_综合私有源.m3u` | **358条频道** — 央视/卫视/地方/体育/今日直播/回放 |
| `playback.xml` | EPG电子节目单（119频道，3621条节目信息） |
| `interface.txt` | 原始Migu源列表（453条含代理地址） |

## 使用方法

```
# 综合私有源（358条公网直链）
https://raw.githubusercontent.com/zhmzjj310144/migu-sports/main/%E7%BD%91%E7%BB%9C%E5%BF%97%C3%97%E5%8C%BB%E5%B7%A5%E6%97%A5%E5%BF%97_%E7%BB%BC%E5%90%88%E7%A7%81%E6%9C%89%E6%BA%90.m3u

# EPG节目单
https://raw.githubusercontent.com/zhmzjj310144/migu-sports/main/playback.xml
```

## 频道结构

- 📺 央视（28条）：CCTV1~CCTV17超清
- 📡 卫视（17条）：湖南/浙江/江苏/东方/北京/深圳等
- 📍 地方（30条）：各省市地方台
- ⚽ 今日直播：当天体育赛事
- 🔄 昨日回放：前一天全场回放
- 📅 明日预告：明天赛事预告

## 技术栈

- 源生成：migu_video → Migu CDN公网直链
- 格式标准：网络志 IPTV架构规范
- M3U头：x-tvg-url EPG + catchup回看
- 自动更新：每日8:00 cron job
