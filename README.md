# FFXI_server

FFXI エミュレートサーバーの構築、ソースコード (C++) の修正、およびデータベース (SQL) の管理。

## 主な機能とロジック
### orchestrator.py
- **概要**: -*- coding: utf-8 -*-
- **主要要素**: `now_iso, ensure_dir, read_text, write_text, read_json`
- **特徴**: コマンドライン引数に対応

### announce.py
- **概要**: announce.py
- **主要要素**: `print_help, encode_varint, build_chat_packet`

### bom_checker.py
- **概要**: This script will detect and replace the byte-order-mark for a file.
- **主要要素**: `detect_bom, detect_files, main`

### dbtool.py
- **概要**: Internal Deps
- **主要要素**: `preflight_exit, from_dbtool_path, from_server_path, print_red, print_green`

### generate_changelog.py
- **概要**: py -m pip install requests
- **主要要素**: `days_since_last_run, is_real_name, remove_real_names`

### create_symlink.bat
- **概要**: スクリプト

### initialize_project.bat
- **概要**: スクリプト

### fuzzer.cpp
- **概要**: include <cstddef>

### application.cpp
- **概要**: include "application.h

### arguments.cpp
- **概要**: include "arguments.h
- **特徴**: コマンドライン引数に対応

### blowfish.cpp
- **概要**: include "common/blowfish.h

### console_service.cpp
- **概要**: include "console_service.h

## 技術スタック
- **主要言語/ツール**: Python, Batch, C++/PlatformIO, Excel/CSV (C++, Lua, SQL (MariaDB), Docker, CMake, ZeroMQ。)

## ディレクトリ構造
```text
- .clang-format
- .clang-tidy
- .devcontainer/
  - devcontainer.json
- .dockerignore
- .doxygen
- .editorconfig
- .gitattributes
- .github/
  - ISSUE_TEMPLATE/
    - bug_report.md
    - feature_request.md
  - codeql/
    - codeql-config.yml
  - pull_request_template.md
  - workflows/
    - changelog.yml
    - check_template.yml
    - ci.yml
    - codeql_analysis.yml
... (以下略)
```

## 現在のステータス
- **フェーズ**: complete
- **次ステップ**: 各プロジェクトへコピーする際は、PROJECT.md の初期化ルールに従って state を初期化し、初回は --dry-run で確認する

---
詳細な情報については [PROJECT.md](PROJECT.md) を参照してください。