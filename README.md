<meta name='keywords' content='python, requests, faster, speed, benchmark, pycurl, wget, urllib, rapido, velocidad, optimizacion, cython, pypy, urllib3, urllib2, urllib4, urllib5, urllib6, urllib7, urllib8, urllib9, pywget, cpython, http, httpclient, curl, libcurl, ssl, docker, json, ndjson, https, rapido, veloz, performance, critical, compiled, module, modulo, loc, minimalismo, minimalism, simple, small, tiny, argentina, spanish, compare, mejora, scraper, scrapy'>


# Faster-than-Requests

[![screenshot](https://source.unsplash.com/eH_ftJYhaTY/800x402 "Please Star this repo on GitHub!")](https://youtu.be/QiKwnlyhKrk?t=5)

![screenshot](temp.jpg "Please Star this repo on GitHub!")

| Library                       | Speed    | Files | LOC  | Dependencies          | Developers |
|-------------------------------|----------|-------|------|-----------------------|------------|
| PyWGET                        | `152.39` | 1     | 338  | Wget                  | >17        |
| Requests                      | `15.58`  | >20   | 2558 | >=7                   | >527       |
| Requests (cached object)      |  `5.50`  | >20   | 2558 | >=7                   | >527       |
| Urllib                        |  `4.00`  | ???   | 1200 | 0 (std lib)           | ???        |
| Urllib3                       |  `3.55`  | >40   | 5242 | 0 (No SSL), >=5 (SSL) | >188       |
| PyCurl                        |  `0.75`  | >15   | 5932 | Curl, LibCurl         | >50        |
| PyCurl (no SSL)               |  `0.68`  | >15   | 5932 | Curl, LibCurl         | >50        |
| Faster_than_requests          |  `0.45`  | 1     | 75   | 0                     | 1          |

<details>

- Lines Of Code counted using [CLOC](https://github.com/AlDanial/cloc).
- Direct dependencies of the package when ready to run.
- Benchmarks run on Docker from Dockerfile on this repo.
- Developers counted from the Contributors list of Git.
- Speed is IRL time to complete 10000 HTTP local requests.
- Stats as of year 2019.
- x86_64 64Bit, SSD.

</details>


# Use

```python
import faster_than_requests as requests

print(requests.get("http://httpbin.org/get"))                      # GET
print(requests.post("http://httpbin.org/post", "Some Data Here"))  # POST
requests.downloads("http://example.com/foo.jpg", "output.jpg")     # See Docs for more info.
```


# API

- `get(url: str)` HTTP GET.
- `post(url: str, body: str)` HTTP POST.
- `put(url: str, body: str)` HTTP PUT.
- `delete(url: str)` HTTP DELETE.
- `patch(url: str, body: str)` HTTP PATCH.
- `get2str(url: str)` HTTP GET body only :arrow_right: string.
- `get2str_list(list_of_urls: list)` HTTP GET body from a list :arrow_right: string.
- `get2ndjson_list(list_of_urls: list, ndjson_file_path: str)` HTTP GET body from a list :arrow_right: NDJSON.
- `get2dict(url: str)` HTTP GET body only :arrow_right: dictionary.
- `get2json(url: str)` HTTP GET body only :arrow_right: JSON.
- `get2json_pretty(url: str)` HTTP GET body only :arrow_right: Pretty-Printed JSON.
- `get2assert(url: str)` HTTP GET body only to assert from expected argument for unittests.
- `getlist2list(list_of_urls: list)` HTTP GET body from a list of urls to a list of lowercased strings :arrow_right: list.
- `post2str(url: str, body: str)` HTTP POST data only :arrow_right: string.
- `post2dict(url: str, body: str)` HTTP POST data only :arrow_right: dictionary.
- `post2json(url: str, body: str)` HTTP POST data :arrow_right: JSON.
- `post2json_pretty(url: str, body: str)` HTTP POST data :arrow_right: Pretty-Printed JSON.
- `post2assert(url: str, body: str)` HTTP POST body only to assert from expected argument for unittests.
- `post2list(url: str, body: str)` HTTP POST body to a list of lowercased strings :arrow_right: list.
- `downloads(url: str, filename: str)` HTTP GET Download 1 file.
- `downloads_list(list_of_files: list)` HTTP GET Download a list of files.
- `downloads_list_delay(list_of_files: list, delay: int, randoms: bool, debugs: bool)` HTTP GET Download a list of files with delay, optional randomized delay.

[**For more Examples check the Examples.**](https://github.com/juancarlospaco/faster-than-requests/blob/master/example/example.py)

Instead of having a pair of functions with a lot of arguments that you should provide to make it work,
we have tiny functions with very few arguments that do one thing and do it as fast as possible.

A lot of functions are oriented to Data Science, Big Data, Open Data, Web Scrapping for HTTP REST JSON APIs.

<details>
  <summary>Low Level API Extras</summary>

To control the default values the following environment variables are available:
- `requests_timeout` `int` type, must be a non-zero positive value, milliseconds precision.
- `requests_maxredirects` `int` type, must be a non-zero positive value.
- `requests_useragent` `str type, can be empty string.
- `requests_debugprogress` `bool` type, slows down performance, not recommended for general use.

</details>


# Install

- `pip install faster_than_requests`


# Docker

- Make a quick test drive on Docker!.

```bash
$ ./build-docker.sh
$ ./run-docker.sh
$ ./server4benchmarks &  # Inside Docker.
$ python3 benchmark.py   # Inside Docker.
```


# Platforms

- ✅ Linux
- ✅ Windows
- ✅ Mac
- ✅ Android
- ✅ Raspberry Pi
- ✅ BSD


# Extras

More Faster Libraries...

- https://github.com/juancarlospaco/faster-than-csv#faster-than-csv
- https://github.com/juancarlospaco/faster-than-walk#faster-than-walk
- We want to make Open Source faster, better, stronger.


# Requisites

- Python 3.7+
- GCC.
- 64Bit.


# FAQ

- Whats the idea, inspiration, reason, etc ?.

[Feel free to Fork, Clone, Download, Improve, Reimplement, Play with this Open Source. Make it 10 times faster, 10 times smaller.](http://tonsky.me/blog/disenchantment)

- This works with SSL ?.

Yes.

- This works without SSL ?.

Yes.

- This requires Cython ?.

No.

- This runs on PyPy ?.

No.

- This runs on Python2 ?.

I dunno. (Not supported)

- This runs on 32Bit ?.

No.

- This runs with Clang ?.

No.

- How can I Install it ?.

`pip install faster_than_requests`

- Developer Documentation ?.

[Yes.](https://github.com/juancarlospaco/faster-than-requests/raw/master/faster_than_requests_DOCS.zip)
(Zip because GitHub marks the Repo as being JavaScript)

- Where to get help ?.

https://github.com/juancarlospaco/faster-than-requests/issues

- How to set the URL ?.

`url="http://example.com"` (1st argument always).

- How to set the HTTP Method ?.

`http_method="get"` for GET.

`http_method="post"` for POST.

`http_method="put"` for PUT.

`http_method="patch"` for PATCH.

- How to set the HTTP Body ?.

`body="my body"`

- How to set an HTTP Header key=value ?.

`("key", "value")`

- How to set HTTP Proxy ?.

`export https_proxy = "http://yourProxyUrl:8080"`

`export http_proxy =  "http://yourProxyUrl:8080"`

Standard Linux Bash environment variables for proxy.

It will be automatically read from the environment variables.

- Whats NDJSON ?.

https://github.com/ndjson/ndjson-spec

- How can be faster than PyCurl ?.

I dunno.
