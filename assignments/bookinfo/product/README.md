# How to run product page

## Prerequisite

* Python 3.8

```bash
pip install -r requirements.txt
python productpage.py 9080
```

## How to run with Docker

```bash
# Build Docker Image for productpage service
docker build -t productpage .

# Run productpage service on port 8083
docker run -d -p 8083:9080 --name product --link reviews:reviews --link details:details --link ratings:ratings \
-e 'DETAILS_HOSTNAME=http://details:9080/details' -e 'RATINGS_HOSTNAME=http://ratings:8080/' -e 'REVIEWS_HOSTNAME=http://reviews:9080/' products
```