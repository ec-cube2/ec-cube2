# EC-CUBE2 Composer Package (Unofficial)

https://github.com/EC-CUBE/ec-cube2 から Composer Package を作成しています。

```
$ composer create-project ec-cube2/ec-cube2:<version> <directory>
```

## バージョン

| バージョン | 内容 |
|---|---|
| 2.11.0〜2.17.1 | 本家のタグ (`eccube-<version>`) のソースをそのまま配布します。`composer.json` が本家のソースを指しているだけのタグです |
| 2.13.5.1 / 2.17.2.1 / 2.25.0.1 など (4 桁目あり) | 本家のタグにパッチを当てた版です。下記を参照してください |

## パッチ版

本家のタグをもとに、インストール手順 (`eccube_install.sh`) と配布用の `composer.json` にだけパッチを当てています。EC-CUBE の動作は本家と同じです。

| バージョン | ブランチ | もとにした本家のタグ |
|---|---|---|
| 2.13.5.1 | [`patched/2.13`](https://github.com/ec-cube2/ec-cube2/tree/patched/2.13) | `eccube-2.13.5-p2` |
| 2.17.2.1 | [`patched/2.17`](https://github.com/ec-cube2/ec-cube2/tree/patched/2.17) | `eccube-2.17.2-p2` |
| 2.25.0.1 | [`patched/2.25`](https://github.com/ec-cube2/ec-cube2/tree/patched/2.25) | `eccube-2.25.0` |

- 本家との差分はブランチのコミットで確認できます (例: `git log -p eccube-2.13.5-p2..patched/2.13`)。
- 4 桁目は、同じ本家のタグにパッチを足すたびに 1 つ増やします。

### 主なパッチ

- 2.13: `eccube_install.sh` で、別ホストの DB にインストールできるようにします。`DBSERVER` / `DBPORT` を指定でき、PostgreSQL のパスワードは `PGPASSWORD` で渡します。ほかに、MySQL 5.7 以降の `default_storage_engine` と、MySQL の DB を utf8 で作る修正も入っています (EC-CUBE 2.17 で直された箇所と同じ内容です)。
- 2.17 / 2.25: パッケージ名を `ec-cube2/ec-cube2` にします。

経緯は [#1](https://github.com/ec-cube2/ec-cube2/issues/1) を参照してください。
