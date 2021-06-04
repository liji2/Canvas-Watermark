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

Process: 
- Click PDF project in module and then it will redirect to a submit html (same as click the pdf download link), user can submit the original pdf (main.py → asslist.html)
- Canvas send post which contains the formdata about students’ information and original pdf file.  (asslist.html → main.py)
- According to the client ID set before(dev key), use oauth2 to identify and ask for a temporary token to get information from API (main.py)
- API send information to our server and then encrypt the information as watermark((main.py → water.py)
- Output watermarked pdf (water.py -> (main.py) 
- Server send the file to browser as a download pdf ((main.py -> browser)


