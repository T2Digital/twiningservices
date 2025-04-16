<html lang="ar">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>احجز خدمة تنظيف احترافية | توينينج</title>
  <meta name="description" content="احصل على خدمات تنظيف شاملة للمنازل والمكاتب من توينينج. حجز سهل وسريع وجودة عالية.">
  <meta name="keywords" content="تنظيف منازل, تنظيف مكاتب, شركة نظافة, توينينج">
  <meta name="theme-color" content="#e0f7fa">

  <!-- EmailJS Library -->
  <script type="text/javascript" src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <script>
    (function(){
      emailjs.init("sGBVVDlpms13iC8Lb");
    })();
  </script>

  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      direction: rtl;
      background: #e0f7fa;
      margin: 0;
      padding: 0;
    }
    .container {
      width: 90%;
      max-width: 400px;
      margin: 20px auto;
      padding: 20px;
      background: white;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
    }
    select, input, textarea, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      box-sizing: border-box;
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
      background: #f9f9f9;
    }
    .note {
      background: #fffae6;
      padding: 10px;
      border: 1px dashed #e0c200;
      margin-top: 10px;
      border-radius: 5px;
    }
    .success {
      background-color: #d4edda;
      color: #155724;
      padding: 15px;
      margin-top: 15px;
      border: 1px solid #c3e6cb;
      border-radius: 5px;
      display: none;
    }
    #loading {
      display: none;
      margin-top: 10px;
      color: #007BFF;
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
          <option value="75">تنظيف مخدات الكنب - 75 جنيه للواحدة</option>
          <option value="600">تنظيف كنبة ٢ مقعد - 600 جنيه</option>
          <option value="750">تنظيف كنبة ٣ مقعد - 750 جنيه</option>
          <option value="1400">تنظيف كتبة حرف ( L) - 1400 جنيه</option>
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
          <option value="900">تنظيف مرتبة كيتج ٢م - 900 جنيه</option>
          <option value="800">تنظيف مرتبة ديل ١٨٠ سم - 800 جنيه</option>
          <option value="700">تنظيف مرتبة كوين ١٦٠ سم - 700 جنيه</option>
          <option value="700">تنظيف مرتبة سنجل ١٤٠ سم - 700 جنيه</option>
          <option value="150">تنظيف شباك غرفة الوميتال - 150 جنيه</option>
          <option value="300">تنظيف باب بلكونة الوميتال - 300 جنيه</option>
          <option value="750">التنظيف اليومى المنتظم (10ص - 6م) بدون أدوات - 750 جنيه</option>
        </select>
        <input type="text" class="area" placeholder="العدد أو المساحة" oninput="calculatePrice()">
        <button onclick="removeService(this)">❌ حذف</button>
      </div>
    </div>
    <button onclick="addService()">➕ إضافة خدمة أخرى</button>
    <p>💰 السعر الإجمالي: <span id="totalPrice">0</span> جنيه</p>
    <input type="text" id="name" placeholder="الاسم" required>
    <input type="tel" id="phone" placeholder="رقم الهاتف" required>
    <input type="text" id="address" placeholder="العنوان بالتفصيل" required>
    <label for="date">حدد تاريخ الحجز</label>
    <input type="date" id="date" required>
    <select id="gender" required>
      <option value="ذكر">ذكر</option>
      <option value="أنثى">أنثى</option>
    </select>
    <textarea id="notes" placeholder="ملاحظات إضافية"></textarea>
    <div class="note">
      💵 يجب دفع نصف إجمالى قيمة الطلب مقدمًا (أي <span id="halfPrice">0</span> جنيه)<br>
      يرجى التحويل على رقم محفظة <strong>01116199928</strong> ورفع صورة إثبات الدفع.
    </div>
    <input type="file" id="paymentProof" accept="image/*" required>
    <button onclick="getLocation()">📍 مشاركة الموقع</button>
    <input type="text" id="location" placeholder="موقعك" readonly>
    <button onclick="sendWhatsApp()">📲 تأكيد الحجز عبر واتساب</button>
    <div id="loading">⏳ جاري معالجة الطلب...</div>
    <div id="successMessage" class="success">✅ تم تأكيد الحجز بنجاح.</div>
  </div>

  <script>
    function calculatePrice() {
      let total = 0;
      document.querySelectorAll('.serviceItem').forEach(item => {
        let price = parseFloat(item.querySelector('.service').value);
        let qtyInput = item.querySelector('.area').value;
        let qty = parseFloat(qtyInput);
        if (!qtyInput || qty <= 0 || isNaN(qty)) qty = 0;
        total += price * qty;
      });
      document.getElementById("totalPrice").innerText = total;
      document.getElementById("halfPrice").innerText = Math.ceil(total / 2);
    }

    function addService() {
      let options = document.querySelector('.service').innerHTML;
      let div = document.createElement('div');
      div.className = 'serviceItem';
      div.innerHTML = `
        <label>اختر الخدمة</label>
        <select class="service" onchange="calculatePrice()">${options}</select>
        <input type="text" class="area" placeholder="العدد أو المساحة" oninput="calculatePrice()">
        <button onclick="removeService(this)">❌ حذف</button>
      `;
      document.getElementById('servicesContainer').appendChild(div);
    }

    function removeService(button) {
      button.parentElement.remove();
      calculatePrice();
    }

    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(position => {
          const lat = position.coords.latitude;
          const lon = position.coords.longitude;
          document.getElementById("location").value = `https://www.google.com/maps?q=${lat},${lon}`;
        }, () => alert("يرجى السماح بالوصول إلى الموقع"));
      } else {
        alert("المتصفح لا يدعم الموقع الجغرافي");
      }
    }

    async function sendWhatsApp() {
      document.getElementById("loading").style.display = "block";
      const phoneNumber = "201021584901";
      const name = document.getElementById("name").value.trim();
      const phone = document.getElementById("phone").value.trim();
      const address = document.getElementById("address").value.trim();
      const date = document.getElementById("date").value;
      const gender = document.getElementById("gender").value;
      const notes = document.getElementById("notes").value || "لا يوجد";
      const location = document.getElementById("location").value || "لم يتم مشاركة الموقع";
      const totalPrice = document.getElementById("totalPrice").innerText;
      const paymentProof = document.getElementById("paymentProof").files[0];
      if (!paymentProof) return alert("يرجى رفع صورة إثبات الدفع.");

      const formDataImg = new FormData();
      formDataImg.append("image", paymentProof);
      const uploadRes = await fetch("https://api.imgbb.com/1/upload?key=bde613bd4475de5e00274a795091ba04", {
        method: "POST", body: formDataImg
      });
      const result = await uploadRes.json();
      const proofUrl = result.data.url;

      const services = [...document.querySelectorAll(".serviceItem")].map(item => {
        const serviceText = item.querySelector(".service").selectedOptions[0].text;
        const quantity = item.querySelector(".area").value || 0;
        return `${serviceText} - ${quantity}`;
      });

      emailjs.send("service_19gxbce", "template_xvxtz3v", {
        name, phone, gender, address, date, location, notes,
        totalPrice, services: services.join("\n"), proofUrl
      }).then(res => {
        console.log("تم إرسال الإيميل بنجاح", res);
      }).catch(err => {
        console.error("فشل في إرسال الإيميل", err);
      });

      fetch("https://script.google.com/macros/s/AKfycbzNvEpweXKg2BxrIfzqHSgRNnIZsYvJWXNWm5vzsAI/dev", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          name, phone, gender, address, date, location, notes,
          totalPrice, services: services.join("\n"), proofUrl
        })
      }).then(res => res.text()).then(console.log).catch(console.error);

      const message = `👤 الاسم: ${name}\n👫 النوع: ${gender}\n📞 الهاتف: ${phone}\n📍 الموقع: ${location}\n📍 العنوان: ${address}\n🗓 التاريخ: ${date}\n📝 ملاحظات: ${notes}\n💰 السعر الإجمالي: ${totalPrice} جنيه\n🚰 الخدمات:\n${services.join("\n")}\n📸 إثبات الدفع: ${proofUrl}`;
      const waUrl = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
      window.open(waUrl, "_blank");

      document.getElementById("loading").style.display = "none";
      document.getElementById("successMessage").style.display = "block";
    }
  </script>

<script>
function convertArabicToEnglishNumbers(str) {
    return str.replace(/[٠-٩]/g, d => "٠١٢٣٤٥٦٧٨٩".indexOf(d));
}

function calculatePrice() {
    let total = 0;
    document.querySelectorAll('.serviceItem').forEach(item => {
        let price = parseFloat(item.querySelector('.service').value);
        let qtyInput = item.querySelector('.area').value;
        let qtyEnglish = convertArabicToEnglishNumbers(qtyInput);
        let qty = parseFloat(qtyEnglish);
        if (!qtyInput || qty <= 0 || isNaN(qty)) qty = 0;
        total += price * qty;
    });
    document.getElementById("totalPrice").innerText = total;
    document.getElementById("halfPrice").innerText = Math.ceil(total / 2);
}
</script>

<script>
window.onload = function () {
    const ua = navigator.userAgent.toLowerCase();
    if (ua.includes('fbav') || ua.includes('instagram')) {
        alert("⚠️ يرجى فتح الصفحة في المتصفح الخارجي (مثل Chrome أو Safari) لضمان عمل الحجز بشكل سليم.");
    }
};
</script>

<script>
function convertArabicToEnglishNumbers(str) {
    return str.replace(/[٠-٩]/g, d => '0123456789'['٠١٢٣٤٥٦٧٨٩'.indexOf(d)]);
}

function calculatePrice() {
    let total = 0;
    document.querySelectorAll('.serviceItem').forEach(item => {
        let price = parseFloat(item.querySelector('.service').value);
        let inputVal = item.querySelector('.area').value;
        let quantity = parseFloat(convertArabicToEnglishNumbers(inputVal)) || 0;
        total += price * quantity;
    });
    document.getElementById('totalPrice').innerText = total;
    document.getElementById('halfPrice').innerText = Math.ceil(total / 2);
}
</script>
</body>


</html>
