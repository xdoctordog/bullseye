
Project installation

=============================================================================================================
https://magento.stackexchange.com/questions/366082/magento-2-4-6-could-not-validate-a-connection-to-the-opensearch-no-alive-node
Replace --search-engine=opensearch with --search-engine= elasticsearch7, it will solve your issue.

php -d memory_limit=-1 bin/magento setup:install \
--base-url=https://magento.loc \
--db-host=mariadb \
--db-name=magento \
--db-user=magento \
--db-password=magento \
--admin-firstname=Dzmitry \
--admin-lastname=Marozau \
--admin-email=dm@mail.com \
--admin-user=dm \
--admin-password=magento \
--language=en_US \
--currency=USD \
--timezone=America/Chicago \
--use-rewrites=1 \
--backend-frontname="admin" \
--search-engine=elasticsearch7 \
--elasticsearch-host=192.168.100.23 \
--elasticsearch-port=9200

bin/magento admin:user:create --admin-user=dm --admin-password=magento --admin-email=dm@mail.com --admin-firstname=Dzmitry --admin-lastname=Marozau
bin/magento module:disable Magento_TwoFactorAuth

=============================================================================================================


