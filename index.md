<img src="image/yahoo-ganga.JPG" alt="">


## Ganga Swap Image

I'm sharing here a piece of code that will be useful for all those who do image swapping on email (desktop image / mobile image). The **hybrid email template** already allows you to have an email body that fits on email clients that don't accept media queries. The columns are placed one below the other, and the display is that of a mobile phone. This is the **advantage over a responsive version** which will always display a desktop version on these mobiles (ganga, yahoo). However, there is still one problem to solve, the impossibility of displaying a mobile image on these recalcitrant clients. Ganga and yahoo always displayed the desktop image.<br/>
Thanks to Mark Robbins genius (see [here](https://github.com/hteumeuleu/email-bugs/issues/95), I finally managed to create an image swap that works, so that all mobile mail clients where media queries are not accepted will now display the mobile image !! . This code can certainly be simplified, optimized, : out of more than 80 mailboxes (according to testi@) only two are still problematic : **Zimbra**, which doesn't display any image at all (neither desktop nor mobile) and **wall! mail** which still displays the mobile version in desktop... 


### The code 

Here is the application of this technique using conditional comments <!--Yahoo-GANGA-><!yahoo-GANGA--> in a classic hybrid email template.

```

<html lang="fr" xml:lang="fr" xmlns="http://www.w3.org/1999/xhtml" xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office">

<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="x-apple-disable-message-reformatting">
<meta name="format-detection" content="telephone=no,address=no,email=no,date=no,url=no">
<meta name="color-scheme" content="light">
<meta name="supported-color-schemes" content="light">
<title></title>
    <!--[if (gte mso 9)|(IE)]>
<style>
* {
font-family: Arial, sans-serif !important;
}
</style>
<![endif]-->
<!-- CSS Reset : BEGIN -->
<style>
 :root {
    color-scheme: light;
    supported-color-schemes: light;
}
html,
body {
    margin: 0 auto !important;
    padding: 0 !important;
    height: 100% !important;
    width: 100% !important;
}
div[style*="margin: 16px 0"] {
    margin: 0 !important;
}
table,
td {
    mso-table-lspace: 0pt !important;
    mso-table-rspace: 0pt !important;
}
table {
    border-spacing: 0 !important;
    border-collapse: collapse !important;
    table-layout: fixed !important;
    margin: 0 auto !important;
}
img.g-img+div {
    display: none !important;
}

</style>
<style>
a {
    text-decoration: none;
}
a[x-apple-data-detectors] {
    color: inherit !important;
    text-decoration: none !important;
    font-size: inherit !important;
    font-family: inherit !important;
    font-weight: inherit !important;
    line-height: inherit !important;
}

u+#body a {
    color: inherit;
    text-decoration: none;
    font-size: inherit;
    font-family: inherit;
    font-weight: inherit;
    line-height: inherit;
}

#MessageViewBody a {
    color: inherit;
    text-decoration: none;
    font-size: inherit;
    font-family: inherit;
    font-weight: inherit;
    line-height: inherit;
}
</style>
<style>
   /* iPhone 4, 4S, 5, 5S, 5C, and 5SE */
   @media only screen and (min-device-width: 320px) and (max-device-width: 374px) {
      u ~ div .email-container {
         min-width: 320px !important;
      }
   }
   /* iPhone 6, 6S, 7, 8, and X */
   @media only screen and (min-device-width: 375px) and (max-device-width: 413px) {
      u ~ div .email-container {
         min-width: 375px !important;
      }
   }
   /* iPhone 6+, 7+, and 8+ */
   @media only screen and (min-device-width: 414px) {
      u ~ div .email-container {
         min-width: 414px !important;
      }
   }
   @media screen and (-webkit-min-device-pixel-ratio: 0) {
      table[class="button"]:hover {
         opacity: 0.8;
      }
   }
   u + .body .glist { margin-left: 0 !important; }
   @media only screen and (max-width: 680px) {
      u + .body .glist { margin-left: 25px !important; }
   }
</style>
<!--[if gte mso 9]>
<xml>
<o:OfficeDocumentSettings>
<o:AllowPNG/>
<o:PixelsPerInch>96</o:PixelsPerInch>
</o:OfficeDocumentSettings>
</xml>
<![endif]-->
<style>
.btn-td,
.btn-a {
    transition: all 100ms ease-in;
}

.btn-td-primary:hover,
.btn-a-primary:hover {
    background: #646464 !important;
    border-color: #646464 !important;
}

.m-content {
    display: none !important;
    max-height: none !important;
    mso-hide: all;
}
  @media screen and (min-width:680px){


.d-content{
        display: block!important;
        width: auto !important;
        max-height: 100% !important;
        overflow: visible!important;
        height: 100% !important;
    }
}
  
      
   
@media screen and (max-width: 680px) {
    .cc-column,
    .cc-column-center {
        display: block !important;
        width: 100% !important;
        max-width: 100% !important;
        direction: ltr !important;
    }
    .cc-column table {
        height: auto !important;
    }
    .cc-column img {
        max-width: 100% !important
    }
    .cc-column-center {
        text-align: center !important;
    }
    .d-content {
        display: none !important;
    }
    .m-content {
        display: block!important;
        width: auto !important;
        max-height: 100% !important;
        overflow: visible!important;
        height: 100% !important;
    }
    .center-on-narrow {
        text-align: center !important;
        display: block !important;
        margin-left: auto !important;
        margin-right: auto !important;
        float: none !important;
    }
    table.center-on-narrow {
        display: inline-block !important;
    }
}
</style>


<!-- force banner height on samsung BEGIN-->
<style>
#MessageViewBody .samsung{
    height:238px !important;
}
</style>
<!-- force banner height on samsung END-->

<!-- restore desktop image and hide mobile image on Yahoo Aol Yandex  BEGIN-->
<style>
.YahooDesktop{
        display:block !important;
        border:5px solid blue!important;
    }
.YahooGangaMobile {
    display: none!important;
    max-height: none!important;
    mso-hide: all!important;
}
</style>


<!--[if (gte mso 9)|(IE)]>
<style type="text/css">
table {border-collapse: collapse;}
</style>
<![endif]-->
</head>
<body style="margin: 0px; background-color: #F2F2F2; padding: 0px !important;">

    <center role="article" aria-roledescription="email" lang="fr" style="width: 100%;background-color: #F2F2F2;">
        <!--[if (gte mso 9)|(IE)]>
        <table role="presentation" border="0" cellpadding="0" cellspacing="0" width="100%" style="background-color: #F2F2F2;">
        <tr>
        <td>
        <![endif]-->
        <!-- Texte de pré-en-tête masqué visuellement : BEGIN -->
        <div style="max-height:0; overflow:hidden; mso-hide:all;" aria-hidden="true">
        </div>

        <div style="display: none; font-size: 1px; line-height: 1px; max-height: 0px; max-width: 0px; opacity: 0; overflow: hidden; mso-hide: all; font-family: sans-serif;">&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;</div>
        <div style="max-width: 680px; margin: 0 auto;" class="email-container">
            <!--[if (gte mso 9)|(IE)]>
            <table align="center" border="0" cellspacing="0" cellpadding="0" width="680" role="presentation">
            <tr>
            <td align="center" valign="top">
            <![endif]-->
            <!-- Email Body : BEGIN -->
            <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%" style="margin: auto;">
               

               
            <!-- Email Header : END -->
              <tr>
                    <td align="center" class="d-content">
                                   
					<!--Yahoo-GANGA-> 
					  <div style="display:none;" class="YahooDesktop">
					<!yahoo-GANGA-->
					    <img src="https://via.placeholder.com/600x400?text=Classic Desktop image" width="680" alt="" border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px;color: #646464; margin: auto; display:block" class="cc-column-center">					               
					<!--Yahoo-GANGA-> 
					  </div>
					   
                       <div class="YahooGangaMobile">
                    		<a href="https://www.ibm.com/" target="_blank" style="display:block; -webkit-text-size-adjust: 100%; -ms-text-size-adjust: 100%; color: #646464 ; text-decoration: none;">
                        		<img alt="" src="https://via.placeholder.com/680x400?text=GANGA MOBILE IMAGE" border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px; color: #646464;" class="center-on-narrow">
                    		</a>
                       </div>
					<!yahoo-GANGA-->
                    </td>
                </tr>


                <!--[if !mso]><!-->             
                <tr>
                    <td class="m-content samsung" style="text-align: center; width: 0; height: 0; overflow: hidden; float: none; mso-hide: all; background-color: #ffffff; display: none; max-height: 0px;border:5px solid red">
                        <a href="https://www.ibm.com/" target="_blank" style="display:block; -webkit-text-size-adjust: 100%; -ms-text-size-adjust: 100%; color: #646464 ; text-decoration: none;">
                        <img alt="" src="https://via.placeholder.com/680x400?text=classic Mobile image" width="340" border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px; color: #646464;display:none" class="center-on-narrow"></a>
                    </td>
                </tr>
                <!--<![endif]-->
   

                <!-- 2 Even Columns : BEGIN -->
                <tr>
                    <td align="left" valign="top" style="font-size:0; padding: 10px; background-color: #ffffff;">
                        <!--[if (gte mso 9)|(IE)]>
                        <table role="presentation" border="0" cellspacing="0" cellpadding="0" width="660">
                        <tr>
                        <td valign="top" width="330">
                        <![endif]-->
                        <div style="display:inline-block; margin: 0 -1px; width:100%; min-width:200px; max-width:330px; vertical-align:top;" class="cc-column">
                            <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                                <tr>

                                    <td align="left" style="padding: 10px;">
                                        <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%" style="font-size: 14px; text-align: left;">
                                            <tr>
                                                <td valign="top" align="left" style="font-family: 'Arial', sans-serif;font-size:14px;mso-line-height-rule: exactly; line-height: 21px;color:#646464;">
                                                    <p style="margin:0;">
                                                        <strong>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vel, sequi?</strong>
                                                    </p>
                                                </td>
                                            </tr>
                                            <tr>
                                                <td style="padding-top: 10px;font-family: Arial, sans-serif; font-size:14px;  mso-line-height-rule: exactly;line-height: 21px;  color: #646464;text-align:left">
                                                    <p style="margin: 0;">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eius enim labore earum perspiciatis. Officiis sit facilis obcaecati optio consequuntur sunt iusto cumque aliquam voluptates. Esse, quibusdam
                                                        officiis? Est corporis rerum vitae ipsa unde nesciunt cum reprehenderit, libero accusamus facere consequatur. <strong style="color: #525ca3;">Lorem, ipsum.</strong> Lorem ipsum dolor sit amet consectetur
                                                    adipisicing elit. Assumenda ex nesciunt eos harum doloribus natus ab, veniam rerum.</p>

                                                </td>
                                            </tr>

                                        </table>
                                    </td>
                                </tr>
                            </table>
                        </div>
                        <!--[if (gte mso 9)|(IE)]>
                        </td>
                        <td valign="top" width="330">
                        <![endif]-->
                        <div style="display: inline-block; margin: 0 -1px; width: 100%; min-width: 200px; max-width: 330px; vertical-align: top;" class="cc-column">
                            <table align="center" role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                                <tr>
                                    <td align="center" valign="top" style="padding:10px;">
                                        <a href="https://www.intel.com/" target="_blank">
                                            <img alt="" src="https://picsum.photos/640/430" width="320" border="0" style="width: 100%; max-width: 320px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px;color: #646464;" class="center-on-narrow">
                                        </a>
                                    </td>
                                </tr>
                            </table>
                        </div>
                        <!--[if (gte mso 9)|(IE)]>
                        </td>
                        </tr>
                        </table>
                    <![endif]-->
                </td>
            </tr>
            <!-- 2 Even Columns : END -->
            <tr>
                <td align="center" style="padding: 10px;background-color: #ffffff;">
                    <!-- Button : BEGIN -->
                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" style="margin: auto;">
                        <tr>
                            <td class="btn-td btn-td-primary" style="border-radius: 30px; background: #525ca3;text-align:center">
                                <a class="btn-a btn-a-primary" href="https://google.com/" style="border: 1px solid #525ca3; font-family: Arial,sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 14px; text-decoration: none; padding: 10px 31px; color: #ffffff; font-weight:bold;display: block; border-radius: 30px;"><strong>lCal ot ncatoi</strong></a>
                            </td>
                        </tr>
                    </table>
                    <!-- Button : END -->
                </td>
            </tr>

            <tr>
                <td align="center" valign="top" style="font-size:0; padding: 10px; background-color: #ffffff;">

                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                        <tr>
                            <td style="padding:10px; font-family: Arial, sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 21px; color: #646464;text-align:left">
                                <p style="margin:0">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reiciendis ipsum nihil similique culpa molestias. Culpa laborum reiciendis incidunt sint eos dolores mollitia minus nam amet repudiandae. Quos perferendis consequatur
                                esse sunt quisquam veritatis eveniet at, distinctio inventore voluptate.</p>
                            </td>
                        </tr>
                    </table>

                </td>
            </tr>


            <!-- 1 Column Text + Button : BEGIN -->
            <tr>
                <td style="background-color: #ffffff;">
                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                        <tr>
                            <td style="padding:20px">
                                <table align="left" role="presentation" cellspacing="0" cellpadding="0" border="0" style="margin: auto;">
                                    <tr>
                                        <td align="center" valign="middle">

                                            <img src="https://picsum.photos/100/120" alt="" width="100" height="120" border="0" style="width:100px;height:120px;display:block">
                                        </td>
                                        <td align="center" valign="middle" style="border-left:2px solid #525ca3;padding-left:10px;font-family: Arial,sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 17px;text-align:left;color:#525ca3;word-break: break-word;">
                                            <p style="margin: 0 0 4px;font-size:16px;mso-line-height-rule: exactly;line-height: 18px;text-transform:uppercase"><strong>Lorem, ipsum.</strong></p>
                                            <p style="margin:0 0 3px;font-size:16px;mso-line-height-rule: exactly;line-height: 18px;"><a style="color:#525ca3;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%;" href="https://www.apple.com/">Lorem, ipsum dolor.</a></p>
                                            <p style="margin:0 0 3px"><a style="color:#525ca3;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%;" href="https://www.redhat.com/" target="_blank">Lorem, ipsum dolor.</a></p>
                                            <p style="margin:0">Lorem ipsum dolor sit.</p>
                                        </td>
                                    </tr>
                                </table>
                            </td>
                        </tr>
                    </table>
                </td>
            </tr>



       
        </table>
        <!-- Email Body : END -->
            <!--[if (gte mso 9)|(IE)]>
</td>
</tr>
</table>
<![endif]-->
</div>
        <!--[if (gte mso 9)|(IE)]>
</td>
</tr>
</table>
<![endif]-->
</center>

</body>

</html>

```

### Explanations


1-the desktop image will show everywhere apart from Yahoo, AOL, GANGA where it will be hidden by <div style="display:none"> 
2-YahooDesktop class in the head restore the desktop image on yahoo AOL and Yandex webmails
2-the YahooGangaMobile mobile image will be displayed on ganga and yahoo android. So here we'll have two image, desktop and mobile.It will also appear on webmail , Zimbra and Wall!Mail
To hide it, we use embed css in the head. But as Zimbra is displaying  the mobile image, this client is the only one where there will be no image .*/

### Second test
    
Here is an example of image swap that works on 100% of emails tested on testi@ . This example can be used as a basis to display your mobile images even on Gmail IMAP, and Yahoo android which usually do not accept media queries!  

In this example, Yandex Yahoo AOL and Zimbra will display the ganga mobile image 

    
*/
```  
<html lang="fr" xml:lang="fr" xmlns="http://www.w3.org/1999/xhtml" xmlns:v="urn:schemas-microsoft-com:vml" xmlns:o="urn:schemas-microsoft-com:office:office">

<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="x-apple-disable-message-reformatting">
<meta name="format-detection" content="telephone=no,address=no,email=no,date=no,url=no">
<meta name="color-scheme" content="light">
<meta name="supported-color-schemes" content="light">
<title></title>
    <!--[if (gte mso 9)|(IE)]>
<style>
* {
font-family: Arial, sans-serif !important;
}
</style>
<![endif]-->
<!-- CSS Reset : BEGIN -->
<style>
 :root {
    color-scheme: light;
    supported-color-schemes: light;
}
html,
body {
    margin: 0 auto !important;
    padding: 0 !important;
    height: 100% !important;
    width: 100% !important;
}
div[style*="margin: 16px 0"] {
    margin: 0 !important;
}
table,
td {
    mso-table-lspace: 0pt !important;
    mso-table-rspace: 0pt !important;
}
table {
    border-spacing: 0 !important;
    border-collapse: collapse !important;
    table-layout: fixed !important;
    margin: 0 auto !important;
}
img.g-img+div {
    display: none !important;
}

</style>
<style>
a {
    text-decoration: none;
}
a[x-apple-data-detectors] {
    color: inherit !important;
    text-decoration: none !important;
    font-size: inherit !important;
    font-family: inherit !important;
    font-weight: inherit !important;
    line-height: inherit !important;
}

u+#body a {
    color: inherit;
    text-decoration: none;
    font-size: inherit;
    font-family: inherit;
    font-weight: inherit;
    line-height: inherit;
}

#MessageViewBody a {
    color: inherit;
    text-decoration: none;
    font-size: inherit;
    font-family: inherit;
    font-weight: inherit;
    line-height: inherit;
}
</style>
<style>
   /* iPhone 4, 4S, 5, 5S, 5C, and 5SE */
   @media only screen and (min-device-width: 320px) and (max-device-width: 374px) {
      u ~ div .email-container {
         min-width: 320px !important;
      }
   }
   /* iPhone 6, 6S, 7, 8, and X */
   @media only screen and (min-device-width: 375px) and (max-device-width: 413px) {
      u ~ div .email-container {
         min-width: 375px !important;
      }
   }
   /* iPhone 6+, 7+, and 8+ */
   @media only screen and (min-device-width: 414px) {
      u ~ div .email-container {
         min-width: 414px !important;
      }
   }
   @media screen and (-webkit-min-device-pixel-ratio: 0) {
      table[class="button"]:hover {
         opacity: 0.8;
      }
   }
   u + .body .glist { margin-left: 0 !important; }
   @media only screen and (max-width: 680px) {
      u + .body .glist { margin-left: 25px !important; }
   }
</style>
<!--[if gte mso 9]>
<xml>
<o:OfficeDocumentSettings>
<o:AllowPNG/>
<o:PixelsPerInch>96</o:PixelsPerInch>
</o:OfficeDocumentSettings>
</xml>
<![endif]-->
<style>
.btn-td,
.btn-a {
    transition: all 100ms ease-in;
}

.btn-td-primary:hover,
.btn-a-primary:hover {
    background: #646464 !important;
    border-color: #646464 !important;
}

.m-content {
    display: none !important;
    max-height: none !important;
    mso-hide: all;
}
  @media screen and (min-width:680px){


.d-content{
        display: block!important;
        width: auto !important;
        max-height: 100% !important;
        overflow: visible!important;
        height: 100% !important;
    }
}
  
      
   
@media screen and (max-width: 680px) {
    .cc-column,
    .cc-column-center {
        display: block !important;
        width: 100% !important;
        max-width: 100% !important;
        direction: ltr !important;
    }
    .cc-column table {
        height: auto !important;
    }
    .cc-column img {
        max-width: 100% !important
    }
    .cc-column-center {
        text-align: center !important;
    }
    .d-content {
        display: none !important;
    }
    .m-content {
        display: block!important;
        width: auto !important;
        max-height: 100% !important;
        overflow: visible!important;
        height: 100% !important;
    }
    .center-on-narrow {
        text-align: center !important;
        display: block !important;
        margin-left: auto !important;
        margin-right: auto !important;
        float: none !important;
    }
    table.center-on-narrow {
        display: inline-block !important;
    }
}
</style>


<!-- force banner height on samsung BEGIN-->
<style>
#MessageViewBody .samsung{
    height:238px !important;
}
</style>
<!-- force banner height on samsung END-->


<!-- show mobile image on Yahoo Aol Zimbra wall!mail BEGIN-->
<style>
.ZimbraYahooGanga{
        display:block!important;
        border:5px solid blue!important;
    }

</style>
<!-- show ganga desktop image on Yahoo Aol END-->


<!--[if (gte mso 9)|(IE)]>
<style type="text/css">
table {border-collapse: collapse;}
</style>
<![endif]-->
</head>
<body style="margin: 0px; background-color: #F2F2F2; padding: 0px !important;">
    <center role="article" aria-roledescription="email" lang="fr" style="width: 100%;background-color: #F2F2F2;">
        <!--[if (gte mso 9)|(IE)]>
        <table role="presentation" border="0" cellpadding="0" cellspacing="0" width="100%" style="background-color: #F2F2F2;">
        <tr>
        <td>
        <![endif]-->
        <!-- Texte de pré-en-tête masqué visuellement : BEGIN -->
        <div style="max-height:0; overflow:hidden; mso-hide:all;" aria-hidden="true">
        </div>

        <div style="display: none; font-size: 1px; line-height: 1px; max-height: 0px; max-width: 0px; opacity: 0; overflow: hidden; mso-hide: all; font-family: sans-serif;">&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;&zwnj;&nbsp;</div>
        <div style="max-width: 680px; margin: 0 auto;" class="email-container">
            <!--[if (gte mso 9)|(IE)]>
            <table align="center" border="0" cellspacing="0" cellpadding="0" width="680" role="presentation">
            <tr>
            <td align="center" valign="top">
            <![endif]-->
            <!-- Email Body : BEGIN -->
            <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%" style="margin: auto;">
            <!-- Email Header : END -->
              <tr>
                    <td align="center" class="d-content">
                    <!--Yahoo-GANGA-> 
                    <div style="display:none;">
                    <!yahoo-GANGA-->
                    <img src="https://via.placeholder.com/600x400?text=Classic Desktop image" width="680" alt="" border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px;color: #646464; margin: auto; display:block" class="cc-column-center">
                    <!--Yahoo-GANGA-> 
                    </div>
                    <!yahoo-GANGA-->
                        
                    <!--Yahoo-GANGA->
                    <div style="border:5px solid green" class="ZimbraYahooGanga">  
                    <a href="https://www.ibm.com/" target="_blank" style="display:block; -webkit-text-size-adjust: 100%; -ms-text-size-adjust: 100%; color: #646464 ; text-decoration: none;">
                        <img alt="" src="https://via.placeholder.com/680x400?text=zimbra and ganga image"  border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px; color: #646464;" class="center-on-narrow"></a></div>
                    <!yahoo-GANGA-->
                    </td>
                </tr>


                <!--[if !mso]><!-->             
                <tr>
                    <td class="m-content samsung" style="text-align: center; width: 0; height: 0; overflow: hidden; float: none; mso-hide: all; background-color: #ffffff; display: none; max-height: 0px;border:5px solid red">
                        <a href="https://www.ibm.com/" target="_blank" style="display:block; -webkit-text-size-adjust: 100%; -ms-text-size-adjust: 100%; color: #646464 ; text-decoration: none;">
                        <img alt="" src="https://via.placeholder.com/680x400?text=classic Mobile image" width="340" border="0" style="width: 100%; max-width: 680px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px; color: #646464;display:none" class="center-on-narrow"></a>
                    </td>
                </tr>
                <!--<![endif]-->
   

                <!-- 2 Even Columns : BEGIN -->
                <tr>
                    <td align="left" valign="top" style="font-size:0; padding: 10px; background-color: #ffffff;">
                        <!--[if (gte mso 9)|(IE)]>
                        <table role="presentation" border="0" cellspacing="0" cellpadding="0" width="660">
                        <tr>
                        <td valign="top" width="330">
                        <![endif]-->
                        <div style="display:inline-block; margin: 0 -1px; width:100%; min-width:200px; max-width:330px; vertical-align:top;" class="cc-column">
                            <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                                <tr>

                                    <td align="left" style="padding: 10px;">
                                        <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%" style="font-size: 14px; text-align: left;">
                                            <tr>
                                                <td valign="top" align="left" style="font-family: 'Arial', sans-serif;font-size:14px;mso-line-height-rule: exactly; line-height: 21px;color:#646464;">
                                                    <p style="margin:0;">
                                                        <strong>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vel, sequi?</strong>
                                                    </p>
                                                </td>
                                            </tr>
                                            <tr>
                                                <td style="padding-top: 10px;font-family: Arial, sans-serif; font-size:14px;  mso-line-height-rule: exactly;line-height: 21px;  color: #646464;text-align:left">
                                                    <p style="margin: 0;">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eius enim labore earum perspiciatis. Officiis sit facilis obcaecati optio consequuntur sunt iusto cumque aliquam voluptates. Esse, quibusdam
                                                        officiis? Est corporis rerum vitae ipsa unde nesciunt cum reprehenderit, libero accusamus facere consequatur. <strong style="color: #525ca3;">Lorem, ipsum.</strong> Lorem ipsum dolor sit amet consectetur
                                                    adipisicing elit. Assumenda ex nesciunt eos harum doloribus natus ab, veniam rerum.</p>

                                                </td>
                                            </tr>

                                        </table>
                                    </td>
                                </tr>
                            </table>
                        </div>
                        <!--[if (gte mso 9)|(IE)]>
                        </td>
                        <td valign="top" width="330">
                        <![endif]-->
                        <div style="display: inline-block; margin: 0 -1px; width: 100%; min-width: 200px; max-width: 330px; vertical-align: top;" class="cc-column">
                            <table align="center" role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                                <tr>
                                    <td align="center" valign="top" style="padding:10px;">
                                        <a href="https://www.intel.com/" target="_blank">
                                            <img alt="" src="https://picsum.photos/640/430" width="320" border="0" style="width: 100%; max-width: 320px; height: auto; background: #ffffff; font-family: Arial, sans-serif; font-size:14px;color: #646464;" class="center-on-narrow">
                                        </a>
                                    </td>
                                </tr>
                            </table>
                        </div>
                        <!--[if (gte mso 9)|(IE)]>
                        </td>
                        </tr>
                        </table>
                    <![endif]-->
                </td>
            </tr>
            <!-- 2 Even Columns : END -->
            <tr>
                <td align="center" style="padding: 10px;background-color: #ffffff;">
                    <!-- Button : BEGIN -->
                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" style="margin: auto;">
                        <tr>
                            <td class="btn-td btn-td-primary" style="border-radius: 30px; background: #525ca3;text-align:center">
                                <a class="btn-a btn-a-primary" href="https://google.com/" style="border: 1px solid #525ca3; font-family: Arial,sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 14px; text-decoration: none; padding: 10px 31px; color: #ffffff; font-weight:bold;display: block; border-radius: 30px;"><strong>lCal ot ncatoi</strong></a>
                            </td>
                        </tr>
                    </table>
                    <!-- Button : END -->
                </td>
            </tr>

            <tr>
                <td align="center" valign="top" style="font-size:0; padding: 10px; background-color: #ffffff;">

                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                        <tr>
                            <td style="padding:10px; font-family: Arial, sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 21px; color: #646464;text-align:left">
                                <p style="margin:0">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Reiciendis ipsum nihil similique culpa molestias. Culpa laborum reiciendis incidunt sint eos dolores mollitia minus nam amet repudiandae. Quos perferendis consequatur
                                esse sunt quisquam veritatis eveniet at, distinctio inventore voluptate.</p>
                            </td>
                        </tr>
                    </table>

                </td>
            </tr>


            <!-- 1 Column Text + Button : BEGIN -->
            <tr>
                <td style="background-color: #ffffff;">
                    <table role="presentation" cellspacing="0" cellpadding="0" border="0" width="100%">
                        <tr>
                            <td style="padding:20px">
                                <table align="left" role="presentation" cellspacing="0" cellpadding="0" border="0" style="margin: auto;">
                                    <tr>
                                        <td align="center" valign="middle">

                                            <img src="https://picsum.photos/100/120" alt="" width="100" height="120" border="0" style="width:100px;height:120px;display:block">
                                        </td>
                                        <td align="center" valign="middle" style="border-left:2px solid #525ca3;padding-left:10px;font-family: Arial,sans-serif; font-size:14px; mso-line-height-rule: exactly;line-height: 17px;text-align:left;color:#525ca3;word-break: break-word;">
                                            <p style="margin: 0 0 4px;font-size:16px;mso-line-height-rule: exactly;line-height: 18px;text-transform:uppercase"><strong>Lorem, ipsum.</strong></p>
                                            <p style="margin:0 0 3px;font-size:16px;mso-line-height-rule: exactly;line-height: 18px;"><a style="color:#525ca3;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%;" href="https://www.apple.com/">Lorem, ipsum dolor.</a></p>
                                            <p style="margin:0 0 3px"><a style="color:#525ca3;-webkit-text-size-adjust:100%;-ms-text-size-adjust:100%;" href="https://www.redhat.com/" target="_blank">Lorem, ipsum dolor.</a></p>
                                            <p style="margin:0">Lorem ipsum dolor sit.</p>
                                        </td>
                                    </tr>
                                </table>
                            </td>
                        </tr>
                    </table>
                </td>
            </tr>       
</table>
<!-- Email Body : END -->
<!--[if (gte mso 9)|(IE)]>
</td>
</tr>
</table>
<![endif]-->
</div>
<!--[if (gte mso 9)|(IE)]>
</td>
</tr>
</table>
<![endif]-->
</center>
</body>
</html>
```

Fell free to use this code, test it and leave a comment or suggest improvements
