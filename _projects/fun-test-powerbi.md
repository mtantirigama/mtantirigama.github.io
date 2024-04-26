---
layout: page
title: fun test powerbi
description: md from embed-powerbi
img: assets/img/prof_pic_color.jpg
importance: 2
category: fun
related_publications: false
---

``` python
---
title: "powerbi test"
toc: true # include table of contents
format: 
  html:
    code-fold: true
    code-tools: true
  gfm:
    code-annotations: true
execute:
    echo: false
    freeze: auto 
    # re-render when source changes|true: never re-render 
jupyter: python3
---
```

\#installation \#pip install powerbiclient \#Install nodeJS
(https://nodejs.org/en/) \#pip install ipywidgets \#jupyter labextension
install @jupyter-widgets/jupyterlab-manager

``` python
from powerbiclient.authentication import DeviceCodeLoginAuthentication
from powerbiclient import Report, models
from io import StringIO
from ipywidgets import interact
import requests
import pandas as pd
import matplotlib
```

``` python
# Auth object alternative
#from powerbiclient.authentication import InteractiveLoginAuthentication
#auth = InteractiveLoginAuthentication()
auth = DeviceCodeLoginAuthentication()
```

    Performing device flow authentication. Please follow the instructions below.
    To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code JYGQCUT23 to authenticate.

    Device flow authentication successfully completed.
    You are now logged in .

    The result should be passed only to trusted code in your notebook.

``` python
view_mode=models.EmbedMode.VIEW.value
```

url =
‘https://app.powerbi.com/links/pqHkpoYOLw?ctid=09a10672-822f-4467-a5ba-5bb375967c05&pbi_source=linkShare’
\#url =
‘https://app.powerbi.com/reportEmbed?reportId=9010429c-8899-49e2-bd44-420762415d8b&autoAuth=true&ctid=09a10672-822f-4467-a5ba-5bb375967c05’
\#url =
‘https://app.powerbi.com/groups/me/reports/9010429c-8899-49e2-bd44-420762415d8b/ReportSectioncdcd0719430dfa57b48a?experience=power-bi’

res = requests.get(url) access_token =
res.json()\[‘EmbedToken’\]\[‘Token’\] embed_url =
res.json()\[‘EmbedUrl’\] print(access_token,‘’,embed_url)

``` python
report_id = "9010429c-8899-49e2-bd44-420762415d8b"
report = Report(report_id=report_id, auth=auth)
```

``` python
def loaded_callback(event_details):
    print('Report is loaded')

report.on('loaded', loaded_callback)
```

``` python
def rendered_callback(event_details):
    print('Report is rendered')

report.on('rendered', rendered_callback)
```

## Render report

``` python
report
```

    Report()

``` python
report.set_size(500, 900)
```


