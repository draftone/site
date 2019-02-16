# matplotlib

## irisの特徴量表示

```Python
def read_iris_data():
    df = pd.read_csv('https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data', header=None)
    print(df.tail())

    # データフレームの4列目の0から100行目までを取得
    y = df.iloc[0:100, 4].values

    # データがIris-setosaの場合-1、それ以外は1を出力
    y = np.where(y == 'Iris-setosa', -1, 1)

    # データフレームの0、2列目の0から100行目までを出力
    X = df.iloc[0:100, [0, 2]].values

    plt.scatter(X[:50,0], X[:50,1], color='red', marker='o', label='setosa')
    plt.scatter(X[50:100,0], X[50:100,1], color='blue', marker='x', label='versicolor')
    plt.xlabel('sepal length [cm]')
    plt.ylabel('petal length [cm]')
    plt.legend(loc='upper left')
    plt.show()

```

### plt.scatter

散布図を描写する

上は0から50行目までのPlotの例

下は51行目から100行目までのPlotの例

```Python
plt.scatter(X[:50,0], X[:50,1], color='red', marker='o', label='setosa')
plt.scatter(X[50:100,0], X[50:100,1], color='blue', marker='x', label='versicolor')
```

### plt.xlabel ylabel

ラベルを設定する

```
plt.xlabel('sepal length [cm]')
plt.ylabel('petal length [cm]')
```

### plt.legend

凡例の表示

```
plt.legend(loc='upper left')
```

### plt.show

表示する

```
plt.show()
```