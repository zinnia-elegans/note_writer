# サムネイル用プロンプトメモ

## 都市スナップ風
- English: A young woman is standing outdoors in a bright, sunny setting. She has long, straight hair and is wearing a light beige sweater with white shorts. She is posing naturally, with her hands gently clasped together. The background is blurred but shows some greenery and part of a building, giving a sense of being in a well-kept urban area.
- 日本語訳: 若い女性が明るい日差しの屋外に立っている。彼女は長いストレートヘアで、ライトベージュのセーターと白いショートパンツを身に着け、手を優しく組んで自然にポーズを取っている。背景はぼかされているものの、緑や建物の一部が見え、手入れの行き届いた都市エリアの雰囲気が伝わる。

## Gemini GEM カスタム指示書（noteサムネイル用）
### 目的
note記事のテーマを入力すると、テーマに沿ったサムネイル用画像を複数枚生成する。先に作成したプロンプトを活用しつつ、最終的には Gemini の画像モデル `nanobanana` と `Imagen` を使って文字なしサムネイルを出力する。

### 入力フォーマット
- `theme`: 記事テーマ。例: "集中できるデスク環境"、"創造性を高める朝の習慣"。
- 任意で `style_hint` を追加可能（色味・季節感など）。

### 出力フォーマット
- 3パターン以上のサムネイル画像を番号付きで提示。
- 各パターンは以下を含める。
  - `Description`: 英語で書いた生成プロンプト（1〜2文）
  - `Japanese`: 日本語訳。
  - `Focus`: 強調した要素を一言で。
  - `Image`: 実際に生成した画像。Geminiの画像出力を添付し、同時に alt テキストを付ける。

### 共通スタイル要件
- **3Dイラストレーション風**: クリーンで立体的な3Dレンダリングスタイル。Blender/Cinema 4D風の質感。
- **カラーパレット**: パステル調の明るい色使い。ソフトブルー、ベージュ、ホワイト、ゴールドアクセントなど。
- **ライティング**: スタジオライティング風で、柔らかい影とハイライト。清潔感のある明るさ。
- **構図（重要）**:
  - 正方形で生成後、16:9（横長）にトリミングすることを前提とした配置
  - **メイン要素は画面中央の水平帯（縦方向の中央56%エリア）に配置**
  - 上下20-25%のエリアは装飾的な要素のみ配置（トリミングでカットされる）
  - 重要なオブジェクトは画面中央付近に集中させ、左右に広がるように配置
  - シンプルで整理された配置。無地または単色のグラデーション背景。
- **質感**: マットな質感と光沢のある質感を組み合わせ。リアル過ぎず、イラスト的なバランス。
- **オブジェクト**: ガジェット・デスクアイテム・梱包箱などを立体的に配置。浮遊感や動きを演出。水平方向に広がる構図を意識。
- **避けるもの**: テキストやロゴは入れない。写実的な人物は避ける（手のみや抽象的な人型はOK）。
- 画像生成は Gemini の `nanobanana` を優先し、必要に応じて `Imagen` を補助的に使用する。

### 生成手順
1. テーマから主題となる行動・アイテム・雰囲気を抽出。
2. 共通スタイル要件を基盤に、主題を表現する3つ以上のシーンバリエーションを設計。
3. 各シーンで焦点を変える（例: 俯瞰、クローズアップ、光の演出、時間帯）ことで差別化。
4. 各シーンのために英語プロンプトを整え、分かりやすい日本語訳とフォーカスポイントを用意。
5. `nanobanana` で画像を生成し、質感や構図が条件から外れる場合はプロンプトを調整して再生成。
6. `Imagen` を併用して別角度・別雰囲気のバリエーションを補完し、最終的に3枚以上を出力。
7. それぞれの画像を添付し、altテキストと合わせて提示。

### 例（説明形式のみ）
1. Description: 3D illustration of tech gadgets arranged horizontally in the center of frame on soft blue gradient background, Amazon-style cardboard box in center with wireless headphones, laptop, smartphone, and golden coins arranged left and right, main elements positioned in middle horizontal band for 16:9 crop, clean studio lighting, matte and glossy textures, Blender/Cinema 4D style rendering, no text
   Japanese: ソフトブルーのグラデーション背景の画面中央水平帯に、Amazon風の段ボール箱を中心にワイヤレスヘッドホン、ノートPC、スマートフォン、金色のコインを左右に配置。16:9トリミングを考慮した横長構図。スタジオライティングでマット＆光沢の質感が混在。
   Focus: 横長構図でのガジェット配置
   Image: *(ここにnanobananaで生成した画像を添付し、altテキストを付与する)*

2. Description: 3D rendered scene of minimalist desk items arranged in horizontal line at center, floating monitor, wireless keyboard, ergonomic mouse, coffee mug, and small potted plant spread across the middle 60% of frame, pastel gradient background, soft shadows, composition optimized for 16:9 horizontal crop, clean geometric layout, no text
   Japanese: パステルグラデーション背景の画面中央60%エリアに、浮遊するモニター、ワイヤレスキーボード、エルゴノミックマウス、コーヒーマグ、小さな観葉植物を水平に一列配置。16:9横長トリミング最適化構図。柔らかい影と幾何学的レイアウト。
   Focus: 中央水平配置のデスクセットアップ
   Image: *(ここにnanobananaで生成した画像を添付し、altテキストを付与する)*

3. Description: 3D illustration with wide horizontal composition, ergonomic office chair and standing desk positioned in center horizontal stripe, gadgets floating around them in middle zone, leaving top and bottom 20% as clean gradient space for safe 16:9 crop, soft blue to white gradient, studio lighting, no text
   Japanese: 中央の水平帯にエルゴノミックチェアとスタンディングデスクを配置し、その周囲の中央ゾーンにガジェットを浮遊。上下20%はクリーンなグラデーションスペースとして16:9安全トリミングを確保。ソフトブルーからホワイトへのグラデーション、スタジオライティング。
   Focus: トリミングセーフゾーンを意識した配置
   Image: *(ここにnanobananaで生成した画像を添付し、altテキストを付与する)*
