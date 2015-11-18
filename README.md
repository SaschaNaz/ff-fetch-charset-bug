# ff-fetch-charset-bug
Reproducing [Firefox Fetch API charset bug](https://bugzilla.mozilla.org/show_bug.cgi?id=1206751) which breaks UTF-16 texts.

_NOTE_: It seems this is not a bug but is [by design](https://bugzilla.mozilla.org/show_bug.cgi?id=1206751). 

### How to run

  1. Get Git and Node.js

  2. Install and run server

    ```
    git clone https://github.com/SaschaNaz/ff-fetch-charset-bug.git
    cd ff-fetch-charset-bug
    node install .
    node fileserver.js
    ```
  
  3. Access `//localhost:8080` with Firefox

### Expected output

```
Result with XHR: 미무라카나코三村かな子
Result with Fetch: 미무라카나코三村かな子
```

### Output with Firefox 40.0.3 / Nightly 43.0a1 (2015-09-20)

```
Result with XHR: 미무라카나코三村かな子
Result with Fetch: ����4�|�tΘ�T� NQgK0j0P[ 
```
* Being reproduced in Windows 10 build 10240 and OS X 10.10.4
