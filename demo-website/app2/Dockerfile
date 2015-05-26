FROM php:5.6

RUN mkdir /app

COPY index.php /app/index.php

EXPOSE 80

WORKDIR /app

CMD ["php", "-S", "0.0.0.0:80"]
