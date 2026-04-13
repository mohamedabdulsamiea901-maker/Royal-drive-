<!doctype html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Royal Drive - Firebase Version</title>
    
    <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore-compat.js"></script>

    <script src="https://cdn.tailwindcss.com/3.4.17"></script>
    <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
    
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap');
        * { font-family: 'Cairo', sans-serif; box-sizing: border-box; }
        body { background: #f8fafc; margin: 0; }
        .auth-gradient { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .input-group { position: relative; }
        .eye-icon { position: absolute; left: 12px; top: 42px; cursor: pointer; color: #94a3b8; z-index: 10; }
        .crown-anim { animation: bounce 2s infinite; display: inline-block; }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }
    </style>
</head>
<body>

<div id="app">
    <div id="auth-screen" class="min-h-screen auth-gradient flex items-center justify-center p-4">
        <div class="w-full max-w-md bg-white rounded-[2rem] p-8 shadow-2xl">
            <div class="text-center mb-8">
                <div class="text-6xl mb-2 crown-anim">👑</div>
                <h1 class="text-3xl font-bold text-gray-800">Royal Drive</h1>
                <p class="text-gray-500">نظام الإدارة الآمن</p>
            </div>

            <form id="login-form" onsubmit="handleLogin(event)" class="space-y-5">
                <div class="input-group">
                    <label class="block text-sm font-bold mb-1 text-gray-700">البريد الإلكتروني</label>
                    <input type="email" id="email" required class="w-full p-4 rounded-2xl border-2 border-gray-100 outline-none focus:border-purple-500 transition-all" placeholder="name@company.com">
                </div>
                <div class="input-group">
                    <label class="block text-sm font-bold mb-1 text-gray-700">كلمة المرور</label>
                    <input type="password" id="password" required class="w-full p-4 rounded-2xl border-2 border-gray-100 outline-none focus:border-purple-500 transition-all" placeholder="••••••••">
                    <div class="eye-icon" onclick="togglePass('password')"><i data-lucide="eye" id="eye-icon-svg"></i></div>
                </div>
                <div id="error-msg" class="text-red-500 text-xs hidden text-center font-bold">❌ خطأ في الإيميل أو الباسورد</div>
                <button type="submit" id="login-btn" class="w-full bg-purple-600 text-white py-4 rounded-2xl font-bold shadow-lg hover:bg-purple-700 transition-all active:scale-95">دخول آمن</button>
            </form>
        </div>
    </div>

    <div id="dashboard" class="hidden min-h-screen flex flex-col">
        <nav class="auth-gradient p-5 text-white flex justify-between items-center shadow-xl sticky top-0 z-50">
            <div class="flex items-center gap-3">
                <span class="text-2xl">👑</span>
                <div>
                    <p class="text-[10px] opacity-80 leading-none">مرحباً بك يا مدير</p>
                    <span id="user-display" class="font-bold">المسؤول</span>
                </div>
            </div>
            <button onclick="logout()" class="p-2 bg-white/20 rounded-full hover:bg-white/30 transition"><i data-lucide="log-out"></i></button>
        </nav>

        <div class="p-4 space-y-6 flex-1 overflow-y-auto">
            <div class="grid grid-cols-2 gap-4">
                <div class="bg-white p-5 rounded-3xl shadow-sm border-b-4 border-blue-500">
                    <i data-lucide="users" class="text-blue-500 mb-2 w-5"></i>
                    <p class="text-gray-400 text-[10px]">إجمالي السائقين</p>
                    <p class="text-2xl font-bold" id="drivers-count">0</p>
                </div>
                <div class="bg-white p-5 rounded-3xl shadow-sm border-b-4 border-green-500">
                    <i data-lucide="trending-up" class="text-green-500 mb-2 w-5"></i>
                    <p class="text-gray-400 text-[10px]">رحلات اليوم</p>
                    <p class="text-2xl font-bold">0</p>
                </div>
            </div>

            <div class="bg-white rounded-[2rem] p-6 shadow-sm border border-gray-50">
                <h3 class="font-bold text-gray-800 mb-4 flex items-center gap-2"><i data-lucide="shield-check" class="text-purple-600"></i> خيارات الأمان</h3>
                <button onclick="resetPassword()" class="w-full text-right p-4 bg-orange-50 text-orange-700 rounded-2xl font-bold text-sm flex justify-between items-center transition active:bg-orange-100">
                    تغيير كلمة المرور عبر الإيميل
                    <i data-lucide="mail" class="w-4"></i>
                </button>
            </div>

            <div class="bg-white rounded-[2rem] p-6 shadow-sm">
                <div class="flex justify-between items-center mb-4">
                    <h3 class="font-bold text-gray-800">السائقين في Firestore</h3>
                    <button onclick="addDriverPrompt()" class="bg-blue-600 text-white px-4 py-1 rounded-full text-xs font-bold">+ إضافة</button>
                </div>
                <div id="drivers-list" class="space-y-3 py-4 text-center text-gray-400 text-sm">
                    لا توجد بيانات حالياً في Firestore
                </div>
            </div>
        </div>
    </div>
</div>

<script>
    // الإعدادات التي أرسلتها أنت
    const firebaseConfig = {
      apiKey: "AIzaSyBhZdYXdISIPlcCbC4yiVdlUx0QDWfITdk",
      authDomain: "royal-drive-38c15.firebaseapp.com",
      projectId: "royal-drive-38c15",
      storageBucket: "royal-drive-38c15.firebasestorage.app",
      messagingSenderId: "94912656002",
      appId: "1:94912656002:web:f461fdf7c3cd67b4a77a9b",
      measurementId: "G-ZSFHLWPJKV"
    };

    // تهيئة Firebase
    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();
    const db = firebase.firestore();

    lucide.createIcons();

    // تبديل العين للباسورد
    function togglePass(id) {
        const el = document.getElementById(id);
        el.type = el.type === 'password' ? 'text' : 'password';
    }

    // تسجيل الدخول
    async function handleLogin(e) {
        e.preventDefault();
        const email = document.getElementById('email').value;
        const pass = document.getElementById('password').value;
        const btn = document.getElementById('login-btn');
        const error = document.getElementById('error-msg');

        btn.innerText = "جاري التحقق...";
        error.classList.add('hidden');

        try {
            await auth.signInWithEmailAndPassword(email, pass);
            showDashboard();
        } catch (err) {
            btn.innerText = "دخول آمن";
            error.classList.remove('hidden');
        }
    }

    // عرض لوحة التحكم
    function showDashboard() {
        document.getElementById('auth-screen').classList.add('hidden');
        document.getElementById('dashboard').classList.remove('hidden');
        document.getElementById('user-display').innerText = auth.currentUser.email.split('@')[0];
        loadDrivers();
    }

    // جلب السائقين من Firestore
    function loadDrivers() {
        db.collection('drivers').onSnapshot(snapshot => {
            const list = document.getElementById('drivers-list');
            document.getElementById('drivers-count').innerText = snapshot.size;
            
            if (snapshot.empty) {
                list.innerHTML = "قاعدة البيانات فارغة.. أضف أول سائق!";
                return;
            }

            list.innerHTML = "";
            snapshot.forEach(doc => {
                const d = doc.data();
                list.innerHTML += `
                    <div class="flex justify-between items-center p-4 bg-gray-50 rounded-2xl border border-gray-100">
                        <div class="text-right">
                            <p class="font-bold text-gray-800">${d.name}</p>
                            <p class="text-[10px] text-gray-500">${d.car || 'بدون سيارة'}</p>
                        </div>
                        <i data-lucide="car" class="text-purple-500 w-4"></i>
                    </div>
                `;
            });
            lucide.createIcons();
        });
    }

    // إضافة سائق (تجريبي)
    async function addDriverPrompt() {
        const name = prompt("اسم السائق الجديد:");
        const car = prompt("نوع السيارة:");
        if (name) {
            await db.collection('drivers').add({
                name: name,
                car: car,
                createdAt: firebase.firestore.FieldValue.serverTimestamp()
            });
        }
    }

    // رابط تعيين الباسورد
    async function resetPassword() {
        try {
            await auth.sendPasswordResetEmail(auth.currentUser.email);
            alert("تم إرسال رابط التغيير لإيميلك بنجاح!");
        } catch (err) {
            alert("حدث خطأ: " + err.message);
        }
    }

    function logout() {
        auth.signOut().then(() => location.reload());
    }

    // مراقبة حالة المستخدم
    auth.onAuthStateChanged(user => {
        if (user) showDashboard();
    });
</script>
</body>
</html>
