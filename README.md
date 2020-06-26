## setup
git clone git@github.com:ren3-k/work2.git
cd work2/docker/jpug-doc-web
git clone git@github.com:pgsql-jp/jpug-doc.git
cd ../../
docker-compose build
docker-compose run -d

http://localhost:8080/admin

クローラー →　ウェブ
| URL | http://jpug-doc-web:1080/ |
| クロール対象とするURL | http://jpug-doc-web:1080/.* |
| 間隔 | 10 ミリ秒 |
