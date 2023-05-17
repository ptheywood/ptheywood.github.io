# [ptheywood.github.io](http://ptheywood.github.io)

Jekyll powered personal / academic website.

## Building the site

### Install Dependencies

1. Install ruby.

    ```bash
    sudo apt install ruby-full
    ```

2. Install Bundler

    ```bash
    sudo gem install bundler
    ```

3. Install other dependencies with Bundler

    ```bash
    bundle config set --local path 'vendor/bundle'
    bundle install
    ```

### Update Dependencies

```bash
bundler update --all
```

### Serving a local copy of the site

```bash
bundler exec jekyll serve
```

### Building a static HTML version of the site

```bash
bundler exec jekyll build
```
