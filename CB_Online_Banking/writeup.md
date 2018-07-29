# CB_Online_Banking

50 Points

## Question

???

## How I got the flag

Immediately, I knew it was Basic SQL injection. Just have to try everything from commenting, UNION SELECT, or even valued true expressions like 1=1 or 'a'='a'. Then found empty OR values did the trick.

Input as the following fields:
Username: ' or ''='
Password: ' or ''='

It shows me all the users. One of them displayed this:

`username: ninja, password: 5qln1nj4, realname: System Administrator`

Refreshed the page, entered the credentials and got the flag.

CBCTF{SQL_inj3cti0n_101}
