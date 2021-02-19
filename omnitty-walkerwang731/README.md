### omnitty-walkerwang731
Base on omnitty-g112wdh

support
1. UTF8
2. resize windows
3. replace `/usr/bin/ssh` to `/usr/local/bin/omnittyssh`, ensure to you can customsize your script, if use ssh please create a soft link, such as `ln -sv /usr/bin/ssh /usr/local/bin/omnittyssh`, if you use customsized scriptes(such as not use 22 port or other action what you want) omnitty will call `{script} $1`
4. adjust summary window color to `0x90`(red) from `0x80`(grey) that ensure to clearer, and avoid occurred special TTY not display issue
