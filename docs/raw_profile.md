# Raw profile of the 47 sheets that touch Miyagi (whole sheets, before any cutting)

Source: G空間情報センター dataset `mesh_10` (全国森林資源メッシュ, zone X), sheets chosen by intersecting the sheet index with the Miyagi boundary (KSJ N03). Run 2026-10-29; sha256 of each archive is in data/raw/20261029/MANIFEST.json (kept in the Hugging Face repo).

These counts cover the whole sheets, so they include cells of neighbouring prefectures and of the sea. The Miyagi-only figures are in docs/miyagi_profile.md.

- sheets: 47; rows: 26,280,216; layers: 47 geometry layers, one per file, named like the file; geometry type ids: {6: 26280216} (6 = MultiPolygon); invalid geometries: 0
- CRS: EPSG:6678; plane bbox x -60000 to 80000, y -247180 to -105000
- column sets: 1 distinct (林種, 森林簿樹種1, 森林簿樹種2, 森林簿樹種3, 林齢, 森林簿年月日, 樹冠高, レーザ解析樹種, 立木密度, 平均標高, 計測年月日, plus the GeoPackage fid)

| column | NULL rows | share of rows |
| --- | ---: | ---: |
| 林種 | 8,992,676 | 34.2% |
| 森林簿樹種1 | 8,992,676 | 34.2% |
| 森林簿樹種2 | 21,335,935 | 81.2% |
| 森林簿樹種3 | 24,305,448 | 92.5% |
| 林齢 | 8,992,676 | 34.2% |
| 森林簿年月日 | 8,992,676 | 34.2% |
| 樹冠高 | 26,280,216 | 100.0% |
| レーザ解析樹種 | 26,280,216 | 100.0% |
| 立木密度 | 26,280,216 | 100.0% |
| 平均標高 | 26,280,216 | 100.0% |
| 計測年月日 | 26,280,216 | 100.0% |

## Unique values of the text columns (all 47 sheets)

### 林種

| value | rows |
| --- | ---: |
| 天然林 | 9,258,010 |
| <NULL> | 8,992,676 |
| 人工林 | 7,246,134 |
| その他 | 338,197 |
| 未立木地 | 213,067 |
| 伐採跡地 | 155,366 |
| 竹林 | 76,766 |

### 森林簿樹種1

| value | rows |
| --- | ---: |
| <NULL> | 8,992,676 |
| 広葉樹 | 8,822,430 |
| スギ | 5,093,264 |
| マツ類 | 1,822,597 |
| その他 | 535,931 |
| カラマツ | 459,042 |
| ヒノキ類 | 268,773 |
| 伐採跡地 | 155,366 |
| タケ | 76,766 |
| その他針葉樹 | 44,444 |
| ヒバ | 8,914 |
| エゾマツ | 13 |

### 森林簿樹種2

| value | rows |
| --- | ---: |
| <NULL> | 21,335,935 |
| 広葉樹 | 3,615,550 |
| マツ類 | 617,720 |
| スギ | 392,452 |
| カラマツ | 189,815 |
| ヒノキ類 | 55,944 |
| ヒバ | 39,886 |
| その他針葉樹 | 31,288 |
| その他 | 895 |
| 伐採跡地 | 656 |
| タケ | 75 |

### 森林簿樹種3

| value | rows |
| --- | ---: |
| <NULL> | 24,305,448 |
| 広葉樹 | 1,074,270 |
| マツ類 | 440,135 |
| ヒバ | 181,683 |
| その他針葉樹 | 147,072 |
| スギ | 78,447 |
| カラマツ | 26,937 |
| ヒノキ類 | 26,130 |
| 伐採跡地 | 54 |
| その他 | 40 |

### レーザ解析樹種

| value | rows |
| --- | ---: |
| <NULL> | 26,280,216 |

### 森林簿年月日

| value | rows |
| --- | ---: |
| <NULL> | 8,992,676 |
| 2023/3/31 | 7,830,124 |
| 2024/4/1 | 3,546,284 |
| 2020/4/1 | 2,245,452 |
| 2019/4/1 | 1,800,526 |
| 2021/4/1 | 1,410,371 |
| 2023/4/1 | 367,588 |
| 2022/4/1 | 73,295 |
| 2024/3/31 | 13,900 |

## Other findings

- 計測年月日 values other than NULL: {}
- The literal text `#N/A` as a value: 森林簿樹種1 0 rows, 森林簿樹種2 0 rows; kept as in the source.
- 林齢 is 0 in 551,827 rows besides the NULLs (8,992,676); whether 0 means an age of zero or an unknown age is not stated in the definition.
- 森林簿年月日 holds 8 dates, as text: 2019/4/1, 2020/4/1, 2021/4/1, 2022/4/1, 2023/3/31, 2023/4/1, 2024/3/31, 2024/4/1.
- No column separates 国有林 from 民有林 in the mesh; that attribute (民国別) is in the 森林計画対象森林レイヤ of Miyagi (downloaded as well).
