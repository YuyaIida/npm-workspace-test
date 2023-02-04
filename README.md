# npm workspace

# npm workspaceとは

あるリポジトリ内に複数プロジェクトが存在する場合、ルートプロジェクト内に別プロジェクトを作る際に親ディレクトリ内のnode_modulesを参照できるようにしたりするもの

例えば、親ディレクトリ・子ディレクトリにjestを入れる場合、親ディレクトリだけにjestを入れれば良い等のメリットがある

## 構成

```jsx
.
├── node_modules
│   ├── npm-workspace-test-child
│   │   ├── index.js
│   │   └── package.json
├── npm-workspace-test-child
│   ├── index.js
│   └── package.json
├── package-lock.json
└── package.json
```

## ユースケース

---

### 親ディレクトリでも子ディレクトリでも使うnpm libraryを追加する際

```jsx
npm install --save jest
```

### 子ディレクトリのみで使用する場合

```jsx
npm install jest -w npm-workspace-test-child
```

上記コマンドを叩くとnode_modules/npm-workspace-test-child/のpackage.jsonが更新され、jestがnode_modules内に追加される