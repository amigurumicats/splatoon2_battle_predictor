# splatoon2_battle_predictor
NNでSplatoon2のブキ構成・ステージから勝敗を学習・予測するやつ
[※WIP]

## Usage
### Requirement
- python3.x
- pip
- pytorch>=0.4
- tqdm

### Data
stat.inkさんのbattle-result-csv.zipをダウンロードしてきます。解凍します。
```
python data_preprocess.py <path/to/battle-result-csv/>
```
weapon.vocab、stage.vocab、train.json、dev.json、test.jsonが作成されます。

### Training
```
python train.py [option]
```
- `-epoch <int>` : 最大エポック数
- `-savedir <string>` : 学習モデルを保存するディレクトリ
- `-early_stopping_num <int>` : nエポック連続でdevデータでのロスが下がらなかった場合、学習を打ち切ります
- `-train_path <string>` : train.jsonのパス
- `-dev_path <string>` : dev.jsonのパス
- `-hidden_size <int>` : NNの隠れ層のサイズ

### Evaluation

