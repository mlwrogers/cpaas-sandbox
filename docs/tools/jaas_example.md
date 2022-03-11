---
layout: default
title: JaaS example
parent: JaaS
nav_order: 1
---

JaaS example page placeholder


    <!DOCTYPE html>
    <html>
      <head>
        <script src='https://8x8.vc/external_api.js' async></script>
        <style>html, body, #jaas-container { height: 100%; }</style>
        <script type="text/javascript">
          window.onload = () => {
            const api = new JitsiMeetExternalAPI("8x8.vc", {
              roomName: "vpaas-magic-cookie-501874befda74dfd9a8911820dc4274a/SampleAppTopDictionariesTimeSadly",
              parentNode: document.querySelector('#jaas-container'),
							jwt: "eyJraWQiOiJ2cGFhcy1tYWdpYy1jb29raWUtNTAxODc0YmVmZGE3NGRmZDlhODkxMTgyMGRjNDI3NGEvODJjYWE0LVNBTVBMRV9BUFAiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiJqaXRzaSIsImV4cCI6MTY0NzAxODIzMSwibmJmIjoxNjQ3MDExMDI2LCJpc3MiOiJjaGF0Iiwicm9vbSI6IioiLCJzdWIiOiJ2cGFhcy1tYWdpYy1jb29raWUtNTAxODc0YmVmZGE3NGRmZDlhODkxMTgyMGRjNDI3NGEiLCJjb250ZXh0Ijp7ImZlYXR1cmVzIjp7ImxpdmVzdHJlYW1pbmciOmZhbHNlLCJvdXRib3VuZC1jYWxsIjpmYWxzZSwic2lwLW91dGJvdW5kLWNhbGwiOmZhbHNlLCJ0cmFuc2NyaXB0aW9uIjpmYWxzZSwicmVjb3JkaW5nIjpmYWxzZX0sInVzZXIiOnsibW9kZXJhdG9yIjp0cnVlLCJuYW1lIjoiVGVzdCBVc2VyIiwiaWQiOiJhdXRoMHw2MDVjYmNmNzRlNTJkNjAwNjlhNGE5MmQiLCJhdmF0YXIiOiIiLCJlbWFpbCI6InRlc3QudXNlckBjb21wYW55LmNvbSJ9fX0.fNWHoe4sztVMEJNwJb9WrT2883nuGI2wKCe5HajD1Rvky7hsA81XpK_7jWmNdug9ZVoLgOFiMEmNW-nGkmw8O6dnEFcnv7YL_-KIyunYBAHCTKf6vgUqPRBzOjah0P8_rDfGD5z6MO0U-l1G-PD65gztRokiy1pD6bPRnjziFGPutxwIkYNbNNZBMjz0D5OzP5SoWKDIVMDmxk5rSjDd9-8_xa-xnm55LgrL2mYYssvHomLSaiZuVpCixZvKua_btXSf7u3SRY3KzulII_qW9fVQwR9Vdu0NSzCum-D2Gzh8DXb_Cb-U5af5VdZv5DybN2IGRD4HllWYoqO1EKyrPA"
            });
          }
        </script>
      </head>
      <body><div id="jaas-container" /></body>
    </html>
  
