# Next.js × Biome

Biome をインストールした Next.js プロジェクトの雛形

## 環境

- TypeScript 5.3.3
- Next.js 14.1.0
- Biome 1.5.3

## Biome

- 設定ファイル `./biome.json`

- 使い方

  ```bash
  # Formatter ルールを適用
  npx @biomejs/biome format --write <files or directory>

  # Linterルールを適用
  npx @biomejs/biome lint --apply <files or directory>

  # 上記を一括で実行
  npx @biomejs/biome check --apply <files or directory>
  ```

- 参考

  - [Biome の設定について](https://biomejs.dev/ja/reference/configuration/)
  - [Formatter のルールについて](https://biomejs.dev/ja/reference/configuration/#formatter)
  - [Linter のルールについて](https://biomejs.dev/ja/linter/rules/)
  - [import 文のソートについて](https://biomejs.dev/analyzer/#imports-sorting)

## VSCode の設定

1.  拡張機能 [Biome](https://marketplace.visualstudio.com/items?itemName=biomejs.biome) をインストールする
2.  settings.json に Biome の設定を追加する

    ```json
    "editor.codeActionsOnSave": {
        // 保存時にLinterを適用
        "quickfix.biome": true,
        // 保存時にインポートの並び替えを適用
        "source.organizeImports.biome": true
    },
    // 保存時に Formatter を適用
    "editor.formatOnSave": true,
    // デフォルトの Formatter は prettier を指定
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    // js, jsx, ts, tsx, json ファイルは Biome を指定（左記以外は prettier）
    "[javascript]": {
    "editor.defaultFormatter": "biomejs.biome"
    },
    "[javascriptreact]": {
    "editor.defaultFormatter": "biomejs.biome"
    },
    "[typescript]": {
    "editor.defaultFormatter": "biomejs.biome"
    },
    "[typescriptreact]": {
    "editor.defaultFormatter": "biomejs.biome"
    },
    "[json]": {
    "editor.defaultFormatter": "biomejs.biome"
    },
    ```
