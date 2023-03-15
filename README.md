Here is a list of some very handy resources to learn NJS

 - NJS is a subset of ECMAScript, the [compatibility guide](https://nginx.org/en/docs/njs/compatibility.html) lists the properties and methods that are compliant with ECMAScript.
 - The NJS [reference](https://nginx.org/en/docs/njs/reference.html) lists the specific properties, methods and modules that are specific to NJS.  I found this guide extremely valuable in understanding NJS. 
 - NGINX's github page has many [hands-on examples](https://github.com/nginx/njs-examples) for real-world use cases.
 - Timo Sark's [youtube channel](https://www.youtube.com/@Tippexs91), especially his video [NJS Zero to Hero](https://www.youtube.com/live/FuBi9pvdr-A?feature=share&t=159).
 - The NJS [cli](http://nginx.org/en/docs/njs/cli.html) is very handy for debugging.

The quickest way to get up an environment with NJS is to use the official nginx container:

    docker run -p 80:80 nginx:latest
    docker exec -it [container_id] bash

Edit /etc/nginx/nginx.conf and add the following line in the main context:

    load_module /usr/lib/nginx/modules/ngx_http_js_module.so;
    
Reload nginx and away you go:

    nginx -s reload
