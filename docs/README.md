- https://electrum.org
- https://docs.electrum.org

Documentation Inspirations:

* http://zespia.tw/hexo/docs/

Guides Inspirations:

* http://guides.github.com/

Getting [Hexo docs](https://github.com/tommy351/hexo/tree/gh-pages)...

```sh
#!/bin/bash

# get hexo gh-pages source
wget https://github.com/tommy351/hexo/archive/gh-pages.zip && unzip gh-pages.zip

# fix links
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#href="/hexo/#href="/#g'
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#value="/hexo/#value="/#g'
find hexo-gh-pages -type f -print0 | xargs -0 sed -i 's#src="/hexo/#src="/#g'

# remove Google Analytics, Twitter, Facebook, Google +1
cd hexo-gh-pages
for i in `ack gaq -l`; do vim -u NONE -c "12,23d" -c "wq" $i; done
vim -u NONE -c "57,67d" -c "wq" index.html
ack plusone -l --print0 | xargs -0 sed -i 's#<script type="text/javascript" src="https://apis.google.com/js/plusone.js"></script>##g'
cd ..

# localize jQuery
cd hexo-gh-pages
ack jquery -l --print0 | xargs -0 sed -i 's#<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>#<script src="/js/jquery-2.1.0.min.js"></script>#g'
wget http://code.jquery.com/jquery-2.1.0.min.js -O js/jquery-2.1.0.min.js
cd ..

# clean up
rm gh-pages.zip
```

launch site:

`cd hexo-gh-pages && darkhttpd $PWD --port 54321`
