# 5.3 データ加工

## テーブルの正規化

第１正規形 ... １つのセルには１つの値しか含まれない状態。Excelのセル結合はだめな状態

第２正規形 ... 複合キーがあるテーブルで、一部のキーで一意に定まる列がある状態を部分関数従属という。この部分関数従属を別のテーブルに分割したものを第２正規形という。（例：注文情報から商品の情報を商品マスタに追い出す）

第３正規形 ... 主キー以外の列が決まると一意に定まる列がある状態を遷移関数従属という。これを別テーブルに分割したものを第３正規形という。

- 第１正規形 ... １つのセルに１つの値にする
- 第２正規形 ... 複合キーによる部分関数従属をテーブル分割する
- 第３正規形 ... 非主キーによる遷移関数従属をテーブル分割する

## ER図

- エンティティ
- アトリビュート
- リレーション
- カーディナリティ

## SQL

- DDL ... CREATE, ALTER, DROPなど
- DCL ... GRANT, REVOKEなど
- DML ... SELECT, INSERTなど

UNIONは重複が排除される、UNION ALLは重複が排除されない

## 正規表現

正規表現

