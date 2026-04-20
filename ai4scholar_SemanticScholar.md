## API参考

https://ai4scholar.net/open-platform
https://www.semanticscholar.org/product/api/tutorial



## 文献关键词检索

GET https://ai4scholar.net/graph/v1/paper/search
一次发送多条查询进行批量搜索，提高吞吐量

### 参数

- `query` sets the search term
- `token` automatically handles pagination
- `fields` determines what data the API endpoint will return to you. citations是这篇文章被引用的论文信息。
- `sort` allows users to sort the results by the paperId, publicationDate, or citationCount fields
- `publicationTypes` filters results by paper publication type (e.g. journal articles)
- `openAccessPdf` filters results by whether they contain public PDFs of papers
- `minCitationCount` filters results by whether they have at least a given number of citations
- `publicationDateOrYear` filters results by a date range
- `year` filters results by a year range
- `venue` filters results by publication venue
- `fieldsOfStudy` filters results by the paper’s field of study

### 样例

```
curl -X GET "https://ai4scholar.net/graph/v1/paper/search" \
-H "Authorization: Bearer api_key" \
-G \
--data-urlencode 'query="LLM inference optimization"' \
--data-urlencode 'limit=100' \
--data-urlencode 'fields=paperId,title,authors,year,abstract,citations' \
--data-urlencode 'year=2026-'
```