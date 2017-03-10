# Questrade API Python Wrapper
A Python wrapper for Questrade's Restful API


<a href="https://questrade.com"><img src="https://pbs.twimg.com/profile_images/3121643627/ab59bf9e1b51307feb88a4f07727eff1_400x400.png" width="75" height="75" /></a>  [![Python](https://www.python.org/static/community_logos/python-logo.png)](https://www.python.org/)  <a href="https://products.office.com/en-ca/excel"><img src="http://seeklogo.com/images/E/excel-logo-974BFF9CB9-seeklogo.com.png" width="75" height="75" /></a>



[Questrade](http://www.questrade.com/) is a leading Canadian Discount Brokerage with the goal of allowing investors reach their financial independence.

[Python](https://www.python.org/) is a leading programming language with a rich set of packages to analyze financial data.

This package aims to bridge the gap for developers to create pythonic investing applications with Questrade's Restful API.

The development of this project has progressed to a point where most of Questrade's API calls can now be easily made from Python.  It allows Python developers to easily build upon this package and focus on creating trading strategies and algos.  The only outstanding API calls that require Python wrappers are Orders calls used to buy and sell securities.  These will come in time.

### Features
Some of the features this package contains are as follows:

 * OAuth 2.0 API requests via HTTPS (TLS)
 * Wrappers for all Questrade Account and Market calls that automatically handle making authorized requests
 * Optimized calls to request new access tokens via refresh tokens when available
 * Error handling and logging
 * Streaming quotes
 * [xlwings] User Defined Functions (UDFs) that can call all Python wrapped Questrade API's from within Microsoft Excel
 * A local SQLite database to locally store symbol ids as to minimize API callouts when possible so that rate limits are not hit


### How it works
Questrade REST APIs require an access token to be obtained from their servers first before making any subequent API requests.  This package automatically handles that for you whenever one of the Python wrapped Questrade APIs is called.  The initial access token can only be retrieved through the OAuth2 handshake.  Therefore, if your machine has not yet retrieved an access token, it will launch a web browser directed at the Questrade login page where you will have to enter your Questrade Id and password.  You'll then be prompted to accept the Authorization Request to receive your initial access token from Questrade.  Once the access token is retrieved, the intended Questrade API call will then occur.  Subsequest API calls will then automatically refresh the access token whenever needed to avoid having to re-enter a Questrade Id and password.

You can also obtain your initial access token manually by following these steps:
 1. Point your web browser to ~~[https://n0mq97v6uj.execute-api.us-east-1.amazonaws.com/dev/authorize~](https://n0mq97v6uj.execute-api.us-east-1.amazonaws.com/dev/authorize)~~ See [Issue #1](https://github.com/pcinat/QuestradeAPI_PythonWrapper/issues/1)
 2. Login with your Questrade credentials
 3. Accept the Authorization Request to receive an access token from Questrade.

The above steps are programmatically followed when leveraging the Python API wrappers in this package.


### Getting Started
This package contains two getting started modules to help you get more familiar with how you can leverage the Python wrapped Questrade API calls.
 1. Module `getting_started_access_tokens.py` walks through an example of how access tokens and refresh tokens are retrieved in this package. Although access tokens are automatically retrieved when making Python wrapped Questrade API calls, it is useful to be  knowledgeable with how this package handles it.
 2. Module `getting_started_api_calls` walks through an example of how Python wrapped Questrade API calls are made.

Once you see how easy it is to make Questrade API calls through this Python package, you can build upon it and concentrate on developing your own trading strategies and algos.


### Requirements
 - Python 2.7.11 - Note that 2.7 is used because of the extensive financial packages that exist for Python 2.7 as opposed to 3.5
 - Questrade user account


### Operating Systems
This package has been tested to work on Windows 7 and above.  Most of the features will also work on Mac OS X and Linux operating systems but have not been tested as of yet.


### Development Setup
Eclipse [PyDev] was used as the primary IDE.

[virtualenv] was also integrated with this project in PyDev.  Once you have Python 2.7 installed and your virtualenv activated, enter the following command to download and install all the required Python dependencies that are needed.

`pip install -r requirements.txt`


### Technologies
Some of the technologies leveraged in this project are the following:

 - numpy
 - pandas
 - Flask
 - AWS Lambda + API Gateway
 - OAuth2
 - Zappa
 - requests
 - WebSockets
 - Selenium
 - Twisted
 - Threading
 - xlwings
 - ctypes
 - SQLite
 - RTD (real-time data for Excel)
 
    Note: An efficient RTD Server was created in another project to integrate real-time data from Python, or any other COM applications, into Excel.  You can learn more about that project at [Message Queue RTD Server](https://github.com/pcinat/MessageQueueRTDServer)



### License
Licensed under the Apache License, Version 2.0 (the "License"). You may obtain a copy of the License at:

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the License for the specific language governing permissions and limitations under the License.


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [xlwings]: <https://www.xlwings.org/>
   [PyDev]: <http://www.pydev.org/>
   [virtualenv]: <http://docs.python-guide.org/en/latest/dev/virtualenvs/>
   
