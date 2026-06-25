# setup-hsp

指定バージョンのHSP3を取得・展開し、インストール先パスを出力するcomposite action(Gitea Actions / GitHub Actions互換)。`actions/cache`でバージョンごとにキャッシュする。

**Inputs**

| 名前 | 必須 | 説明 |
|---|---|---|
| `hsp-version` | ✓ | 取得するHSP3のバージョン(例: `"3.6"`, `"3.7"`) |

**Outputs**

| 名前 | 説明 |
|---|---|
| `hsp-home` | 展開済みHSP3インストールへのパス |

```yaml
- name: Setup HSP
  id: setup-sdk
  uses: kijuky/setup-hsp@<commit-sha>
  with:
    hsp-version: "3.6"
```

## ピン留め規約

サプライチェーン攻撃対策として、このアクションを参照する側は**タグではなくコミットSHAで固定**すること(`actions/checkout`等の外部アクションと同じ規約)。バージョンの目印として、SHAの末尾にタグ名やバージョンをコメントで残す。

```yaml
uses: kijuky/setup-hsp@1234567890abcdef1234567890abcdef12345678 # v1.0.0
```
