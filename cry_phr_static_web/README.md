# Cry PHR Domain Database 静态网页

这个项目是一个可直接部署的静态网页数据库。它只需要两个核心文件：

- `index.html`
- `cry_phr_database.csv`

网页会自动读取同目录下的 `cry_phr_database.csv`，提供搜索、筛选、分页、PDB / AlphaFold 链接。

## 你需要替换的文件

压缩包里的 `cry_phr_database.csv` 是示例数据。请用你自己的最终 CSV 替换它：

```bash
cp /你的路径/cry_phr_database_ready.csv cry_phr_database.csv
```

CSV 推荐包含这些列：

```text
record_id
record_id_raw
accession_guess
accession_guess_raw
uniprot_accession_clean
uniprot_accession
source_tag
cry_group
pdb_id
pdb_count
organism
phr_length_aa
description
phr_sequence
aligned_phr_sequence
```

最关键的是：

- `uniprot_accession_clean`：干净 UniProt accession，用于 AlphaFold 链接。
- `pdb_id`：PDB 编号，有多个时用 `;` 分隔，例如 `1U3D;4DJA`。
- `phr_sequence`：PHR 域序列。

## 本地预览

不要直接双击 `index.html`，请用本地服务器打开：

```bash
cd cry_phr_static_web
python3 -m http.server 8000
```

浏览器打开：

```text
http://localhost:8000
```

## 分享给别人

把整个文件夹部署到 GitHub Pages、Netlify 或 Cloudflare Pages。部署后把生成的网址发给别人即可。

注意：静态网页会公开暴露 CSV 文件中的全部序列和注释。如果数据不能公开，请不要部署到公开站点。
