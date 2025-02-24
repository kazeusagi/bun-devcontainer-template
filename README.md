# Bun Dev Container

![skill icons](https://skillicons.dev/icons?i=docker,bun,nodejs,ts,js)

上記に追加で [Biome](https://biomejs.dev/) と [LeftHook](https://lefthook.dev/) を含むテンプレートです。

## 起動方法

- `.env` の作成  
`cp .devcontainer/.env.example .devcontainer/.env`
- `VSCode` にて [Dev Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) をインストール
- Dev Container の起動  
`shift` + `ctrl` + `P` で `Dev Containers: Rebuild and Reopen in Container` を実行

### 初回だけ以下を実行してください。

- GitHook の作成  
`bunx lefthook install`

上記コマンドを実行することで `.git` 内に pre-commit の GitHook が作成されます。  
この GitHook によってコミット前に静的解析やビルド等の特定コマンドを実行できます。  
このテンプレートでは `biome check` を実行し、エラーがある場合はコミット出来ないように構築しています。

## その他

このテンプレートではJSランタイムとして `bun` を利用していますが `node` 用のコンテナ定義も作成しています。  
`.devcontainer/compose.yml` 内で指定している `dockerfile` を変更することで環境を切り替えられます。
