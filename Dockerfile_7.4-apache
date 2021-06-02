FROM yiisoftware/yii2-php:7.4-apache

# workdir /app
RUN apt-get update && apt-get install -y git
ADD WeWorkFinance /WeWorkFinance
RUN ls -ls /WeWorkFinance
RUN cd / && git clone https://github.com/pangdahua/php7-wxwork-finance-sdk.git
RUN cd /php7-wxwork-finance-sdk && phpize && ./configure  --with-wxwork-finance-sdk=/WeWorkFinance && make && make install
ADD wxwork-finance-sdk.ini /usr/local/etc/php/conf.d/wxwork-finance-sdk.ini
RUN rm -rf /usr/local/etc/php/conf.d/docker-php-ext-intl.ini
