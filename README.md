# 大数据算法与数学基础

本仓库用于管理《大数据算法与数学基础》教材的 LaTeX 源码、图片素材和参考文献。

最后更新：2026-04-30

## 当前状态

- 主文件：`elegantbook-cn.tex`
- 编译方式：XeLaTeX + Biber，推荐使用 `latexmk`
- 编译产物：默认输出到 `build/`
- 参考文献：`bib/reference.bib`、`bib/main.bib`
- 当前 PDF：编译后生成 `build/elegantbook-cn.pdf`

## 目录结构

```text
.
├── elegantbook-cn.tex        # 教材主文件
├── elegantbook.cls           # ElegantBook 类文件，本项目仍依赖它
├── symbol.sty                # 本项目自定义符号宏包
├── bib/                      # 参考文献数据库
├── chapters/                 # 已拆分或待拆分的章节文件
├── figure/                   # 主教材图片素材
├── images/                   # 讲义章节图片素材
├── archive/                  # 原模板说明、模板许可证等归档材料
├── build/                    # 本地编译输出，已被 .gitignore 忽略
├── .vscode/                  # VS Code LaTeX Workshop 配置
├── .latexmkrc                # latexmk 默认编译配置
├── .gitignore                # Git 忽略规则
└── LICENSE                   # 当前 GitHub 仓库许可证
```

## 编译

推荐在项目根目录运行：

```powershell
latexmk elegantbook-cn.tex
```

也可以显式指定 XeLaTeX：

```powershell
latexmk -xelatex -interaction=nonstopmode -file-line-error elegantbook-cn.tex
```

编译成功后，PDF 位于：

```text
build/elegantbook-cn.pdf
```

清理编译产物：

```powershell
latexmk -C elegantbook-cn.tex
```

## VS Code

建议安装扩展：

- LaTeX Workshop：`james-yu.latex-workshop`

本仓库已配置 `.vscode/settings.json`，保存主文件时会使用 `latexmk-xelatex` 编译，并将中间文件放到 `build/`。

## 许可证

根目录 `LICENSE` 是当前 GitHub 仓库许可证。ElegantBook 模板原始 LPPL 声明已归档到 `archive/elegantbook-template/ElegantBook-LPPL-License.txt`。

## GitHub 管理流程

远程仓库：

```text
https://github.com/MoGuanlin/Big-Data-Textbook
```

首次提交并推送：

```powershell
git config user.name "Your Name"
git config user.email "your-email@example.com"
git status
git add .
git commit -m "Initialize textbook project"
git push -u origin main
```

之后的日常流程：

```powershell
git pull
git status
git add .
git commit -m "Describe your change"
git push
```

建议提交粒度：

- 修改正文或公式：单独提交
- 添加图片或参考文献：单独提交
- 调整编译配置、README、目录结构：单独提交

不建议提交 `build/` 中的文件。需要发布 PDF 时，可以在 GitHub Releases 中上传 `build/elegantbook-cn.pdf`。
