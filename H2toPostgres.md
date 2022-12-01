## DBをH2からPostgreSQLに変更する

コマンドプロンプト（ターミナル）にて次のコマンドを打ち、このプロジェクトで使用する(postgresの)データベースを作成する。    
※パスワードの入力を求められます
`createdb -U postgres wsbp_prac`

作成したデータベースに接続する
`psql -U postgres wsbp_prac`

接続できたら↓のようになる
`wsbp_prac=#`

pom.xmlの以下の部分を変更する
``` xml
<dependency>
  <groupId>com.h2database</groupId>
  <artifactId>h2</artifactId>
  <scope>runtime</scope>
</dependency>
```
↓
``` xml
<dependency>
  <groupId>org.postgresql</groupId>
  <artifactId>postgresql</artifactId>
  <scope>runtime</scope>
</dependency>
```

application.propertiesの以下の部分を変更する
``` properties
spring.datasource.driver-class-name=org.h2.Driver
spring.datasource.url=jdbc:h2:~/h2db/wsbp_prac;Mode=PostgreSQL;AUTO_SERVER=TRUE;
spring.datasource.username=bxxxxxxx
spring.datasource.password=bxxxxxxx
```
↓
``` properties
spring.datasource.driver-class-name=org.postgresql.Driver
spring.datasource.url=jdbc:postgresql://localhost:5432/wsbp_prac
spring.datasource.username=postgres
spring.datasource.password=postgres
```
