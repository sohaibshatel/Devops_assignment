FROM python:3.11-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    postgresql-client \
    tar \
    && rm -rf /var/lib/apt/lists/*

ARG ARTIFACT_PATH

COPY ${ARTIFACT_PATH} /tmp/app.tar.gz

RUN tar -xzf /tmp/app.tar.gz -C /app && rm /tmp/app.tar.gz

RUN pip install --no-cache-dir -r requirements.txt

RUN useradd -m -u 1000 appuser && chown -R appuser:appuser /app

USER appuser

EXPOSE 8000

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "--workers", "3", "book_shop.wsgi:application"]
