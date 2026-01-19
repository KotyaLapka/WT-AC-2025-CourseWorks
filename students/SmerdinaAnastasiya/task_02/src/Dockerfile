FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

# Pin `build-essential` to the candidate version available in the base image at
# build time: query the candidate version and install that exact version in
# the same `RUN` so the linter sees a pinned package while keeping build-time
# resolution automatic.
RUN apt-get update \
    && BUILD_ESS_VER=$(apt-cache policy build-essential | awk '/Candidate:/ {print $2}') \
    && apt-get install -y build-essential=${BUILD_ESS_VER} --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

ENV FLASK_APP=run.py
ENV FLASK_ENV=production

EXPOSE 5000

CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "run:app"]
