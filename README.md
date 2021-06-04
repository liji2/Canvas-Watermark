# Canvas Assignment Watermarking

Module:
- Python3.8
- Flask 2.0: Python based web framework that lets you develop web applications.
- PyPDF2: Python library built as PDF toolkit, perform things like creating a new PDF file from scratch or merging two PDF files.
- OAuth2: OAuth2 is a protocol designed to let third-party applications perform actions as a user without getting the user's password. Canvas uses OAuth2 for authentication and authorization of the Canvas API.

Process: 
- Click PDF project in module and then it will redirect to a submit html (same as click the pdf download link), user can submit the original pdf (main.py → asslist.html)
- Canvas send post which contains the formdata about students’ information and original pdf file.  (asslist.html → main.py)
- According to the client ID set before(dev key), use oauth2 to identify and ask for a temporary token to get information from API (main.py)
- API send information to our server and then encrypt the information as watermark(hello.py → water.py)
- Output watermarked pdf (water.py -> hello.py) 
- Server send the file to browser as a download pdf (hello.py -> browser)


