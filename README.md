#!/usr/bin/python
#coding=utf-8
import smtplib
from email.mime.text import MIMEText
msg_from = '2363743226@qq.com'
passwd = 'dvdfafmsaxrkeaha'
msg_to= '57820048@qq.com'
subject = "2019144150郑宇"
content = "本机：  10.85.68.107  108.162.215.76  校园网：172.68.142.127  220.164.161.128"
msg = MIMEText(content)
msg['Subject'] = subject
msg['From'] = msg_from
msg['To'] = msg_to
try:
    s=smtplib.SMTP_SSL("smtp.qq.com",465)
    s.login(msg_from,passwd)
    s.sendmail(msg_from,msg_to,msg.as_string())
    print("发送成功")
except(s.SMTPException,e):
    print("发送失败")
finally:
    s.quit()
