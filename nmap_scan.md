Websites:
nmap -p 80,443 -T4 -Pn -A -vvv --reason --webxml --script=http-auth-finder,http-backup-finder,http-csrf,http-enum,http-errors,http-exif-spider,http-headers,http-ls,http-methods,http-passwd,http-php-version,http-robots.txt,http-server-header,http-title,http-trace,http-traceroute,http-useragent-tester,mysql-enum,mysql-info,firewalk,firewall-bypass,ftp-anon,ftp-bounce,ssh-hostkey,ssh2-enum-algos,sshv1,ssl-cert,ssl-ccs-injection,ssl-enum-ciphers,ssl-heartbleed,ssl-dh-params,ssl-date,ssl-cert-intaddr,ssl-known-key,ssl-poodle,sslv2,sslv2-drown,whois-domain,whois-ip -oA nse_test "url"

Wordpress:
http-wordpress-enum, http-wordpress-users

cupps:
cups-info, cups-queue-info

citrix:
citrix-enum-apps, citrix-brute-xml, citrix-enum-apps-xml, citrix-enum-servers, citrix-enum-servers-xml


ftp:
ftp-anon, ftp-brute, ftp-bounce, ftp-libopie, ftp-proftpd-backdoor, ftp-syst, ftp-vsftpd-backdoor, ftp-vuln-cve2010-4221

drupal:
http-drupal-enum, http-drupal-enum-users

sql
ms-sql-brute, ms-sql-config, ms-sql-dac, ms-sql-dump-hashes, ms-sql-empty-password, ms-sql-hasdbaccess, ms-sql-info, ms-sql-ntlm-info, ms-sql-query, ms-sql-tables, ms-sql-xp-cmdshell, mysql-audit, mysql-brute, mysql-databases, mysql-dump-hashes, mysql-empty-password, mysql-enum, mysql-info, mysql-query, mysql-users, mysql-variables, mysql-vuln-cve2012-2122, oracle-brute, oracle-brute-stealth, oracle-enum-users, oracle-sid-brute, oracle-tns-version, pgsql-brute

rdp:
rdp-enum-encryption, rdp-vuln-ms12-020

ssh:
ssh-auth-methods, ssh-brute, ssh-publickey-acceptance, ssh-run, ssh-hostkey, ssh2-enum-algos, sshv1

smb:
nmap —script smb-check-vulns –script-args=unsafe=1 -p445 "host"

NMAP zu Nikto:
nmap -p80,443 10.0.1.0/24 -oG - | nikto.pl -h -