* veri tabani kullanicisiyla baglanmadiginda aldigin hata
pdns=> DROP DATABASE pdns;
ERROR:  must be owner of database pdns

* cozum;
# psql -U postgres -c "drop database pdns"
DROP DATABASE

* yeni veri tabani - kullanici ekleme
CREATE USER kullanici_adi WITH PASSWORD '';
CREATE DATABASE db_adi;
GRANT ALL PRIVILEGES ON DATABASE db_adi to kullanici_adi;

* auto-increment'i arastir.
