# 環境構築

typescript と next をインストールします。

```bash
npx create-next-app --example with-typescript with-typescript-app
```

実際に動かして確認するときに使います。

```bash
yarn dev
```

## 不要なファイルの削除

- components, interfaces, utils ディレクトリを削除します。
- pages 直下の IndexPage 関数のあるファイル以外を削除します。
