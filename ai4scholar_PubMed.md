参考https://ai4scholar.net/open-platform



## 文献搜索

POST /pubmed/v1/paper/search
根据关键词搜索 PubMed 文献，支持多种过滤条件

### 参数
- `query` string 必填搜索关键词
- `limit` number 返回数量（默认 20，最大 10000）
- `offset` number 分页偏移量
- `sort` string 排序方式：relevance | date
- `minDate` string 最小日期（YYYY/MM/DD）
- `maxDate` string 最大日期（YYYY/MM/DD）

### 样例
```
curl -X POST https://ai4scholar.net/pubmed/v1/paper/search \
-H "Content-Type: application/json" \
-H "Authorization: Bearer api_key" \
-d '{
  "query": "Protein-templated synthesis",
  "limit": 100,
  "sort": "relevance"
}'
```



## 批量获取论文详情

POST`/pubmed/v1/paper/batch`

一次获取多篇论文信息（最多 100 篇）

### 参数

- `ids `string 必填PMID 数组（最多 100 个）

### 示例

```
curl -X POST https://ai4scholar.net/pubmed/v1/paper/batch \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-xxxxx" \
  -d '{
    "ids": ["38123456", "38123457", "38123458"]
  }'
```



## 获取引用文献

GET /pubmed/v1/paper/{pmid}/citations
获取引用该论文的其他论文

### 参数

- `pmid` string 必填 PubMed ID
- `limit` number 返回数量（默认 20） 示例

样例

```
curl "https://ai4scholar.net/pubmed/v1/paper/pmid/citations?limit=10" \
  -H "Authorization: Bearer api_key"
```

