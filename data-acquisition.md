from apiclient.discovery import build
import urllib.request
## saving images
images = []
## performing search query
for i in range(1, 100, 10):
    result = resource.list(q='garage', cx='62a9b993ddbd54792',
                      searchType='image', start=i).execute()
    images += result['items']
## saving filename
for i in range(len(images)):
    filename = "garage_img"
    link = images[i]['link']
    filename +="_" + str(i) + ".jpg"
    urllib.request.urlretrieve(link, filename)
