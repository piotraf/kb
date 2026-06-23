# MySQL Generic Binary Tarballs — Fetch

## HEAD-check (confirm 200 before pulling)

```bash
for u in \
 https://dev.mysql.com/get/Downloads/MySQL-9.7/mysql-9.7.1-linux-glibc2.28-x86_64.tar.xz \
 https://dev.mysql.com/get/Downloads/MySQL-9.7/mysql-9.7.1-linux-glibc2.28-x86_64-minimal.tar.xz \
 https://dev.mysql.com/get/Downloads/MySQL-8.4/mysql-8.4.10-linux-glibc2.28-x86_64.tar.xz \
 https://dev.mysql.com/get/Downloads/MySQL-8.4/mysql-8.4.10-linux-glibc2.28-x86_64-minimal.tar.xz \
 https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.46-linux-glibc2.28-x86_64.tar.xz \
 https://downloads.mysql.com/archives/get/p/23/file/mysql-5.7.44-linux-glibc2.12-x86_64.tar.gz \
 https://downloads.mysql.com/archives/get/p/23/file/mysql-5.6.51-linux-glibc2.12-x86_64.tar.gz \
 https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.62-linux-glibc2.12-x86_64.tar.gz ; do
  echo "$(curl -fsLI -o /dev/null -w '%{http_code}' "$u") $u"
done
```

## Fetch

```bash
curl -fLO https://dev.mysql.com/get/Downloads/MySQL-9.7/mysql-9.7.1-linux-glibc2.28-x86_64.tar.xz
curl -fLO https://dev.mysql.com/get/Downloads/MySQL-9.7/mysql-9.7.1-linux-glibc2.28-x86_64-minimal.tar.xz
curl -fLO https://dev.mysql.com/get/Downloads/MySQL-8.4/mysql-8.4.10-linux-glibc2.28-x86_64.tar.xz
curl -fLO https://dev.mysql.com/get/Downloads/MySQL-8.4/mysql-8.4.10-linux-glibc2.28-x86_64-minimal.tar.xz
curl -fLO https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.46-linux-glibc2.28-x86_64.tar.xz
curl -fLO https://downloads.mysql.com/archives/get/p/23/file/mysql-5.7.44-linux-glibc2.12-x86_64.tar.gz
curl -fLO https://downloads.mysql.com/archives/get/p/23/file/mysql-5.6.51-linux-glibc2.12-x86_64.tar.gz
curl -fLO https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.62-linux-glibc2.12-x86_64.tar.gz
```

## Verify

```bash
ls -lh 
```

Pass: eight files (9.7.1 full+minimal, 8.4.10 full+minimal, 8.0.46, 5.7.44, 5.6.51, 5.5.62).

Notes:
- Current LTS: 9.7.1, 8.4.10. 8.0.46 = final 8.0 (EOL April 2026).
- glibc: 5.5/5.6/5.7 = glibc2.12; 8.0/8.4/9.x = glibc2.28.
- minimal = no test suite/debug binaries (smaller); full includes mysqltest etc.
- Runtime libs (libaio, libncurses/libtinfo5, libnuma) belong in the consuming container, not here.
- Point releases tick up — re-run the HEAD-check before reproducing later.
