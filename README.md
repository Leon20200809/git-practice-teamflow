## チーム開発練習 リポジトリ git-practice-teamflow

### 1．mainブランチの保護ルール設定

- `Settings` → `Branches（ブランチ）` → `ルールを追加`
- 対象ブランチ：`main`
- チェック項目：
  - ✅ プルリクエストの作成を要求する
  - ✅ ブランチ削除を防止する（Restrict deletions）
  - ✅ 強制pushを禁止する（Block force pushes）
  - ✅ 管理者にもルールを適用する
- Enforcement status：**Active**

---

### 2. featureブランチを切る
```bash
git checkout -b feature/add-readme-note
```

- 新しいブランチを作成する (-b オプション)
- 作成した新しいブランチに切り替える (通常の git checkout の機能)

feature/: これはプレフィックスで、「これから追加する変更が新しい機能（feature）に関するものである」ことを示します。これにより、ブランチの種類が一目でわかります。

add-readme-note: これはブランチの具体的な目的や内容を表しています。この場合、「READMEファイルにメモを追加する」という作業を行うブランチであることが示唆されます。

```bash
git add -A
git commit -m "docs: READMEにPR練習用の追記"
git push origin feature/add-readme-note
```

- feature/変更内容 ブランチに移動してコミットしてpush！！

### 3. GitHubで「Compare & pull request」ボタンをクリック
- PRタイトル：docs: READMEにPR練習用の追記
- 説明欄に軽く書けばOK 例：「GitHub Flowの練習のため、READMEに1行追記しました。」
- 

### 4. プルリクエストが承認されたらmainブランチにマージする。
- Git上でfeatureブランチ削除。ローカルの同じブランチも"手動"で削除
- mainブランチをpullして、mainブランチに移動して作業再開！