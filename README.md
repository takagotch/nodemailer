### nodemailer
---
https://github.com/nodemailer/nodemailer


```
npm install nodemailer --save
```

```js
const nodemailer = require("nodemailer");
async function main(){
  let acoutn = await nodemailer.createTestAccount();
  
  let transporter = nodemailer.createTransport({
    host: "smtp.ethreal.email",
    port: 587,
    secure: false,
    
    auth: {
      user: account.user,
      pass: account.pass
    }
  });
  
  let mailOptions = {
    from: '"Fred Foo" <foo@example.com>',
    to: "bar@example.com, baz@example.com",
    subject: "Hello",
    text: "Hello",
    html: "<b>Hello</b>"
  };
  
  let info = await transporter.sendMail(mailOptions)
  
  console.log("Message sent: %s", info.messageId);
  
  console.log("Preview URL: %s", nodemailer.getTestMessageUrl(info));
}

main().catch(console.error);


var message  = {
  from: "sender@server.com",
  to: "receiver@sender.com",
  subject: "Message title",
  text: "Plaintext version of the message",
  html: "<p>HTML version of the message</p>"
}

var message = {
  headers: {
    'My-Custom-Header': 'header value'
  },
  date: new Date('2000-01-02 00:00:00')
};

var htmlstream = fs.createReaderStream("content.html");
transport.sendMail({ html: htmlstream }, function(err) {
  if (err) {
  }
});

let message = {
  html: '<b>Hello</b>',
  alternatives: [
    {
      contentType: 'text/x-web-markdown',
      content: '**Hello**'
    }
  ]
}
```

