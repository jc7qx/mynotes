刪除不必要的欄位
```python
df1 = df.loc[:, ~df.columns.isin(['居住地址', '戶籍地址', '公司地址'])] 
```

顯示資料表特定欄位
``` python
caseInfo = ['身分證號','觀護案號', '交付原因','案由名稱', '保護管束開始起日', '保護管束結束迄日', '終結日期', '終結情形','註記日期', '再犯機關', '再犯案號', '解除註記日期', '解除註記原因']
df1[df1['身分證號']==caseNo][['身分證號', '姓名', '生日','婚姻', '教育', '職業', '兵役']]'
df1[df1['身分證號']==caseNo].loc[:,caseInfo] #caseInfo= string`
```

資料表中將重複資料消除
``` python
indiviual_cases = df1[caseInfo].drop_duplicates()
```
