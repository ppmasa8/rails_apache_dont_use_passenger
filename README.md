# rails_apache_don't_use_passenger

仮想環境でどうしてもメモリが増やせなくて、（スワップしても無理）passagerのコンパイルができない
時に、apacheとrailsを連携させる方法。

- リバースプロキシを利用する方法

apacheのこのディレクトリにアクセスが来たら、指定したURLにリクエストを丸投げすることができる機能を使って、
擬似的にapacheとrailsを連携させることができる

```
/etc/httpd/conf/httpd.conf

ProxyPass /app/ http://127.0.0.1:3000/
ProxyPassReverse /app/ http://127.0.0.1:3000/
```
