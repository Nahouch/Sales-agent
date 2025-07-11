# Sales-agent
موقع موظف مبيعات
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>موظف مبيعات - رد فوري</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.rtl.min.css" rel="stylesheet">
  <style>
    body { background: #f8f9fa; font-family: 'Cairo', sans-serif; }
    .card { border-radius: 1rem; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
    .chat-button { background-color: #25D366; color: white; font-size: 1.2rem; padding: 10px 20px; border-radius: 50px; }
  </style>
  <!-- دردشة Tawk.to -->
  <script type="text/javascript">
    var Tawk_API=Tawk_API||{}, Tawk_LoadStart=new Date();
    (function(){
    var s1=document.createElement("script"),s0=document.getElementsByTagName("script")[0];
    s1.async=true;
    s1.src='https://embed.tawk.to/64a7fc17cc26a871b028cb1e/1h59f6rcv';
    s1.charset='UTF-8';
    s1.setAttribute('crossorigin','*');
    s0.parentNode.insertBefore(s1,s0);
    })();
  </script>
</head>
<body>
  <div class="container py-5">
    <div class="text-center mb-4">
      <h1>مرحباً بك!</h1>
      <p class="lead">أنا موظف مبيعات جاهز للرد خلال أقل من 15 ثانية.</p>
    </div>

    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card p-4 text-center">
          <img src="https://via.placeholder.com/150" class="rounded-circle mx-auto mb-3" width="100" alt="صورة الموظف">
          <h3>علي ناحوش</h3>
          <p>خبير مبيعات وتقنيات تواصل سريع</p>
          <a href="https://wa.me/213660000000?text=مرحباً،%20أحتاج%20مساعدة%20في%20الشراء" class="chat-button d-inline-block my-3 text-decoration-none">
            تواصل عبر واتساب الآن
          </a>
          <form onsubmit="registerClient(); return false;">
            <input type="text" id="name" class="form-control mb-2" placeholder="اسمك الكامل" required>
            <input type="email" id="email" class="form-control mb-2" placeholder="البريد الإلكتروني" required>
            <textarea id="message" class="form-control mb-2" placeholder="اكتب سؤالك هنا..." required></textarea>
            <button class="btn btn-primary w-100">أرسل الآن</button>
          </form>
        </div>
      </div>
    </div>
  </div>

  <!-- إشعار فوري + حفظ البيانات في localStorage -->
  <script>
    function registerClient() {
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const msg = document.getElementById('message').value;

      // حفظ في LocalStorage
      let clients = JSON.parse(localStorage.getItem('clients') || '[]');
      clients.push({ name, email, msg, time: new Date().toLocaleString() });
      localStorage.setItem('clients', JSON.stringify(clients));

      alert("✅ تم استلام رسالتك بنجاح!\nسنرد عليك خلال لحظات يا " + name);

      // إعادة تعيين النموذج
      document.getElementById('name').value = '';
      document.getElementById('email').value = '';
      document.getElementById('message').value = '';
    }
  </script>
</body>
</html>
