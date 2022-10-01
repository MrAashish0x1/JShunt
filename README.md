# JShunt
JShunt is a tool for quickly extracting URLs and subdomains from JS files on a website.

### Usage

- **Simple Crawl**

```
python JShunt.py -u http://www.mi.com
```

This command will crawl all the js links of the single page http://www.mi.com and find the url and subdomain in it

Return example:

````
url: http://www.mi.com
Find 50 URL:
http://api-order.test.mi.com
http://api.order.mi.com
http://userid.xiaomi.com/userId
http://order.mi.com/site/login?redirectUrl=
...omitted
                                                              
Find 26 Subdomain:
api-order.test.mi.com
api.order.mi.com
userid.xiaomi.com
order.mi.com
...omitted

````

- **Deep Crawl**
```
python JShunt.py -u http://www.mi.com -d
```
Going deeper into a page to crawl JS, the time will consume longer.

It is recommended to use -ou and -os to specify the file name where URLs and subdomains are stored. E.g:

````
python JShunt.py -u http://www.mi.com -d -ou mi_url.txt -os mi_subdomain.txt
````

- **Batch specify URL/specify JS**

Specify URL:

````
python JShunt.py -f text.txt
````

Specify JS:

````
python JShunt.py -f text.txt -j
````

You can use brupsuite to crawl the website and extract the URL or JS link, save it to a txt file, one per line.

Specifying a URL or JS does not require deep crawling, just a single page.

- **other**

-c specifies the cookie to crawl the page Example:

````
python JShunt.py -u http://www.mi.com -c "session=xxx"
````

-ou specifies the file name to save the URL link Example:

````
python JShunt.py -u http://www.mi.com -ou mi_url.txt
````

-os specifies the file name to save the subdomain name Example:

````
python JShunt.py -u http://www.mi.com -os mi_subdomain.txt
````
