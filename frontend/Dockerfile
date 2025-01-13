FROM nginx
COPY code /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY expense.conf /etc/nginx/conf.d/expense.conf