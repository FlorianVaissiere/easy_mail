# easy_mail
Easy mail sending using Python3

## Usage
### Without configuration file

From your program, do the following:
```python
header  = 'My mail header'
message = 'This is my mail, sent with Python'

mail = Email('sender@mail.com', 'receiver@mail.com')
mail.prepare(header, message[, type])
mail.send('smtp.server.addr', 'login@mail.com', 'password')
```

### With a configuration file
Define all fields in the config file in `etc/config.json`:
```json
{
    "header"  : "Python3 mail",
    "content" : "This mail is sent with Python3",
    "type"    : "plain",

    "login"     : "",
    "password"  : "",
    "smtp_addr" : "",

    "receiver": "",
    "sender"  : ""
}
```
Then, just use the class method `send_from_source_file()` instead of `Email`:
```python
Email.send_from_source_file()
```
If your configuration file is somewhere else, specify the path as:
```python
Email.send_from_source_file()('my/custom/path/myfile.json')
```
