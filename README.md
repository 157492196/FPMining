# FPMining
Apriori &amp; FPGrowth implementation by C++

һ�� c++ ʵ�ֵ� Apriori �� FPGrowth Ƶ����ھ��㷨��

�������ݼ� Groceries �� UNIX_usage��

## ʹ�÷���

### ����

```shell
> make
> cd bin
```

### ��������

���²������� bin/ Ŀ¼�½���

```shell
> ./FPMining.exe --help
Apriori & FPGrowth implement with c++. Author: Jiang HuiYu.
Usage:
  FPMining [OPTION...]

  -i, --input arg       Input file name (default: ../DataLoader/test.txt)
  -m, --map             Input map file name (default: input + '.dict')
  -o, --output arg      Output file name prefix
  -a, --algorithm arg   Using algorithm: 'fpgrowth', 'apriori', 'all'
                        (default: all)
  -s, --support arg     Minimal support (default: 2)
  -c, --confidence arg  Minimal confidence (default: 0.2)
  -t, --top-k arg       Output top-k association rule (default: 100)
  -d, --debug           Enable debugging
  -v, --verbose         Verbose output
  -p, --compare         Compare two results
  -h, --help            Print usage
```

### С����

#### �ļ�����

```
> cat ../DataLoader/test.txt
1,2,5,
2,4,
2,3,
1,2,4,
1,3,
2,3,
1,3,
1,2,3,5,
1,2,3,

> cat ../DataLoader/test.txt.dict
1,A
2,B
3,C
4,D
5,E
```

#### ���н��

```shell
> ./FPMining.exe
FPGrowth time consuming: 0 s, get 13 itemsets

Apriori time consuming: 0 s, get 13 itemsets

Generate 24 rules, show 24 rules.
{
<{ E } -> { B } : 1>,
<{ E, B } -> { A } : 1>,
<{ E } -> { A, B } : 1>,
<{ E, A } -> { B } : 1>,
<{ D } -> { B } : 1>,
<{ E } -> { A } : 1>,
<{ A } -> { B } : 0.666667>,
<{ A } -> { C } : 0.666667>,
<{ C } -> { A } : 0.666667>,
<{ C } -> { B } : 0.666667>,
<{ B } -> { C } : 0.571429>,
<{ B } -> { A } : 0.571429>,
<{ A, C } -> { B } : 0.5>,
<{ A, B } -> { E } : 0.5>,
<{ C, B } -> { A } : 0.5>,
<{ A, B } -> { C } : 0.5>,
<{ A } -> { E } : 0.333333>,
<{ A } -> { E, B } : 0.333333>,
<{ A } -> { B, C } : 0.333333>,
<{ C } -> { A, B } : 0.333333>,
<{ B } -> { D } : 0.285714>,
<{ B } -> { A, E } : 0.285714>,
<{ B } -> { E } : 0.285714>,
<{ B } -> { A, C } : 0.285714>,
}
```

### ��ʵ����

���� Groceries ���ݼ���֧�ֶȴ��ڵ��� 10 ����� ��������ŶȽϴ��ǰ 20 ����������

ע�⣺ͨ�� -s ���ø�С����С֧�ֶȽ��ᵼ������ʱ�������ӡ�

```shell
> ./FPMining.exe -i ../Dataset/Groceries.set -s 10 -t 20
FPGrowth time consuming: 0.208439 s, get 13492 itemsets

Apriori time consuming: 33.5215 s, get 13492 itemsets

Generate 102766 rules, show 20 rules.
{
<{ newspapers, whole milk, rolls/buns, soda } -> { other vegetables } : 1>,
<{ brown bread, pip fruit, whipped/sour cream } -> { other vegetables } : 1>,
<{ rice, sugar } -> { whole milk } : 1>,
<{ pip fruit, hygiene articles, butter } -> { whole milk } : 1>,
<{ rice, root vegetables, butter } -> { whole milk } : 1>,
<{ cream cheese , napkins, domestic eggs } -> { whole milk } : 1>,
<{ canned fish, hygiene articles } -> { whole milk } : 1>,
<{ oil, tropical fruit, root vegetables, yogurt } -> { whole milk } : 1>,
<{ flour, root vegetables, whipped/sour cream } -> { whole milk } : 1>,
<{ fruit/vegetable juice, butter, tropical fruit, whipped/sour cream } -> { other vegetables } : 1>,
<{ oil, other vegetables, root vegetables, yogurt } -> { whole milk } : 1>,
<{ grapes, yogurt, whole milk, tropical fruit } -> { other vegetables } : 1>,
<{ sugar, domestic eggs, curd } -> { whole milk } : 1>,
<{ butter, domestic eggs, other vegetables, whipped/sour cream } -> { whole milk } : 1>,
<{ butter, pork, other vegetables, whipped/sour cream } -> { whole milk } : 1>,
<{ ham, pip fruit, tropical fruit, yogurt } -> { other vegetables } : 1>,
<{ sausage, rolls/buns, tropical fruit, root vegetables } -> { whole milk } : 1>,
<{ white bread, other vegetables, butter, root vegetables } -> { whole milk } : 1>,
<{ soft cheese, root vegetables, citrus fruit } -> { other vegetables } : 1>,
<{ oil, other vegetables, tropical fruit, root vegetables, yogurt } -> { whole milk } : 1>,
}
```

## Requirements
[cxxopts](https://github.com/jarro2783/cxxopts): �����в���չʾ
