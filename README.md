


#Run Json server (mocking JSON responces)

* Docker (https://github.com/William-Yeh/docker-json-server):

    docker pull  williamyeh/json-server

    docker run  \
        -p 3000:3000  -v /<project folder>/json_mock:/data  \
        williamyeh/json-server        \
        --watch server.json

* Local Node.js (https://www.npmjs.com/package/json-server)

    npm install -g json-server

    json-server --watch server.json
