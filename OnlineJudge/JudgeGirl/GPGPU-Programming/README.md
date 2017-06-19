## README ##


### Sample Input ###

```
gpu  qq   a hello   sonoda  
```

### Sample Output ###

```
gpu  qq   a hello   sonoda  
1230012000101234500012345600
```

### Input Format ###

輸入一個長度最多一千萬且只包含小寫英文字母和空白的組合，連續的英文字母長度不超過 500。

### Output Format ###

輸出結果為一整數序列

### 解法說明 ###


以輸入為例 `  abc    defg `

#### 第一步 ####

將每一個空白位置填上索引，反之填上 `-1`

```
str[] = [ ][ ][a][b][c][ ][ ][ ][ ][d][e][f][g][ ]
pos[] =  0  1  -1 -1 -1  5  6  7  8 -1 -1 -1 -1 13
```

#### 第二步 ####

將 `pos[]` 陣列，根據 inclusive scan，完成前綴最大值。

```
str[] = [ ][ ][a][b][c][ ][ ][ ][ ][d][e][f][g][ ]
pos[] =  0  1   1  1  1  5  6  7  8  8  8  8  8 13
```

#### 第三步 ####

利用索引值扣去其值

```
str[] = [ ][ ][a][b][c][ ][ ][ ][ ][d][e][f][g][ ]
pos[] =   0  0  1  2  3  0  0  0  0  1  2  3  4  0
```