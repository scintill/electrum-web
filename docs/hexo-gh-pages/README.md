# From [Hexo](https://github.com/tommy351/hexo/tree/gh-pages)

```sh
# get hexo gh-pages source
wget https://github.com/tommy351/hexo/archive/gh-pages.zip && unzip gh-pages.zip

# fix links
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#href="/hexo/#href="/#g'
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#value="/hexo/#value="/#g'
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#src="/hexo/#src="/#g'

# remove Google Analytics
cd hexo-gh-pages
for i in `ack gaq -l`; do vim -u NONE -c "12,23d" -c "wq" $i; done
cd ..

# launch site
darkhttpd $PWD --port 54321
```
