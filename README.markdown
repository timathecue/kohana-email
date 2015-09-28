Email Module For Kohana 3.3+
=================================

Methods defined:

	Email::connect($config = NULL)

Creates SwiftMailer object. $config is an array of configuration values and defaults to using the config file 'email'.

	Email::send($to, $from, $subject, $message, $html = false)

$to can be any of the following:

*  a single string email address e.g. "test@example.com"
*  an array specifying an email address and a name e.g. array('test@example.com', 'John Doe')
*  an array of recipients in either above format, keyed by type e.g. array('to' => 'test@example.com', 'cc' => array('test2@example.com', 'Jane Doe'), 'bcc' => 'another@example.com')

$from can be either a string email or array of email and name as above

More complex email (multipart, attachments, batch mailing etc.) must be done using the native Swift_Mailer classes. The Swift Mailer autoloader is included by connect() so you can use and class in the Swift library without worrying about including files.

The Swift_Mailer object setup by connect is returned by it so if you need to access it manually use:

        $mailer = Email::connect();

        // Create complex Swift_Message object stored in $message

        $mailer->send($message);

