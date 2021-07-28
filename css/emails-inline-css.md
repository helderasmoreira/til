# Emails should use inline CSS

Writing emails with (modern) CSS seems to be harder than what one would expect. Most clients, especially web clients, ignore linked stylesheets or `<style>` tags in the HTML. The workaround is to write all the CSS rules in the style attribute of each tag inside your email.

Now, the partly good news is that you don't need to do this manually and should look to include this "move existing CSS to inline CSS" as an automated process.

If you're using Rails look [here](https://github.com/fphilipe/premailer-rails) and for further reading on the topic along with some other tools to do the job, look [here](https://www.litmus.com/blog/a-guide-to-css-inlining-in-email/).
