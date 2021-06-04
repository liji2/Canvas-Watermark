# Canvas Assignment Watermarking
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/canvasapi?style=for-the-badge)

## Dependencies
  * BackEnd
    * Python3.6+ --- The operating environment of the server program
    * Flask2.0+  --- Server-side framework
    * Canvasapi --- Access the canvas API through the public key requested by the user
  * Watermarking
    *  Reportlab ---Use OSU's logo and encrypted identification information to generate a watermark
    *  PyPDF2 ---Merge source files and watermark files
  * FrontEnd
    * Canvas LMS --- Learning management system
    * XMLHttpRequest ---Send a watermark request
## Installation
### To Install Python
Please use the official python Interpreter(cpython)!!!!!!! <br>
[Official Download](https://www.python.org/downloads/)
### To Add Requiring Packages
```
  pip install
```
### Configure App On Canvas
#### General
```
Launch URL: https://{host}/upload
Consumer Key: N/A
```
#### Custom Feilds
Reuquire Instructors Get a <b>client ID</b> from <br>Canvas -> Account -> Settings -> Approved Integrations -> "+New Access Token"
```
clientID={Super Secret}
account_id=$Canvas.account.id
base_url=$Canvas.api.baseUrl
course_id = $Canvas.course.id
logo_url=https://oregonstate.edu/themes/osu/homepage/logo.svg
domain=$Canvas.api.domain
group_context_ids=$Canvas.group.contextIds
membership_service_url=$ToolProxyBinding.memberships.url
time_zone=$Person.address.timezone
user_id=$Canvas.user.id

```
### Start
```
python3 main.py

```
### Config
The watermarker allows user customizetheir watermark within certain limits<br>
```
# config.ini
[Default]
alpha = 0.1
Font = Helvetica
FontSize = 14
# Color 0.0 - 1.0
FontColorR = 0.4
FontColorG = 0.5
FontColorB = 0.3
PageWidth = 300
PageHeight = 500
```
We expect that the work of adding watermarks can be further scripted, just like we tried in config.ini.
## Process
- Receive user data as form-data from canvas
- Response a Interface
- Send PDF to server with requested information
- Watermarking PDF with encoded information from user
- Resonse(200) if uploaded
- Send download request from Canvas 
- Send watermarked PDF back
## How To Use 
- Open the course page on Canvas
- Double click the app you created
- Choose a asssignment you wanna watermark
- Upload a file
- Tah Dah!!!!👻👻👻👻👻


