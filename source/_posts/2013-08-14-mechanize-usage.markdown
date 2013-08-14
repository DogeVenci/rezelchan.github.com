---
layout: post
title: "Mechanize Usage"
date: 2013-08-14 11:44
comments: true
categories: [python,crawler]
---
<!--more-->
###Init
``` python
import machanize
import cookielib
import urllib,urllib2

br=mechanize.Browser(history=NoHistroy())
cj=cookielib.LWPCookieJar()
br.set_cookiejar(cj)
br.set_handle_equiv(True)
br.set_handle_gzip(True)
br.set_handle_redirect(True)
br.set_handle_referer(True)
br.set_handle_robots(False)
br.set_handle_refresh(mechanize._http.HTTPRefreshProcessor(), max_time=1)
#br.addheaders = [('User-agent', 'Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.9.0.1) Gecko/2008071615 Fedora/3.0.1-1.fc9 Firefox/3.0.1')]

#debug?
#br.set_debug_http(True)
#br.set_debug_redirects(True)
#br.set_debug_responses(True)
```

###Open URL
``` python
try:
    self.br.open(addr,timeout=15.0)
except Exception,e:
    print 'error open url:',addr,e
    return 

br.response().read()
br.responese().geturl()
br.back() 
br.reload()

```

###Form
``` python
for form in br.forms():
    print form
br.select_form(nr=0)
br.select_form(name="order")
print br.form
br.form['u']="username"
br.form['p']=raw_input("password")
br.submit()
```

###Links
```python
for link in br.links(url_regex="",text_regex=""):
    print link
br.follow_link(link)

```