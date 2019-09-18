# 엘라스틱 서치(Elasticsearch) 기본 개념 정리

## RDBMS와 무엇이 다른가?
- 관계형 데이터베이스는 key-value 값 중심으로 모든 데이터를 저장하는데 비해, 엘라스틱서치의 경우 키워드 중심으로 데이터를 검색합니다. 그러므로, category 기준으로 데이터를 찾아가는 관계형 데이터베이스에 비해 속도가 상당히 빠르다고 할 수 있습니다.

## ElasticSearch 와 RDB의 예약어 비교

| ElasticSearch | Relational DB |
|:-------------:|:-------------:|
|     index     |  Database     |
|     type      |     table     |
| Document      |   Row         |
| Field         |   Column      |
|  Mapping      |    Schema     |

## ElasticSearch 데이터 다루기

- Ubuntu의 Curl 커맨드를 사용하여 다음과 같이 REST API를 보낼 수 있습니다.

- select * from class where id = 1
```
curl -XGET localhost:9200/classes/class/1
```

- insert into class values (xxx)
```
curl -XPOST localhost:9200/classes/class/1 -d ' {xxx}'
```
- update class set xxx where id = 1;
```
curl -XPUT localhost:9200/classes/class/1 -d ' {xxx}'
```
- delete from class where id = 1;
```
curl -XDELETE localhost:9200/classes/class/1
```

## Troubleshooting

- curl 커맨드 사용시, 다음과 같은 명령어를 넣지 않으면 에러가 발생 한다. (mapping json 수정)

```
curl -H 'Content-Type: application/json'
```

