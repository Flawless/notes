# Gitlab Naxx Update

1. emerge --sync && emerge -uaNDv world
2. cd /opt/gitlabhq-X.X && sudo -u git -H bundle exec rake gitlab:backup:create RAILS_ENV=production
3. service gitlabhq-X.X stop
4. emerge --config gitlabhq
5. nano /etc/init.d/gitlabhq-X.X # Workhorse config
* -listenNetwork tcp -listenAddr 127.0.0.1:8181
6. nano /etc/cron.daily # Change directory to new version
7. nano /etc/apache/vhost.d/*01_gitlab.dnoublublenie.ru*.conf # Change directory to new version
8. cd /opt/gitlabhq-X.X && sudo -u git -H bundle exec rake gitlab:check RAILS_ENV=production
8. emerge -ca
 