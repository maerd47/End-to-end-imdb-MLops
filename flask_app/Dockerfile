FROM python:3.10-slim

WORKDIR /app

COPY  . /app/

COPY vectorizer.pkl /app/models/vectorizer.pkl

RUN pip install -r requirements.txt

RUN python -m nltk.downloader stopwords wordnet

EXPOSE 5000

#local
#CMD ["python", "app.py"]  

#Prod
CMD ["/usr/local/bin/gunicorn", "--bind", "0.0.0.0:5000", "--timeout", "120", "app:app"]