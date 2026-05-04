# redhat-training-schedule

Red Hat が提供する技術トレーニングの予定を、**CSV** または **HTML** で閲覧するためのデータを置いています。

## このリポジトリに含まれるもの

| パス | 内容 |
|------|------|
| [`docs/data.csv`](docs/data.csv) | クラス予定などの表形式データ（CSV） |
| [`docs/holidays.csv`](docs/holidays.csv) | 日本の国民の祝日データ（CSV） |
| [`docs/index.html`](https://lab8010.github.io/redhat-training-schedule/) | 上記 CSV を読み込んで表示する静的ページ（HTML） |

## データソースについて

### トレーニングスケジュール (`data.csv`)

Red Hat 公式のトレーニングクラス予定データです。

- **更新頻度**: 原則として日次（午前中に更新予定）
- **データ項目**: 開催日、コース名、SKU、ステータスなど

### 日本の祝日 (`holidays.csv`)

[内閣府が公開している国民の祝日データ](https://www8.cao.go.jp/chosei/shukujitsu/gaiyou.html)を自動取得・変換したものです。

- **更新頻度**: 毎週日曜 0:00 (UTC) に自動更新
- **更新方法**: GitHub Actions (`.github/workflows/update-holidays.yml`)
- **エンコーディング**: UTF-8（元データの Shift_JIS から自動変換）

Grafana などの可視化ツールで、トレーニングスケジュールと祝日を併せて表示することで、受講計画時に祝日を考慮できます。

## クラスステータスについて

掲載されているクラスの **ステータスは日々変わることがあります**。  
受講の計画をすでにお持ちの場合は、状況が変わる前に **お早めの受講登録** をお願いします。

## Red Hat トレーニング規定

受講・キャンセル・認定試験などの公式な取り決めは、Red Hat のサイトをご確認ください。

- [Red Hat トレーニングポリシー（日本語）](https://www.redhat.com/ja/about/red-hat-training-policies)

## このサイトについて

- 公開・管理は **Lab8010** が行っています。Red Hat の公式サイトではなく、Red Hat 認定インストラクターによるボランティア運用です。
- `docs/data.csv` および `docs/holidays.csv` は各自のサイトへの掲載などに活用できます。条件はリポジトリルートの [**MIT License**](LICENSE) に従ってください。
  - 祝日データの出典: 内閣府「[国民の祝日について](https://www8.cao.go.jp/chosei/shukujitsu/gaiyou.html)」

## GitHub Pages で見る場合

リポジトリの **Settings → Pages** でソースを **`/docs`**（ブランチは通常 `main`）に設定すると、次のような URL で HTML 版を公開できます（実際のユーザー名・リポジトリ名に読み替えてください）。

`https://<ユーザー名>.github.io/<リポジトリ名>/`
