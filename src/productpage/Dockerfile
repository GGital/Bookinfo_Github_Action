From python:3.9-slim

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN pip install --no-cache-dir --progress-bar off -r requirements.txt

COPY . .

EXPOSE 9000

CMD [ "python", "./productpage.py" , "9000" ]