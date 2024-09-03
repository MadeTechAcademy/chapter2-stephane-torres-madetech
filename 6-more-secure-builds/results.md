# Measure your progress!

Commit your data here but **remember to redact any token data**!

Error message(s) from original build:


Output from better image when run:

[
  '/usr/src/app/src/../.npmrc',
  '/usr/src/app/src/../.nvmrc',
  '/usr/src/app/src/../node_modules/.package-lock.json',
  '/usr/src/app/src/../node_modules/@tess-barnes-mt/basic-node-lib/.github/workflows/publish-package.yml',
  '/usr/src/app/src/../node_modules/@tess-barnes-mt/basic-node-lib/.nvmrc',
  '/usr/src/app/src/../node_modules/@tess-barnes-mt/basic-node-lib/README.md',
  '/usr/src/app/src/../node_modules/@tess-barnes-mt/basic-node-lib/package.json',
  '/usr/src/app/src/../package-lock.json',
  '/usr/src/app/src/../package.json',
  '/usr/src/app/src/../src/index.js'
]


History listing from better image:

IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
e6911bc52d25   41 seconds ago   CMD ["/bin/sh" "-c" "node src/index.js"]        0B        buildkit.dockerfile.v0
<missing>      41 seconds ago   COPY . . # buildkit                             230kB     buildkit.dockerfile.v0
<missing>      41 seconds ago   RUN |1 GITHUB_PAT=ghp_idJff8WZJGT4iV3iGGlS3w…   6.38kB    buildkit.dockerfile.v0
<missing>      42 seconds ago   COPY package-lock.json package-lock.json # b…   229kB     buildkit.dockerfile.v0
<missing>      42 seconds ago   COPY package.json package.json # buildkit       238B      buildkit.dockerfile.v0
<missing>      42 seconds ago   COPY .npmrc ./.npmrc # buildkit                 100B      buildkit.dockerfile.v0
<missing>      42 seconds ago   WORKDIR /usr/src/app                            0B        buildkit.dockerfile.v0
<missing>      42 seconds ago   RUN |1 GITHUB_PAT=ghp_idJff8WZJGT4iV3iGGlS3w…   0B        buildkit.dockerfile.v0
<missing>      42 seconds ago   ENV GITHUB_PAT=ghp_idJff8WZJGT4iV3iGGlS3wpe4…   0B        buildkit.dockerfile.v0
<missing>      42 seconds ago   ARG GITHUB_PAT=ghp_idJff8WZJGT4iV3iGGlS3wpe4…   0B        buildkit.dockerfile.v0
<missing>      42 seconds ago   ENV NODE_ENV=production                         0B        buildkit.dockerfile.v0
<missing>      11 days ago      CMD ["node"]                                    0B        buildkit.dockerfile.v0
<missing>      11 days ago      ENTRYPOINT ["docker-entrypoint.sh"]             0B        buildkit.dockerfile.v0
<missing>      11 days ago      COPY docker-entrypoint.sh /usr/local/bin/ # …   388B      buildkit.dockerfile.v0
<missing>      11 days ago      RUN /bin/sh -c apk add --no-cache --virtual …   5.59MB    buildkit.dockerfile.v0
<missing>      11 days ago      ENV YARN_VERSION=1.22.22                        0B        buildkit.dockerfile.v0
<missing>      11 days ago      RUN /bin/sh -c addgroup -g 1000 node     && …   118MB     buildkit.dockerfile.v0
<missing>      11 days ago      ENV NODE_VERSION=20.17.0                        0B        buildkit.dockerfile.v0
<missing>      5 weeks ago      /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B        
<missing>      5 weeks ago      /bin/sh -c #(nop) ADD file:a71f7e9bc66668361…   8.83MB  



Output from multistage image when run:

[
  '/usr/src/app/src/../.npmrc',
  '/usr/src/app/src/../package-lock.json',
  '/usr/src/app/src/../package.json',
  '/usr/src/app/src/../src/index.js'
]


History listing from multistage image:

IMAGE          CREATED              CREATED BY                                      SIZE      COMMENT
6993c974e680   About a minute ago   CMD ["/bin/sh" "-c" "node src/index.js"]        0B        buildkit.dockerfile.v0
<missing>      About a minute ago   COPY /usr/src/app/src src/ # buildkit           473B      buildkit.dockerfile.v0
<missing>      26 hours ago         COPY /usr/src/app/package-lock.json package-…   229kB     buildkit.dockerfile.v0
<missing>      26 hours ago         COPY /usr/src/app/package.json package.json …   238B      buildkit.dockerfile.v0
<missing>      26 hours ago         COPY /usr/src/app/.npmrc ./.npmrc # buildkit    100B      buildkit.dockerfile.v0
<missing>      26 hours ago         WORKDIR /usr/src/app                            0B        buildkit.dockerfile.v0
<missing>      12 days ago          CMD ["node"]                                    0B        buildkit.dockerfile.v0
<missing>      12 days ago          ENTRYPOINT ["docker-entrypoint.sh"]             0B        buildkit.dockerfile.v0
<missing>      12 days ago          COPY docker-entrypoint.sh /usr/local/bin/ # …   388B      buildkit.dockerfile.v0
<missing>      12 days ago          RUN /bin/sh -c apk add --no-cache --virtual …   5.59MB    buildkit.dockerfile.v0
<missing>      12 days ago          ENV YARN_VERSION=1.22.22                        0B        buildkit.dockerfile.v0
<missing>      12 days ago          RUN /bin/sh -c addgroup -g 1000 node     && …   118MB     buildkit.dockerfile.v0
<missing>      12 days ago          ENV NODE_VERSION=20.17.0                        0B        buildkit.dockerfile.v0
<missing>      6 weeks ago          /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B        
<missing>      6 weeks ago          /bin/sh -c #(nop) ADD file:a71f7e9bc66668361…   8.83MB   


