# s3-yc

## RU
Скрипт обновлен для работы с [Яндекс Облаком](https://cloud.yandex.ru/)

### Установка скрипта
```bash
# Получение файла:
wget https://raw.githubusercontent.com/clientapi/s3-yc/master/build/s3-get -O /usr/local/bin/yc-get && chmod +x /usr/local/bin/yc-get

# Загрузка файла:
wget https://raw.githubusercontent.com/clientapi/s3-yc/master/build/s3-put -O /usr/local/bin/yc-put && chmod +x /usr/local/bin/yc-put

# Удаление файла:
wget https://raw.githubusercontent.com/clientapi/s3-yc/master/build/s3-delete -O /usr/local/bin/yc-delete && chmod +x /usr/local/bin/yc-delete
```
### Использование

```bash
# Получение файла:
yc-get -k {ACCESS_KEY_ID} -s {SECRET_ACCESS_KEY} /{bucketname}/{filename} > {filename}

# Загрузка файла:
yc-put -k {ACCESS_KEY_ID} -s {SECRET_ACCESS_KEY} -T /{path}/{filename} /{bucketname}/{filename}

# Удаление файла;
yc-delete -k {ACCESS_KEY_ID} -s {SECRET_ACCESS_KEY} /{bucketname}/{filename}
```

# s3-bash4

_s3-bash4_ is a small collection of _Bash_ scripts to do simple interaction with _Amazon S3_ using [_AWS Signature Version 4_](http://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-authenticating-requests.html). The advantage of using _s3-bash4_ is that it's extremly lightweight and easy to use. No need to setup _Python_, _Java_, _Ruby_ and co.

This is inspired by the discontinued [_s3-bash_](https://github.com/cosmin/s3-bash) from _cosmin_. I was in need of a _Bash_ version that supports the newer _AWS Signature Version 4_.

### Usage
    # Get file from bucket:
    s3-get -k {accesskey} -s /{path}/{secretid} -r {region} /{bucketname}/{filename} > {filename}

    # Upload file to bucket:
    s3-put -k {accesskey} -s /{path}/{secretid} -r {region} -T /{path}/{filename} /{bucketname}/{filename}

    # Delete from bucket:
    s3-delete -k {accesskey} -s /{path}/{secretid} -r {region} /{bucketname}/{filename}

### Environment Variables

Variable               | Description
---------------------- | -----------------------------------------------------------
`AWS_ACCESS_KEY_ID`    | Default _AWS Access Key ID_
`AWS_SECRET_ACCESS_KEY`| Default _AWS Secret Access Key_
`AWS_DEFAULT_REGION`   | Default _AWS S3 Region_
`AWS_SECURITY_TOKEN`   | Default _AWS Security Token for temporary credentials_

### Requirements
  - _OpenSSL_
  - _cUrl_

### License
_Apache License Version 2.0_
