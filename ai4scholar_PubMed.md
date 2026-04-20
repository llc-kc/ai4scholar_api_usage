
## 文献搜索
POST /pubmed/v1/paper/search
根据关键词搜索 PubMed 文献，支持多种过滤条件

### 参数
query string 必填搜索关键词
limit number 返回数量（默认 20，最大 10000）
offset number 分页偏移量
sort string 排序方式：relevance | date
minDate string 最小日期（YYYY/MM/DD）
maxDate string 最大日期（YYYY/MM/DD）

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
