<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Application_login</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        header {
            width: 100%;
            height: 100vh;
            background-size: cover;
            background-position: center;
            background-image: url(https://img.freepik.com/premium-photo/back-school-school-building_899145-17962.jpg?ga=GA1.1.1221565113.1776769732&amp;semt=ais_hybrid&amp;w=740&amp;q=80);
        }

        main {
            width: 100%;
            height: 100%;
            justify-content: space-evenly;
            background: rgb(0 0 0 / 20%);
        }

        .H4_title {
            top: 60px;
            color: black;
            font-weight: 800;
            font-size: 30px;
            font-family: math;
            text-align: center;
            position: relative;
            text-transform: uppercase;
        }

        .heading {
            top: 80px;
            left: 14px;
            width: 90%;
            padding: 4px;
            position: relative;
            border: 1px solid black;
            border-radius: 20px;
            background-color: rgb(0 0 0 / 50%);
        }

        .H4_student {
            color: white;
            font-size: 25px;
            font-family: system-ui;
            text-align: center;
            margin-top: 15px;
            font-weight: 300;
        }

        .label {
            font-size: 18px;
            color: white;
            text-align: center;
            font-family: system-ui;
            font-weight: 500;
            margin-top: 15px;
            word-spacing: 2px;
        }

        .input_login {
            width: 86%;
            height: 31px;
            border: none;
            outline: none;
            font-weight: 700;
            border-radius: 25px;
            margin-top: 10px;
            padding-left: 20px;
            font-size: medium;
            background: hsl(0deg 0% 100% / 80%);
        }

        .div_01 {
            height: 100%;
            line-height: 1.45;
            font-size: 22px;
            text-align: start;
            letter-spacing: 3px;
        }

        .image_01 {
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            cursor: pointer;
            image-rendering: auto;
            background-image: url(https://www.freeiconspng.com/uploads/refresh-icon-png-3.png);
        }

        .style_01 {
            width: 20%;
            border: none;
            border-radius: 0 25px 25px 0;
            background-color: lightgray;
        }

        .verify_Div {
            height: 30px;
            margin-top: 8px;
            /* background-color: aqua; */
        }

        .Verify_Btn {
            width: 40%;
            border: none;
            border-radius: 20px;
            height: 100%;
            font-size: small;
            text-transform: lowercase;
            font-weight: 700;
            cursor: pointer;
            filter: drop-shadow(2px 4px 6px black);
        }

        button.Verify_Btn:focus {
            box-sizing: border-box;
            border: 2px solid aqua;
            box-shadow: 0px 0px 6px 2px skyblue;
        }

        .result_p {
            font-size: medium;
            font-family: monospace;
            word-spacing: -2px;
            font-weight: 700;
        }

        .last_div {
            width: 102.5%;
            height: 42px;
            right: 4px;
            display: flex;
            margin-top: 5px;
            position: relative;
            align-items: end;
            padding-bottom: 4px;
            justify-content: center;
            border-radius: 0 0 20px 20px;
        }

        .last_btn {
            width: 65%;
            height: 38px;
            border-radius: 30px;
            box-sizing: border-box;
            border: none;
            color: white;
            box-shadow: inset 0 30px 22px rgba(0, 0, 0, 0.3);
            background: linear-gradient(135deg, #00c6ff, #0072ff);
            font-weight: 800;
            font-size: 22px;
            letter-spacing: 3px;
        }

        .Hide_Div_01 {
            display: none;
            margin: 6px 0;
        }
    </style>
</head>

<body>
    <header>
        <main>
            <h4 class="H4_title">International College Portal</h4>
            <div class="heading">
                <div>
                    <h4 class="H4_student">STUDENT LOGIN</h4>
                </div>
                <div style="text-align: center;">
                    <h4 class="label">Enter The Mobile No Or Email Provide The <p
                            style="display: inline-block; color: yellow;">
                            Registration Form</p> !</h4>
                    <input id="Mobile_Email" type="text" placeholder="Mobile Number / Email ID" class="input_login">
                    <h4 class="label">Enter Password ( यहाँ नीचे भरें ! )</h4>
                    <input type="text" id="Password_login" class="input_login" placeholder="Enter Password"
                        style="margin-top: 5px;">

                    <!-- Captcha System Code -->
                    <div class="input_login" style="display: flex; position: relative; left: 10.5px;">
                        <div id="captcha" class="div_01" style="width: 80%;"></div>
                        <button class="div_01 image_01 style_01" onclick="generateCaptcha()"></button>
                    </div>

                    <!-- captcha input -->
                    <input type="text" id="input_captcha" class="input_login" maxlength="6" placeholder="Enter Captcha"
                        style="margin-top: 10px; margin-left: 1px; font-weight: 500;">

                    <!-- Verify btn -->
                    <div class="verify_Div">
                        <button id="btn_small" class="Verify_Btn" onclick="checkCaptcha()">Verify</button>
                    </div>
                    <div style="height: 25px; margin-top: 6px;">
                        <p id="result" class="result_p"></p>
                    </div>
                </div>

                <!-- hidden btn -->
                <div id="Hide_Div" class="Hide_Div_01">
                    <div class="last_div">
                        <button id="confirm_btn_01" class="last_btn" onclick="loginBtn()">Login</button>
                    </div>
                </div>
            </div>
        </main>
    </header>


    <script>
        let captchaCode = "";
        const Hidden = document.getElementById("Hide_Div");

        // Generate 6 digit number
        function generateCaptcha() {
            captchaCode = Math.floor(100000 + Math.random() * 900000).toString();
            document.getElementById("captcha").innerText = captchaCode;
        }

        // Check captcha
        function checkCaptcha() {
            const div_check = document.getElementById("input_captcha").value.trim();
            const input_div = document.getElementById("input_captcha");
            const show_result = document.getElementById("result");
            const Verify = document.getElementById("btn_small");

            //check captcha code vailed
            if (!div_check) {
                show_result.innerText = "⚠️ Please Enter Captcha";
                show_result.style.color = "white";
                Hidden.classList.add("Hide_Div_01");
            } else if (div_check === captchaCode) {
                alert("✔️ Captcha Verified");
                show_result.innerText = "";
                show_result.innerText = "✅ Captcha Verified";
                show_result.style.color = "lightgreen";
                Hidden.classList.remove("Hide_Div_01");
                Verify.disabled = true; // 👈 Verify disable
                input_div.disabled = true; // 👈 Verify disable
            } else {
                show_result.innerText = "❌ Wrong Captcha";
                show_result.style.color = "red";
                Hidden.classList.add("Hide_Div_01");
            }

            return;
        }

        // Load first captcha
        generateCaptcha();

        // Login Btn function
        function loginBtn() {
            const M_Email = document.getElementById("Mobile_Email").value.trim();
            const pass_input = document.getElementById("Password_login").value.trim();
            const U_data = JSON.parse(localStorage.getItem("userdetails_filled"));

            const pass_inout = localStorage.getItem("PASS_word");

            if (!M_Email || !pass_input) {
                alert("⚠️ Please Fill All Data ❗\n( कृपया सभी जानकारी भरें । )");
                return;
            }
            if (U_data.mobile === M_Email || U_data.email === M_Email && pass_inout === pass_input) {
                alert("✔️ LOGIN SUCCESSFULLY !\n( लॉगिन सफल हुआ 🎉)");

                // redirect code
                window.location.href = "";

            } else {
                alert("❌ The Information Wrong !\n( जानकारी गलत है । )");
                // alert("❌ THE INFORMATION INCORRECT ! ⤵️\n📌 NOTE : ⚠️\n(i) The Mobile Number OR Email ID Is Incorrect ! ⬅️\n( मोबाइल नंबर या ईमेल ID गलत है । )\n(ii) The Password Is Incorrect ! ⬅️\n( पासवर्ड गलत है । )\n\n📌 Please Enter The Correct Information ! 📍\n( कृपया सही जानकारी दर्ज करें । )");
            }
            return;
        }

    </script>
</body>

</html>

<!-- ID bhi localstroage me save kar diya hai name hai :- "ID_In" -->
