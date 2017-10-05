
## Running `jekyll` locally via `docker`

```
docker build -t artic/jekyll .
docker run --rm -p 4000:4000 -v $PWD:/src artic/jekyll serve --host=0.0.0.0
```

Browse locally at `http://localhost:4000`
