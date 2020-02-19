## install
```
brew install hugo
```

## verify version
```
hugo version
> Hugo Static Site Generator v0.63.2/extended darwin/amd64 BuildDate: unknown
```

## create new book instance
```
hugo new site <book_name>
> creates new folder
```

## make sure you are inside the book folder
```
cd <book_name>
```

## init git repo
```
git init
```

## add book theme
```
git submodule add https://github.com/alex-shpak/hugo-book themes/book
```

## copy example site
```
cp -R themes/book/exampleSite/content .
```

## run hugo server
```
hugo server --minify --theme book
hugo server
```

## generate public folder
```
hugo
```
