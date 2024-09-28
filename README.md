// hello-world.js
console.log("HELLO WORLD");
// server.js
const http = require("http");

const server = http.createServer((req, res) => {
    res.writeHead(200, { "Content-Type": "text/html" });
    res.end("<h1>Hello Node!!!!</h1>\n");
});

server.listen(3000, () => {
    console.log("Server is running on http://localhost:3000");
});
// file-operations.js
const fs = require("fs");

// Create "welcome.txt"
fs.writeFile("welcome.txt", "Hello Node", (err) => {
    if (err) throw err;
    console.log("welcome.txt has been created!");
});

// Read from "hello.txt"
fs.readFile("hello.txt", "utf8", (err, data) => {
    if (err) throw err;
    console.log(data);
});
// password-generator.js
const generatePassword = require("generate-password");

const password = generatePassword.generate({
    length: 10,
    numbers: true,
});

console.log("Generated Password:", password);
// email-sender.js
const nodemailer = require("nodemailer");

const transporter = nodemailer.createTransport({
    service: "gmail", // Use your email provider
    auth: {
        user: "abdiwahid2362@gmail.com", // Your email
        pass: "ABDIWAHID2005" // Your password
    }
});

const mailOptions = {
    from: "abdiwahid2362@gmail.com",
    to: "recipient-email@example.com",
    subject: "Test Email",
    text: "Hello from Node.js!",
};

transporter.sendMail(mailOptions, (err, info) => {
    if (err) {
        return console.log(err);
    }
    console.log("Email sent: " + info.response);
});

