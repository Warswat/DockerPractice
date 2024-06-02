FROM huecker.io/library/python:3.10

WORKDIR /src

COPY . .
RUN pip3 install --no-cache-dir --upgrade -r requirements.txt

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]