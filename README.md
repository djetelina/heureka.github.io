# Develop!

* From project directory run: 
```shell script
$ docker run -it --rm --volume="$PWD:/srv/jekyll" -p 4000:4000 -p 4001:4001 jekyll/jekyll:pages jekyll serve --livereload --livereload-port 4001
```


# Deploy!

* Get your PRs merged
