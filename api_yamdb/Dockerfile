FROM python:3.7-slim
WORKDIR /app
COPY . .
RUN pip install --upgrade pip && pip3 install -r requirements.txt --no-cache-dir
ENV DJANGO_SECRET_KEY 123
RUN ["chmod", "+x", "/entrypoint.sh"]
ENTRYPOINT ["/app/entrypoint.sh"]
CMD ["run"]