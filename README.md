# Dhelm Gfeed Python Client Package

Dhelm-gfeed-python-client is a python client library to access and integrate stock market data from  
[Global Financial Datafeeds LLP](https://globaldatafeeds.in/) with your application.

To use this library you must [subscribe](https://globaldatafeeds.in/api/) to web socket api with Global Financial Datafeeds LLP and get your API key and web socket endpoint URL. Programmatic access to data obviously provides better control over your algorithm. You access the raw data from your data provider, then feed into your own application and do whatever analysis you want.

Using Dhelm-gfeed-python-client you can plug data from web socket api into your  application directly.

**For detailed integration and usage guidelines, please read through the [documentation]().**

## Installation
The client is tested with python 3.4+.
###Install from Sources
1. clone the repository:

   git clone https://github.com/kncsolutions/dhelm-gfeed-python-client.git
2. cd to dhelm-gfeed-python-client
3. python setup.py install
## Getting started with the client
```python
from DhelmGfeedClient.gfeedclient import GfeedClient
client = GfeedClient("<ws_url>","<api_key>")
# where,
#<ws_url> : Replace <ws_url> with the web socket url
#<api_key> : Replace <api_key> with your api key which you have got on subscription.

def on_authenticated(base_client):
	#do your staff

#Assign your callbacks. Every callback has some specific functions.
#This callback will be called when user will be authenticated after successful connection.
#Once the user is authenticated then only other predefined methods to access data from web socket can be called from inside this callback.
client.on_authenticated = on_authenticated

#Connect to the web socket. You have to use the predefined methods and callbacks to receive and process data.
client.connect()
```

For deatails of the methods and corresponding callbacks see the documentation.

## How to run the test file
Git clone the repository to your pc.<br/>
Naviagate to the folder **dhelm-gfeed-python-client/example**.<br/>
Open the terminal and type:
```
py test.py <ws_url> <api_key>
```
Replace <ws_url> with the web socket url and <api_key> with your api key.

If you have any query raise an [issue](https://github.com/kncsolutions/dhelm-gfeed-client/issues) or email at developer@kncsolutions.in.
To know about dhelm project visit our project website at https://dhelm.kncsolutions.in