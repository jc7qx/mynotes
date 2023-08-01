將一個dict轉換成json並儲存到一個json檔

```python
import json 
sample_dict ={ 
	"key1": 1, 
	"key2": 2, 
	"key3": 3 
} 
json_obj = json.dumps(sample_dict, indent = 3) 
print(json_obj)
with open("sample_file.json", "w") as file: 
	json.dump(sample_dict, file)
```
