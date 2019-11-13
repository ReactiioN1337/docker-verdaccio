# docker-verdaccio

Very basic and simple setup to run [verdaccio](https://github.com/verdaccio/verdaccio) using `docker-compose`.

```bash
git clone https://github.com/ReactiioN1337/docker-verdaccio verdaccio \
cd verdaccio                                                          \
&& sudo chown -Rh 10001:65533 config                                  \
&& docker-compose up -d
```

## npm ERR! code E404

I recommend to do this directly as soon as the container has been started up for the first time.


```
npm ERR! code E404
npm ERR! 404 Not Found - PUT http://your.domain/package-name - no such package available
npm ERR! 404
npm ERR! 404  'package-name@1.0.0' is not in the npm registry.
npm ERR! 404 You should bug the author to publish it (or use the name yourself!)
```

Connect to your sever and enter `docker-compose exec --user root verdaccio /bin/sh`. You'll land in 
an attached shell, just type `chown verdaccio: /verdaccio/ -R && exit` to fix this issue (thanks to [@martijnhimestra](https://github.com/verdaccio/verdaccio/issues/483#issuecomment-441362075)).

## References

- https://verdaccio.org/docs/en/docker

