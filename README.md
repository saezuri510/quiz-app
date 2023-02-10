# 環境構築

## Next の導入

1. typescript と next をインストールします。

```bash
npx create-next-app --example with-typescript "好きなプロジェクト名"
```

2. next のバージョン指定をします。

```bash
yarn remove next
yarn add next@^12
```

---

## 不要なファイルの削除

- components, interfaces, utils ディレクトリを削除します。
- pages 直下の IndexPage 関数のあるファイル以外を削除します。

---

## Tailwind CSS の導入

1. tailwindcss, postcss, autoprefixer のインストールと tailwind.config.js, postcss.config.js を作成します。

```bash
yarn add -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

2. css のあるファイルを指定するため tailwind.config.js を編集します。

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./pages/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

3. styles フォルダを作成します<br>
   そのフォルダ内に globals.css を作成し、編集します。

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. pages フォルダ内に\_app.tsx を作成し、編集します。

```tsx
import "../styles/globals.css";
import { AppProps } from "next/app";

function MyApp({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}

export default MyApp;
```

5. pages/index.tsx を編集し、確認します。

```tsx
const IndexPage = () => (
  <div>
    <div className="text-red-500">Hello world</div>
  </div>
);

export default IndexPage;
```

```bash
yarn dev
```
