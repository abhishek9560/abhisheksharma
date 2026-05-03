 
    <meta charset="UTF-8">
  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
    <title>application_07</title>
  
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css"
        integrity="sha512-Evv84Mr4kqVGRNSgIGL/F/aIDqQb7xQ2vcrdIwxfjThSH8CSR7PBEakCr51Ck+w+/U6swU2Im1vVX0SVk9ABhg=="
        crossorigin="anonymous" referrerpolicy="no-referrer" />
  
    <style>
      
        * {
            margin: 0;
            padding: 0;
        }

        .head {
            width: 100%;
            height: 100vh;
        }

        header {
            width: 100%;
            display: flex;
            border-bottom: 3.5px solid lightgray;
        }

        .div_header {
            height: 55px;
            display: flex;
            column-gap: 6px;
            align-items: center;
        }

        .icon_div {
            width: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 10px;
            text-align: center;
            padding: 3px 0;
            border-radius: 6px;
            background-color: #c3361d;
        }

        .logo_div {
            width: 60px;
            height: 40px;
            background-image: url(https://thumbs.dreamstime.com/b/icp-logo-icp-letter-icp-letter-logo-design-initials-icp-logo-linked-circle-uppercase-monogram-logo-icp-typography-396227126.jpg);
            background-size: 70px;
            background-position: center;
            border-radius: 20px;
        }

        .Image_div {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            border: 2px solid lightgray;
        }

        .name_show {
            margin-left: 4px;
            height: max-content;
            font-family: sans-serif, system-ui;
        }

        .Lo-out {
            width: 45px;
            height: 45px;
            font-size: x-large;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            border-radius: 50%;
            margin-right: 15px;
            background-color: black;
        }

        main {
            width: 100%;
            height: auto;
            display: flex;
            margin-top: 10px;
            justify-content: center;
        }

        .infor_div {
            width: 90%;
            display: flex;
            border-radius: 20px;
            align-items: center;
            flex-direction: column;
            border: 2px solid aqua;
        }

        .mini_header {
            width: 100%;
            font-weight: 900;
            font-size: 22px;
            line-height: 1.8;
            text-align: center;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-family: fantasy;
            background-color: aqua;
            border-radius: 16px 16px 0 0;
        }

        footer {
            width: 100%;
            display: flex;
            margin-top: 5px;
            padding-bottom: 15px;
            justify-content: center;
        }

        .footer_div {
            width: 95%;
            height: auto;
            padding: 5px 0;
            font-size: 16.5px;
            text-align: center;
            border-radius: 20px;
            border: 2px solid darkgreen;
            background-color: lightgreen;
            font-family: math, system-ui, sans-serif;
        }

        .slide_Box {
            width: 260px;
            height: 91.3%;
            top: 55px;
            position: fixed;
            left: -270px;
            background: #fff;
            border-radius: 0 15px 0 0;
            box-shadow: 6px 0px 5px 0px rgba(0, 0, 0, 0.3);
            transition: 0.4s;
            z-index: 2;
        }

        .slide_Box.active {
            left: 0;
        }

        .slide_div {
            width: 100%;
            display: flex;
            margin-bottom: 5px;
            align-items: center;
            border-radius: 0 15px 0 0;
            background-color: #c3361d;
        }

        .icon_Bx {
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
        }

        .text_div {
            color: white;
            line-height: 40px;
            font-family: math;
            margin-left: 10px;
            font-size: 18px;
            text-transform: math-auto;
        }

        .div_box {
            width: 100%;
            height: 100%;
            display: flex;
            row-gap: 10px;
            flex-direction: column;
            overflow-y: scroll;
            padding: 8px 0;
            overflow-x: hidden;
            align-items: center;
            scrollbar-width: none;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 999;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
        }

        .modal-content {
            background: #fff;
            margin: 5% auto;
            padding: 20px;
            width: 80%;
            height: 80%;
            border-radius: 10px;
            box-shadow: 8px 8px 14px -6px black;
        }

        .close {
            float: right;
            color: red;
            font-size: 25px;
            cursor: pointer;
            font-weight: 900;
            margin-bottom: 2px;
        }

        #preview {
            width: 100%;
            height: 90%;
        }

        #tick {
            display: none;
            color: green;
            font-size: 20px;
            margin-left: 10px;
        }
    </style>

    <div class="head">
        <header>
            <div class="div_header" style="width: 35%;">
                <div class="icon_div" onclick="toggleBox()">
                    <i class="fa-sharp fa-solid fa-bars" style="font-size: x-large;"></i>
                </div>
                <div class="logo_div"></div>
            </div>
            <!-- slide box code -->
            <div class="slide_Box" id="SlBox">
                <!-- number = 01 -->
                <div class="slide_div">
                    <div class="icon_Bx">
                        <i class="fa-solid fa-house" style="color: white; margin-left: 5px;">
                        </i>
                    </div>
                    <a href="welcome_page.html" style="text-decoration: none;">
                        <div class="text_div">Dashboard</div>
                    </a>
                </div>
                <!-- number = 02 -->
                <div class="slide_div" style="border-radius: 0;">
                    <div class="icon_Bx">
                        <i class="fa-solid fa-circle-user" style="color: white; margin-left: 5px;"></i>
                    </div>
                    <a href="persoanal_infor.html" style="text-decoration: none;">
                        <div class="text_div">Personal Information</div>
                    </a>
                </div>
                <!-- number = 03 -->
                <div class="slide_div" style="border-radius: 0;">
                    <div class="icon_Bx">
                        <i class="fa-sharp fa-solid fa-arrow-rotate-right" style="margin-left: 5px; color: white;"></i>
                    </div>
                    <a href="update.html" style="text-decoration: none;">
                        <div class="text_div">Update Information</div>
                    </a>
                </div>
                <!-- number = 04 -->
                <div class="slide_div" style="border-radius: 0;">
                    <div class="icon_Bx">
                        <i class="fa-solid fa-upload" style="margin-left: 5px; color: white;"></i>
                    </div>
                    <a href="upload.html" style="text-decoration: none;">
                        <div class="text_div">Upload Information</div>
                    </a>
                </div>
            </div>
            <div class="div_header" style="width: 65%; justify-content: end; column-gap: 10px;">
                <div class="Image_div" id="image_div">
                    <img id="img_div" width="45px" height="45px" alt="No Image" style="border-radius: 50%;">
                </div>
                <!-- login Out icon -->
                <a href="foram_format_login.html" style="text-decoration: none;">
                    <div class="Lo-out">
                        <i class="fa-solid fa-power-off" style="font-size: 25px; color: white;"></i>
                    </div>
                </a>
            </div>
        </header>
        <main>
            <div class="infor_div">
                <div class="mini_header">Upload Information</div>
                <div class="div_box">
                    <!-- number = 01 []-->
                    <div style="width: 95%; height: 75px; border-radius: 15px; border: 2px solid darkgreen;">
                        <p
                            style="height: 50%; display: flex; align-items: center; justify-content: center; border-radius: 12px 12px 0 0; background-color: aquamarine;">
                            <input type="file" id="fileInput" style="width: 80%;">
                        </p>
                        <div
                            style="height: 50%; background-color: rgb(229, 231, 235); text-transform: uppercase; border-radius: 0 0 12px 12px; font-weight: 700; display: flex; align-items: center; justify-content: center; font-family: math; cursor: pointer; column-gap: 25px;">
                            <p id="view" class="viewBox"
                                style="background: linear-gradient(45deg, lightgray, gray); padding: 5px; border-radius: 10px 0px;"
                                onclick="previewFile()">View
                            </p>
                            <p id="view" class="viewBox"
                                style="background: linear-gradient(45deg, lightgreen, darkgreen); padding: 5px; border-radius: 10px 0px;"
                                onclick="saveFile()">Save
                            </p>
                            <p id="view" class="viewBox"
                                style="background: linear-gradient(45deg, pink, red); padding: 5px; border-radius: 10px 0px;"
                                onclick="deleteFile()">Delete
                            </p>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Modal -->
            <div id="myModal" class="modal">
                <div class="modal-content">
                    <span class="close" onclick="closeModal()">✖</span>
                    <div id="preview"></div>
                </div>
            </div>
        </main>
        <footer>
            <div class="footer_div">© Online Facilitation System for Students. All rights reserved @2018
            </div>
        </footer>
    </div>







    <script>
        // top details show code.
        const U_data = JSON.parse(localStorage.getItem("userdetails_filled"));
        const Date_Of_Birth = U_data.dob;
        const parts = Date_Of_Birth.split("-");
        const dob_I = parts[2] + "-" + parts[1] + "-" + parts[0];
        if (U_data) {
            document.getElementById("img_div").src = U_data.image;
            document.getElementById("name").innerText = U_data.name;
            document.getElementById("gender").innerText = U_data.Gender;
            document.getElementById("f_name").innerText = U_data.father;
            document.getElementById("mobile_no").innerText = U_data.mobile;
            document.getElementById("DOB").innerText = dob_I;
            document.getElementById("m_name").innerText = U_data.mother;
            document.getElementById("e_mail").innerText = U_data.email;
            document.getElementById("r_no").innerText = U_data.roll_no;
            document.getElementById("r_code").innerText = U_data.roll_code;
            document.getElementById("UID_aadhaar").innerText = U_data.uidsno;
            document.getElementById("age").innerText = U_data.age;
            document.getElementById("s_c_name").innerText = U_data.sc_name;
            document.getElementById("class").innerText = U_data.sk_class;
            document.getElementById("stream").innerText = U_data.stream;
            document.getElementById("skills").innerText = U_data.skills;
            // document.getElementById("").innerText = U_data.address;

        } else {
            alert("No Data Found !\n❌( कोई भी जानकारी नहीं है। )\nPlease Check Your Information !\n( कृपया अपनी जानकारी जाँच करे। )");
        }

        function toggleBox() {
            document.getElementById("SlBox").classList.toggle("active");
        }

        function previewFile() {
            const file = document.getElementById("fileInput").files[0];
            const preview = document.getElementById("preview");
            const modal = document.getElementById("myModal");

            preview.innerHTML = "";

            // 👉 अगर नई file select नहीं है → localStorage से लो
            if (!file) {
                const savedData = localStorage.getItem("fileData");
                const savedType = localStorage.getItem("fileType");

                if (!savedData || !savedType) {
                    alert("📁 Please Select A Document ⬇\n( कृपया एक दस्तावेज़ चुनें। )");
                    return;
                }

                showPreview(savedData, savedType);
                modal.style.display = "block";
                return;
            }

            // 👉 अगर नई file है
            const fileURL = URL.createObjectURL(file);
            showPreview(fileURL, file.type);
            modal.style.display = "block";
            // const fileType = file.type;\
        }

        function saveFile() {
            const file = document.getElementById("fileInput").files[0];

            if (!file) {
                alert("❎ No Document Uploaded ⬇\n( कोई दस्तावेज़ अपलोड नहीं किया गया है। )");
                return;
            }

            const reader = new FileReader();

            reader.onload = function (e) {
                const fileData = e.target.result;

                // Save
                localStorage.setItem("fileData", fileData);
                localStorage.setItem("fileType", file.type);

                // Tick
                alert("✔ Document Saved !");
            };

            reader.readAsDataURL(file);
        }

        // 👉 Common Preview Function (NEW)
        function showPreview(src, type) {
            const preview = document.getElementById("preview");

            preview.innerHTML = "";

            if (type.startsWith("image/")) {
                preview.innerHTML = `<img src="${src}" style="width:100%; height:100%; object-fit:contain;">`;
            }
            else if (type === "application/pdf") {
                preview.innerHTML = `<iframe src="${src}" width="100%" height="100%"></iframe>`;
            }
            else if (type === "image/svg+xml") {
                preview.innerHTML = `<iframe src="${src}" width="100%" height="100%"></iframe>`;
            }
            else {
                preview.innerHTML = `<p>Preview not supported</p>`;
            }
        }

        function closeModal() {
            document.getElementById("myModal").style.display = "none";
        }

        // 👉 Refresh के बाद tick दिखे
        window.onload = function () {
            const data = localStorage.getItem("fileData");

            if (data) {
                document.getElementById("tick").style.display = "inline";
            }
        };

        function deleteFile() {
            // Remove from localStorage
            localStorage.removeItem("fileData");
            localStorage.removeItem("fileType");
            localStorage.removeItem("fileName");
            // Clear preview
            document.getElementById("preview").innerHTML = "";
            // Hide tick
            alert("🗑 Document Deleted Successfully ⬇\n( दस्तावेज़ सफलतापूर्वक हटा दिया गया है। )");
        }

    </script>

<!-- <button onclick="previewFile()">View</button>
<button onclick="saveFile()">Save</button>
<span id="tick">✔ Saved</span>
<button onclick="deleteFile()">Delete</button> -->

<!--document.getElementById("name_div").innerText = U_data.name; -->
<!-- <div class="name_show">
<div class="wel_come">Welcome</div>
<div id="name_div" class="Name_show"></div>
</div> -->

<!-- <div class="file-upload">
<label for="fileInput" class="file-label">Choose File</label>
<input type="file" id="fileInput">
</div> -->
<!-- <p id="fileName">No file chosen</p> -->
<!-- </p> -->
