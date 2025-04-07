
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>طلب خدمة تنظيف - توينينج لخدمات النظافة</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            direction: rtl;
            background: #f2f2f2;
        }
        .container {
            width: 90%;
            max-width: 400px;
            margin: auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        select, input, textarea, button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
        }
        .logo {
            width: 100px;
            height: auto;
            margin-bottom: 10px;
        }
        .serviceItem {
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 10px;
            margin-top: 10px;
        }
        .note {
            background: #fffae6;
            padding: 10px;
            border: 1px dashed #e0c200;
            margin-top: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>
<div class="container">
    <img src="https://i.postimg.cc/bvjDNQ0j/Whats-App-Image-2025-04-07-at-21-17-23-e65cadc5-removebg-preview.png" alt="شعار الشركة" class="logo">
    <h2>طلب خدمة - توينينج لخدمات النظافة</h2>

    <div id="servicesContainer">
        <div class="serviceItem">
            <label>اختر الخدمة</label>
            <select class="service" onchange="calculatePrice()">
                <option value="35">خدمة تنظيف عميق - 35 جنيه للمتر</option>
                <option value="50">تنظيف ما بعد البناء والتشطيب - 50 جنيه للمتر</option>
                <option value="75">تنظيف شلتة الالياف الصناعية - 75 جنيه</option>
                <option value="75">تنظيف موكيت عادى - 75 جنيه للمتر</option>
                <option value="75">تنظيف موكيت فايير - 75 جنيه للمتر</option>
                <option value="75">تنظيف مخدات الكتب - 75 جنيه للواحدة</option>
                <option value="600">تنظيف كنية ٢ مقعد - 600 جنيه</option>
                <option value="750">تنظيف كنية ٣ مقعد - 750 جنيه</option>
                <option value="1400">تنظيف كتية حرف ( L) - 1400 جنيه</option>
                <option value="75">تنظيف مخدات صغيرة - 75 جنيه للواحدة</option>
                <option value="100">تنظيف مخدات كبيرة - 100 جنيه للواحدة</option>
                <option value="250">تنظيف كرسى انتيريه - 250 جنيه</option>
                <option value="200">تنظيف كرسى صالون يد خشب - 200 جنيه</option>
                <option value="450">تنظيف فوتیه - 450 جنيه</option>
                <option value="300">تنظيف كرسي عثمانى - 300 جنيه</option>
                <option value="150">تنظيف كرسى سفره ظهر وقاعدة - 150 جنيه</option>
                <option value="100">تنظيف كرسى سفرة قاعدة فقط - 100 جنيه</option>
                <option value="100">تنظيف كرسى بدون ذراع وظهر - 100 جنيه</option>
                <option value="300">تنظيف شاذلونج - 300 جنيه</option>
                <option value="200">تنظيف كرسى هزاز - 200 جنيه</option>
                <option value="900">تنظيف مرتية كيتج ٢م - 900 جنيه</option>
                <option value="800">تنظيف مرتية ديل ١٨٠ سم - 800 جنيه</option>
                <option value="700">تنظيف مرتية كوين ١٦٠ سم - 700 جنيه</option>
                <option value="700">تنظيف مرتية سنجل ١٤٠ سم - 700 جنيه</option>
                <option value="150">تنظيف شباك غرفة الوميتال - 150 جنيه</option>
                <option value="300">تنظيف باب بلكونة الوميتال - 300 جنيه</option>
                <option value="750">التنظيف اليومى المنتظم (10ص - 6م) بدون أدوات - 750 جنيه</option>
            </select>
            <input type="number" class="area" placeholder="العدد أو المساحة" oninput="calculatePrice()">
            <button onclick="removeService(this)">❌ حذف</button>
        </div>
    </div>

    <button onclick="addService()">➕ إضافة خدمة أخرى</button>
    <p>💰 السعر الإجمالي: <span id="totalPrice">0</span> جنيه</p>

    <input type="text" id="name" placeholder="الاسم" required>
    <input type="tel" id="phone" placeholder="رقم الهاتف" required>
    <input type="text" id="address" placeholder="العنوان بالتفصيل" required>
    <input type="date" id="date" required>
    <select id="gender" required>
        <option value="ذكر">ذكر</option>
        <option value="أنثى">أنثى</option>
    </select>
    <textarea id="notes" placeholder="ملاحظات إضافية"></textarea>

    <div class="note">
        لدفع نصف قيمة الطلب مقدمًا يرجى التحويل على رقم محفظة <strong>01116199928</strong> ورفع صورة إثبات الدفع.
    </div>
    <input type="file" id="paymentProof" accept="image/*" required>

    <button onclick="getLocation()">📍 مشاركة الموقع</button>
    <input type="text" id="location" placeholder="موقعك" readonly>
    <button onclick="sendWhatsApp()">📲 تأكيد الحجز عبر واتساب</button>
</div>

<script>
    function calculatePrice() {
        let totalPrice = 0;
        document.querySelectorAll('.serviceItem').forEach(item => {
            let servicePrice = parseFloat(item.querySelector(".service").value);
            let quantity = parseFloat(item.querySelector(".area").value) || 1;
            totalPrice += servicePrice * quantity;
        });
        document.getElementById("totalPrice").innerText = totalPrice;
    }

    function addService() {
        let serviceOptions = document.querySelector(".service").innerHTML;
        let container = document.getElementById("servicesContainer");
        let newService = document.createElement("div");
        newService.classList.add("serviceItem");
        newService.innerHTML = `
            <label>اختر الخدمة</label>
            <select class="service" onchange="calculatePrice()">` + serviceOptions + `</select>
            <input type="number" class="area" placeholder="العدد أو المساحة" oninput="calculatePrice()">
            <button onclick="removeService(this)">❌ حذف</button>
        `;
        container.appendChild(newService);
    }

    function removeService(button) {
        button.parentElement.remove();
        calculatePrice();
    }

    function getLocation() {
        if (navigator.geolocation) {
            navigator.geolocation.getCurrentPosition(function(position) {
                let latitude = position.coords.latitude;
                let longitude = position.coords.longitude;
                let locationUrl = `https://www.google.com/maps?q=${latitude},${longitude}`;
                document.getElementById("location").value = locationUrl;
            }, function(error) {
                alert("لا يمكن تحديد موقعك، يرجى السماح بالوصول إلى الموقع.");
            });
        } else {
            alert("المتصفح لا يدعم تحديد الموقع الجغرافي.");
        }
    }

    async function sendWhatsApp() {
        let phoneNumber = "201021584901";
        let name = document.getElementById("name").value.trim();
        let phone = document.getElementById("phone").value.trim();
        let address = document.getElementById("address").value.trim();
        let date = document.getElementById("date").value.trim();
        let gender = document.getElementById("gender").value;
        let notes = document.getElementById("notes").value.trim() || "لا يوجد";
        let location = document.getElementById("location").value.trim() || "لم يتم مشاركة الموقع";
        let totalPrice = document.getElementById("totalPrice").innerText;
        let paymentProof = document.getElementById("paymentProof").files[0];

        if (!paymentProof) {
            alert("يرجى رفع صورة إثبات الدفع.");
            return;
        }

        const formData = new FormData();
        formData.append("image", paymentProof);
        const response = await fetch("https://api.imgbb.com/1/upload?key=bde613bd4475de5e00274a795091ba04", {
            method: "POST",
            body: formData
        });
        const result = await response.json();
        const proofUrl = result.data.url;

        let services = [];
        document.querySelectorAll(".serviceItem").forEach(item => {
            let serviceText = item.querySelector(".service").selectedOptions[0].text;
            let quantity = item.querySelector(".area").value || 1;
            services.push(`${serviceText} - ${quantity}`);
        });

        let message = `👤 الاسم: ${name}\n👫 النوع: ${gender}\n📞 الهاتف: ${phone}\n📍 الموقع: ${location}\n📍 العنوان: ${address}\n📅 التاريخ: ${date}\n📝 ملاحظات: ${notes}\n💰 السعر الإجمالي: ${totalPrice} جنيه\n🛠️ الخدمات:\n${services.join("\n")}\n📸 إثبات الدفع: ${proofUrl}`;

        // إرسال إلى واتساب
        let waUrl = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
        window.open(waUrl, "_blank");

        // إرسال إلى البريد
        let mailtoLink = `mailto:Twiningtrade@gmail.com?subject=طلب حجز خدمة تنظيف من ${name}&body=${encodeURIComponent(message)}`;
        window.open(mailtoLink, "_blank");
    }
</script>
</body>
</html>
