# Elasticsearch에게 Lucene이란?

> Lucene은 자바로 만들어진 고성능 정보 검색 라이브러리 `색인`, `검색`, `형태소 분석`을 제공

## Lucene에서 중요한 것

- 검색에서 빼 놓을 수 없는 `역 인덱스`
- 색인과 관련된 `Index Writer`
- 검색과 관련된 `Index Searcher`
- 형태소 분석과 관련된 `Analizer`

## Lucene에서 기본 개념

- Index
- Document
- Field
- Term

-> `Term` < `Field` < `Document` < `Index` (각 단위의 집합 구조)

## Inverted Index Structure (역 색인 구조)

인덱스를 색인어 기반의 검색을 생성 하기 위해 `색인어에 대한 통계를 저장`하는 구조 <br>
즉, 용어에 대해서 문서를 나열 하는 구조가 역인덱스 라고 하는 인덱스 계열

# Elasticsearch란?

> Lucene 기반의 대표적인 검색엔진