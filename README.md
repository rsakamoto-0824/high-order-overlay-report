# Shot高次重ね合わせ補正 技術レポート

- [main.tex](main.tex)：表紙、目次、本文、参考文献をまとめた単一の原稿。
- [main.pdf](main.pdf)：LuaLaTeXで生成した確認用PDF。
- このREADME：コンパイル方法と引用元の対応。

## Overleafでのコンパイル

1. `main.tex`だけをOverleafへアップロードします。
2. Main documentを`main.tex`、Compilerを**LuaLaTeX**に設定します。
3. Recompileを実行します。

外部画像、BibTeX、Biber、独自フォントのアップロードは不要です。著者名は冒頭の`\AuthorName`を変更してください。

ローカルでは`lualatex main.tex`を2回以上実行し、目次と参照を確定します。

## 原稿の状態

日本語の技術レポート原稿です。実験は未実施で、1000通りの合成Shotによる実験計画、固定ハイパーパラメータ、結果記入欄を含みます。実験結果や改善量を仮の数値で埋めていません。

確定が必要な項目は著者名、実験条件の採否、実験結果、結果に基づく結論、謝辞です。希望された結論3項目は事前仮説として記述しています。

ASMLは公開論文の15項モデル、Nikonは公開特許の6次20項モデルを比較対象としています。両者は次数・表現空間が異なり、現行装置の性能比較ではありません。正規化座標の係数をそのまま実機へ入力することは想定していません。

## 端末内の引用文献

以下はすべて、既存の公開論文PDFを読み取って引用しています。原本の変更・移動・外部アップロードは行っていません。

原本は作成者の端末内で管理しています。端末固有の保存先はリポジトリに含めていません。

| 文献番号 | ファイル名 | 本稿で参照した箇所 |
|---|---|---|
| [1] | `2026_KLA_Optical overlay metrology challenges in next-gen semiconductor nodes.pdf` | pp.1–3、微細化・GAA・裏面電源・計測とモデル化 |
| [2] | `2026_KLA_Overlay metrology performance specification challenge entering the sub-nanometer overlay era.pdf` | pp.1–2、計測誤差の伝播と測定配置 |
| [3] | `2020_STMicroelectronics_Run to run and model variability of overlay high order process corrections for mean intrafield signatures.pdf` | p.2 Formula 1、使用する15項、pp.7–9の変動要因 |
| [4] | `2025_KLA_Cherry-picking automated model term selection for precise overlay and CD process control.pdf` | pp.2–3、Lassoで項選択後に線形回帰で再推定 |
| [5] | `2016_SK hynix_Application of Overlay Modeling and Control with Zernike Polynomials in an HVM Environment.pdf` | pp.1–2、ウェハ成分のZernikeとShot内XY iHOPCの区別 |
| [7] | `2009_Nanya_Using Intra-Field High Order Correction to Achieve Overlay Requirement beyond Sub-40nm Node.pdf` | p.3 Fig.2、ASMLの補正可能項の色分けを含む数式 |

## 追加の公開一次資料

- [6] [Magklaras et al., Mathematics 2024, 12, 3179](https://doi.org/10.3390/math12203179)。出版社の公開PDFで確認。pp.6–8の条件別結果に基づき、一律なRidge優位とは記述していません。
- [8] [Nikon JP2010186918A](https://patents.google.com/patent/JP2010186918A/ja)。公開PDF p.15、段落[0070]–[0072]、式(3)(4)。
- [9] [NIST：VIFの定義](https://www.itl.nist.gov/div898/software/dataplot/refman2/auxillar/vif.htm)。
- [10] [Huberの原論文](https://doi.org/10.1214/aoms/1177703732)。
- [11] [Ridgeの原論文](https://doi.org/10.1080/00401706.1970.10488634)。
- [12] [Lassoの原論文](https://doi.org/10.1111/j.2517-6161.1996.tb02080.x)。

原文中で整合が取りにくいロット数や包括的な改善量は転載せず、確認できた範囲の事例として要約しています。

## 確認結果

2026年9月13日、LuaLaTeX（TeX Live 2026）で14ページのPDFを生成しました。コンパイル警告、未解決の参照、文字欠落、はみ出し警告はありません。全ページのレイアウト、主要補正式と参考文献を画像で確認し、12文献の番号が本文の引用順と一致することを確認しました。
