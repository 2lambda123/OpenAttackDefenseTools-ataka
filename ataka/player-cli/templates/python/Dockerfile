FROM python:latest

RUN pip install --no-cache-dir --upgrade pip

RUN pip install --no-cache-dir pwntools cryptography beautifulsoup4 requests

WORKDIR /exploit

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD [ "python3", "exploit.py" ]
