# [ptheywood.github.io](http://ptheywood.github.io)

Jekyll powered personal / academic website.


## Building the site

### Install Dependencies

1. Install ruby. 
    ```
    sudo apt install ruby-full
    ```
2. Install Bundler
    ```
    sudo gem install bundler
    ```
3. Install other dependencies with Bundler
    ```
    bundler install --path vendor/bundle
    ```

### Update Dependencies

```
bundler update --all
```

### Serving a local copy of the site

```
bundler exec jekyll serve
```

### Building a static HTML version of the site

```
bundler exec jekyll build
```
