FROM python:3.11-slim

RUN pip install --no-cache-dir --upgrade pip

WORKDIR /

COPY ataka/common/requirements.txt /ataka/common/
RUN pip install --no-cache-dir -r /ataka/common/requirements.txt
COPY ataka/common /ataka/common

VOLUME /data/shared
VOLUME /data/exploits

COPY ataka/api/requirements.txt /ataka/api/
RUN pip install --no-cache-dir -r /ataka/api/requirements.txt
COPY ataka/api /ataka/api

CMD [ "bash", "/ataka/common/delayed_start.sh", "--", "python", "-m", "uvicorn", "--host", "0.0.0.0", "ataka.api:app"]
