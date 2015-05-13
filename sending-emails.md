# PHP邮件发送

PHP must be configured correctly in the **php.ini** file with the details of how your system sends email. Open php.ini file available in **/etc/** directory and find the section headed mail function.

Windows users should ensure that two directives are supplied. The first is called SMTP that defines your email server address. The second is called sendmail_from which defines your own email address.

The configuration for Windows should look something like this:
必须正确配置PHP中PHP.ini文件中如何详细地使用系统发送电子邮件。打开**php.ini**文件中可用 **/etc/**目录,找到部分[**邮件函数]**。

Windows用户应该确保提供两个指令。第一个叫做SMTP,它定义了你的电子邮件服务器地址。第二个叫做sendmail_from定义您自己的电子邮件地址。

配置Windows看起来应该是这样的:


    [mail function]
    ; For Win32 only.
    SMTP = smtp.secureserver.net

    ; For win32 only
    sendmail_from = webmaster@tutorialspoint.com

Linux users simply need to let PHP know the location of their application. The path and any desired switches should be specified to the sendmail_path directive.

Linux用户只需要告诉PHP 他们的**sendmail** 的应用程序位置。指定的路径和任何所需的开关应该在sendmail_path有所指引。

Linux的配置应该是这样的:

    [mail function]
    ; For Win32 only.
    SMTP =

    ; For win32 only
    sendmail_from =

    ; For Unix only
    sendmail_path = /usr/sbin/sendmail -t -i

Now you are ready to go:
现在你准备好了：

## 发送纯文本的电子邮件:
PHP使用mail()函数来发送电子邮件。这个函数需要三个强制参数指定收件人的电子邮件地址,消息和实际消息的主题另外还有其他两个可选参数。

    mail( to, subject, message, headers, parameters );

这是每个参数的描述。

<table class="table table-bordered">
  <tr>
    <th align="left" valign="top" width="20%">参数</th>
    <th align="left" valign="top" width="80%">描述</th>
  </tr>  
  <tr>
    <td valign="top">to</td>
    <td valign="top">必需的。指定邮件的接收/接收器



</td>
  </tr>
  <tr>
    <td valign="top">subject</td>
    <td valign="top">必需的。指定电子邮件的主题。该参数不能包含任何换行字符</td>
  </tr>
  <tr>
    <td valign="top">message</td>
    <td valign="top">必需的。定义要发送的消息。每一行应该分离低频(\ n)。行不得超过70个字符</td>
  </tr>
  <tr>
    <td valign="top">headers</td>
    <td valign="top">可选的。指定附加头,从Cc和Bcc。附加头应该被CRLF(\ r \ n) 分开</td>
  </tr>
  <tr>
    <td valign="top">parameters</td>
    <td valign="top">
可选的。指定一个附加参数到sendmail的程序</td>
  </tr>
  </table>

尽快PHP调用邮件函数将试图发送电子邮件,那么成功它将返回true,如果失败它将返回false。

可以指定为多个收件人在mail()函数的第一个参数在一个逗号分隔的列表中。

例如：


## Example

以下示例将发送HTML电子邮件消息到xyz@somedomain.com。你可以以这样一种方式编写程序的代码,它应该接收来自用户的所有内容,然后应该发送一个电子邮件。

	<html>
	<head>
	<title>Sending email using PHP</title>
	</head>
	<body>
	<?php
	   $to = "xyz@somedomain.com";
	   $subject = "This is subject";
	   $message = "This is simple text message.";
	   $header = "From:abc@somedomain.com \r\n";
	   $retval = mail ($to,$subject,$message,$header);
	   if( $retval == true )  
	   {
	      echo "Message sent successfully...";
	   }
	   else
	   {
	      echo "Message could not be sent...";
	   }
	?>
	</body>
	</html>

    
    
    
    
    
    

## 发送HTML电子邮件
当你使用PHP发送一个文本信息所有的内容将被视为简单的文本。即使你包含HTML标签在一个文本消息时,它将显示简单的文本和HTML标记将不会通过HTML语法显示格式化。但PHP提供了选择发送HTML消息按照实际HTML消息。

发送电子邮件消息时您可以指定一个Mime版本,内容类型和字符集来发送HTML电子邮件。

## 例如：
以下示例将HTML电子邮件消息发送到xyz@somedomain.com将它复制到afgh@somedomain.com。你可以以编写这个程序的代码的方式从用户接收所有的内容,然后发送一个电子邮件。

	<html>
	<head>
	<title>Sending HTML email using PHP</title>
	</head>
	<body>
	<?php
	   $to = "xyz@somedomain.com";
	   $subject = "This is subject";
	   $message = "<b>This is HTML message.</b>";
	   $message .= "<h1>This is headline.</h1>";
	   $header = "From:abc@somedomain.com \r\n";
	   $header = "Cc:afgh@somedomain.com \r\n";
	   $header .= "MIME-Version: 1.0\r\n";
	   $header .= "Content-type: text/html\r\n";
	   $retval = mail ($to,$subject,$message,$header);
	   if( $retval == true )
	   {
	      echo "Message sent successfully...";
	   }
	   else
	   {
	      echo "Message could not be sent...";
	   }
	?>
	</body>
	</html>

    
    
    
    
    
    
    
    

## 用电子邮件发送附件:
发送电子邮件与混合内容要求设置内容类型头到多部分/混合。然后可以在在边界里指定文本和附件部分。

边界始于两个连字符后跟一个惟一的编号这个编号不可以出现在电子邮件中的一部分。一个PHP函数md5()用于创建一个32位十六进制数唯一的号码。最终的边界表示电子邮件的最后部分也必须有两个连字符结束。

附加文件应该用base64_encode ()函数编码进行安全传输和最好用chunk_split()函数分成块。这增加了\ r \ n定期内部文件，正常每76个字符。

下面的示例将发送文件/ tmp /test.txt作为附件。你可以编写代码程序接收一个上传文件并将其发送。

	<html>
	<head>
	<title>Sending attachment using PHP</title>
	</head>
	<body>
	<?php
	  $to = "xyz@somedomain.com";
	  $subject = "This is subject";
	  $message = "This is test message.";
	  # Open a file
	  $file = fopen( "/tmp/test.txt", "r" );
	  if( $file == false )
	  {
	     echo "Error in opening file";
	     exit();
	  }
	  # Read the file into a variable
	  $size = filesize("/tmp/test.txt");
	  $content = fread( $file, $size);
	
	  # encode the data for safe transit
	  # and insert \r\n after every 76 chars.
	  $encoded_content = chunk_split( base64_encode($content));
	  
	  # Get a random 32 bit number using time() as seed.
	  $num = md5( time() );
	
	  # Define the main headers.
	  $header = "From:xyz@somedomain.com\r\n";
	  $header .= "MIME-Version: 1.0\r\n";
	  $header .= "Content-Type: multipart/mixed; ";
	  $header .= "boundary=$num\r\n";
	  $header .= "--$num\r\n";
	
	  # Define the message section
	  $header .= "Content-Type: text/plain\r\n";
	  $header .= "Content-Transfer-Encoding:8bit\r\n\n";
	  $header .= "$message\r\n";
	  $header .= "--$num\r\n";
	
	  # Define the attachment section
	  $header .= "Content-Type:  multipart/mixed; ";
	  $header .= "name=\"test.txt\"\r\n";
	  $header .= "Content-Transfer-Encoding:base64\r\n";
	  $header .= "Content-Disposition:attachment; ";
	  $header .= "filename=\"test.txt\"\r\n\n";
	  $header .= "$encoded_content\r\n";
	  $header .= "--$num--";
	
	  # Send email now
	  $retval = mail ( $to, $subject, "", $header );
	  if( $retval == true )
	   {
	      echo "Message sent successfully...";
	   }
	   else
	   {
	      echo "Message could not be sent...";
	   }
	?>
	</body>
	</html>

你尝试所有上面的示例。如果你面对任何问题,那么你可以在论坛发布这一问题。

