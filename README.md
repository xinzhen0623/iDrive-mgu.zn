# iDrive 7 中文小程序源码

BMW iDrive 7 车机自定义小程序的简体中文版源码，可直接用于构建、打包并推送到车机。

## 内容

- `apps/` — 15 个应用源码（每个含 `app.json` + JS + 图标）
- `kit/` — 构建工具链（`build.py`、`make_kit.py`、汉化词典、字体等）
- `docs/` — 相关文档

## 应用清单

| 应用 | 名称 | 版本 | 汉化 |
| --- | --- | --- | --- |
| `ambient_config` | 氛围灯配置 | 2.5.0-zh.cn.4 | 是 |
| `brake_test` | 制动测试 | 1.5.20-zh.cn.4 | 是 |
| `car_vitals` | M 车辆仪表 | 2.27.3-zh.cn.4 | 是 |
| `doom` | 毁灭战士 | 1.7.20-zh.cn.4 | 是 |
| `draggy` | 弹射模式 | 2.5.20-zh.cn.4 | 是 |
| `dtc_scanner` | 故障检测 | 2.9.7-zh.cn.4 | 是 |
| `dyno` | 虚拟马力机 | 1.6.1-zh.cn.4 | 是 |
| `edrive` | EDrive助手 | 2.9.2-zh.cn.4 | 是 |
| `gforce` | G 值仪表 | 1.6.21-zh.cn.4 | 是 |
| `live_adjustments` | 发动机配置 | 0.9.6-zh.cn.4 | 是 |
| `live_data` | 实时数据 | 1.0.12-zh.cn.4 | 是 |
| `redline` | 换挡转速 | 2.0.41-zh.cn.4 | 是 |
| `service` | 保养信息 | 1.6.1-zh.cn.4 | 是 |
| `warmup` | 暖机助手 | 1.8.1-zh.cn.4 | 是 |
| `zf8hp` | 变速箱配置 | 1.5.6-zh.cn.4 | 是 |

共 **15** 个应用，其中 **15** 个已汉化。

## 构建

需要 Node 18+ 和 Python 3.10+，以及从车机提取的 `oap-sdk`（不在本仓库内）。

```bash
# 构建单个应用（中文）
python kit/tools/build.py --language zh-CN brake_test

# 构建全部并打包
python kit/tools/make_kit.py --language zh-CN
```

产物：`dist/mgu-custom-apps-zh-CN.tar.gz`，推到车机后由车机端 Store 安装。

## 汉化

翻译词典在 `kit/runtime/locales/zh-CN.json`，键为英文原文，值为中文译文。

`build.py --language zh-CN` 会用它逐字段替换 `app.json` 里的显示文本。

## 说明

- `oap-sdk` 需从自己的车机提取，不随源码分发
- 构建产物、备份目录已在 `.gitignore` 中排除
- 本仓库仅包含应用源码与工具链，不含任何车机固件
