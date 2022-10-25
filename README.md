# Google-0Auth2
https://www.loginradius.com/blog/engineering/google-authentication-with-nodejs-and-passportjs/

## Tuto from  https://www.loginradius.com/blog/engineering/google-authentication-with-nodejs-and-passportjs/

Which problems/error message did you face during the tutorial ? How did you resolve the problem?

1. Correct File extention  views/pages/auth.js is views/pages/auth.ejs
2. There is no rendering of the success page. 

Cause: app.get('/success', (req, res) => res.send(userProfile));
 
 -> Success route only returned the user data previously retrived in JSON format, without returning to the ejs success page  

Solution : app.get("/success", (req, res) => {
  res.render("pages/success", { user: userProfile });
});
