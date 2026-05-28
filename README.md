# vscode-plugin-config-demo

配置菜单外部配置文件示例。

## 格式：JSON

```json
{
  "version": 1,
  "items": [
    {
      "id": "bin",
      "description": "通用工具",
      "repoType": "git",
      "path": "~/.cvte-plugin/bin",
      "codeInit": "git@gitlab.gz.cvte.cn:syssw_cbb/tools/cvte-plugin/bin.git"
    },
    {
      "id": "skills",
      "description": "AI技能",
      "repoType": "repo",
      "path": "~/.cvte-plugin/ai/skills",
      "codeInit": "repo init -u git@gitlab.gz.cvte.cn:syssw_cbb/tools/ai/skills-manifest.git -b default -m dss-sw.xml"
    }
  ]
}
```

## 字段说明

| 字段 | 必填 | 说明 |
|------|------|------|
| `id` | 是 | 行唯一标识 |
| `description` | 是 | 表格「描述」列 |
| `repoType` | 是 | `git` 或 `repo` |
| `path` | 是 | 本地路径，支持 `~` |
| `codeInit` | 否 | 类型后可编辑：`git` 为 clone 地址；`repo` 为 `repo init` 命令 |

`repo` 类型更新时，扩展固定使用内置脚本 `~/.cvte-plugin/bin/repo/jks_clean_release.sh sync`，无需在 JSON 中配置 `updateScript`。
