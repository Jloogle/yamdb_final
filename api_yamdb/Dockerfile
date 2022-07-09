FROM python:3.7-slim
WORKDIR /app
COPY . .
RUN ["chmod", "+x", "/entrypoint.sh"]
RUN pip install --upgrade pip && pip3 install -r requirements.txt --no-cache-dir
ENV DJANGO_SECRET_KEY 123
ENTRYPOINT ["/app/entrypoint.sh"]
CMD ["run"]