# 财税政策库

戴总专属财税政策库，由 `policy-scraper.skill` 自动维护。

## 目录结构

```
政策库/
├── 综合/               # 通用财税政策
│   ├── 财政部/         # 财政部发布 (96 条)
│   ├── 税务总局/       # 国家税务总局发布 (35 条)
│   └── 其他部门/       # 其他部委联合发文 (2 条)
├── 代账行业/           # 代理记账行业相关 (10 条 + README)
├── 美业/              # 美容美发医美行业 (README + 行业指引)
├── _日报索引/          # 每日同步索引快照
└── _bulk_log_*.json   # 批量爬取日志
```

## 当前规模

- **时间范围**: 2024-12-30 ~ 2026-05-26
- **政策总数**: 143 条（去重后）
- **最后更新**: 2026-05-26

## 行业子库

- [代账行业说明](代账行业/README.md)
- [美业说明](美业/README.md)

## 数据来源

| 部门 | 入口 | 抓取方式 |
|------|------|---------|
| 财政部 | http://www.mof.gov.cn/zhengwuxinxi/zhengcefabu/ | HTML 列表分页 |
| 国家税务总局 | https://fgk.chinatax.gov.cn/zcfgk/c100012/listflfg.html | JSON API |

## 维护工具

爬虫位于 `~/.openclaw/workspace-weixin-daizong/skills/policy-scraper/`：

```bash
# 增量爬取（每日）
python3 scripts/scraper.py

# 批量爬取（指定日期范围）
python3 scripts/scraper_bulk.py --start 2024-12-30 --end 2026-05-26

# 生成日报
python3 scripts/read_policies.py --format feishu
```

## Git 仓库

远程: https://github.com/jmgim6276-arch/obsidian-finance.dai

---

_由 policy-scraper.skill 自动维护_
