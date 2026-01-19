FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

RUN set -o pipefail && \
    apt-get update && \
    BUILD_ESS_VER=$(apt-cache policy build-essential | awk '/Candidate:/ {print $2}') && \
    apt-get install -y --no-install-recommends \
        build-essential="${BUILD_ESS_VER}" \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

ENV FLASK_APP=run.py
ENV FLASK_ENV=production

EXPOSE 5000

CMD ["gunicorn", "--workers", "4", "--bind", "0.0.0.0:5000", "run:app"]