# SSS
- Vercel serverless functions allow a custom vercel.json that allows Express to be used to serve the pages directly
- However by the very nature of serverless, there is no server, hence no session. However express does still expose req.session or res.session
- This respository is intended to test if CAPTCHA protected endpoints can be made on a Vercel/Similar Serverless Functions, by the virtue of req.session sharing

# How?
- You make the root route have a captcha, you generate the captcha through another route that sets req.session.captcha to the answer of captcha
- When the other protected routes are accessed you either use a middleware or prefix code to check whether req.body.captcha is equal to req.session.captcha
- This Requires the obvious use of Sessions and the importance of having them, however serverless is unlikely to support these, we'll be testing that Hypothesis in this repository.

# Refrences - 
- [Express Recaptcha](https://www.npmjs.com/package/express-recaptcha)
- [Simple Captcha](https://javascript.plainenglish.io/writing-the-simplest-captcha-validator-for-express-2a3f1411ec0e)
