openssl genrsa -out sec.akj.ru.key 2048
openssl req -new -key sec.akj.ru.key -out sec.akj.ru.csr -config cert.conf
openssl x509 -req -days 365 -in sec.akj.ru.csr -signkey sec.akj.ru.key -out sec.akj.ru.crt -extfile  cert.conf

cat sec.akj.ru.key | base64 -w0
cat sec.akj.ru.crt | base64 -w0
