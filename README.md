<html lang="th" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>คณิตศาสตร์ ร้อยละ</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    * {
      font-family: 'Kanit', sans-serif;
    }
    .gradient-bg {
      background: linear-gradient(135deg, #ff9ad5 0%, #ffb88a 30%, #ff8cc9 70%, #ffaad9 100%);
    }
    .card-shadow {
      box-shadow: 0 10px 40px rgba(0,0,0,0.15);
    }
    .btn-bounce:hover {
      transform: scale(1.05);
    }
    .btn-bounce:active {
      transform: scale(0.95);
    }
    .progress-bar {
      transition: width 0.5s ease;
    }
    @keyframes celebrate {
      0%, 100% { transform: scale(1) rotate(0deg); }
      25% { transform: scale(1.1) rotate(-5deg); }
      75% { transform: scale(1.1) rotate(5deg); }
    }
    .celebrate {
      animation: celebrate 0.5s ease;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .float-animation {
      animation: float 3s ease-in-out infinite;
    }
    @keyframes slideIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .slide-in {
      animation: slideIn 0.4s ease;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div id="app" class="h-full gradient-bg overflow-auto">
   <div class="min-h-full p-4 md:p-8"><!-- Header -->
    <header class="text-center mb-6">
     <div class="inline-block bg-white/20 backdrop-blur-sm rounded-full px-6 py-2 mb-4"><span class="text-white text-lg">🎓 ชั้นประถมศึกษาปีที่ 5</span>
     </div>
     <h1 class="text-3xl md:text-5xl font-bold text-white drop-shadow-lg mb-2"><span id="subject-name">วิชาคณิตศาสตร์</span></h1>
     <h2 class="text-2xl md:text-4xl font-semibold text-white/95 drop-shadow mb-3">เรื่อง <span id="lesson-topic">ร้อยละ</span></h2>
     <p id="welcome-text" class="text-white/90 text-lg mb-3">เรียนรู้เรื่องร้อยละกันเถอะ 🚀</p>
     <p id="teacher-name" class="text-white/80 text-base">จัดทำโดย ครูวิรัลพัชษ์ สว่างเดือน</p>
    </header><!-- Navigation Tabs -->
    <nav class="flex justify-center gap-2 mb-6 flex-wrap"><button onclick="showSection('learn')" id="tab-learn" class="tab-btn bg-white text-purple-600 px-4 py-2 rounded-full font-medium transition-all btn-bounce shadow-lg"> 📚 เรียนรู้ </button> <button onclick="showSection('practice')" id="tab-practice" class="tab-btn bg-white/30 text-white px-4 py-2 rounded-full font-medium transition-all btn-bounce"> ✏️ ฝึกทำ </button> <button onclick="showSection('quiz')" id="tab-quiz" class="tab-btn bg-white/30 text-white px-4 py-2 rounded-full font-medium transition-all btn-bounce"> 📝 ทดสอบ </button> <button onclick="showSection('games')" id="tab-games" class="tab-btn bg-white/30 text-white px-4 py-2 rounded-full font-medium transition-all btn-bounce"> 🎮 เกม </button>
    </nav><!-- Main Content -->
    <main class="max-w-4xl mx-auto"><!-- Learn Section -->
     <section id="section-learn" class="slide-in">
      <div class="bg-white rounded-3xl card-shadow p-6 md:p-8">
       <h2 class="text-2xl font-bold text-purple-600 mb-6 flex items-center gap-2"><span class="text-3xl">📖</span> ร้อยละคืออะไร?</h2><!-- Visual Explanation -->
       <div class="bg-gradient-to-r from-purple-50 to-pink-50 rounded-2xl p-6 mb-6">
        <div class="flex flex-col md:flex-row items-center gap-6">
         <div class="flex-1">
          <p class="text-gray-700 text-lg mb-4"><strong class="text-purple-600">ร้อยละ (Percent)</strong> หมายถึง "ต่อร้อย" หรือ "ใน 100 ส่วน"</p>
          <p class="text-gray-600 mb-4">สัญลักษณ์ <span class="text-3xl font-bold text-pink-500">%</span> ใช้แทนคำว่าร้อยละ</p>
          <div class="bg-white rounded-xl p-4 border-2 border-purple-200">
           <p class="text-purple-700 font-medium">ตัวอย่าง:</p>
           <p class="text-gray-700">25% หมายถึง 25 ใน 100 ส่วน</p>
           <p class="text-gray-700">หรือเขียนเป็นเศษส่วนได้ว่า 25/100</p>
          </div>
         </div>
         <div class="w-48 h-48 relative"><!-- 10x10 Grid Visual -->
          <div class="grid grid-cols-10 gap-0.5 w-full h-full" id="percent-grid">
          </div>
          <p class="text-center mt-2 font-bold text-purple-600" id="grid-label">25%</p>
         </div>
        </div>
       </div><!-- Interactive Slider -->
       <div class="bg-yellow-50 rounded-2xl p-6 mb-6">
        <h3 class="text-xl font-bold text-yellow-700 mb-4">🎚️ ลองปรับดูเอง!</h3><input type="range" min="0" max="100" value="25" id="percent-slider" class="w-full h-3 bg-yellow-200 rounded-lg appearance-none cursor-pointer accent-yellow-500" oninput="updateGrid(this.value)">
        <p class="text-center text-2xl font-bold text-yellow-600 mt-2"><span id="slider-value">25</span>%</p>
       </div><!-- Formula Cards -->
       <h3 class="text-xl font-bold text-purple-600 mb-4">📐 สูตรการคำนวณ</h3>
       <div class="grid md:grid-cols-2 gap-4">
        <div class="bg-blue-50 rounded-xl p-5 border-l-4 border-blue-500">
         <h4 class="font-bold text-blue-700 mb-2">หาร้อยละของจำนวน</h4>
         <p class="text-blue-600 font-mono text-lg">ร้อยละ × จำนวน ÷ 100</p>
         <p class="text-gray-600 text-sm mt-2">ตัวอย่าง: 20% ของ 50 = 20 × 50 ÷ 100 = 10</p>
        </div>
        <div class="bg-green-50 rounded-xl p-5 border-l-4 border-green-500">
         <h4 class="font-bold text-green-700 mb-2">หาว่าเป็นร้อยละเท่าไร</h4>
         <p class="text-green-600 font-mono text-lg">จำนวนที่ต้องการ × 100 ÷ จำนวนทั้งหมด</p>
         <p class="text-gray-600 text-sm mt-2">ตัวอย่าง: 15 เป็นร้อยละเท่าไรของ 60 = 15 × 100 ÷ 60 = 25%</p>
        </div>
       </div><!-- Real Life Examples -->
       <h3 class="text-xl font-bold text-purple-600 mt-6 mb-4">🛒 ตัวอย่างในชีวิตจริง</h3>
       <div class="grid md:grid-cols-3 gap-4">
        <div class="bg-red-50 rounded-xl p-4 text-center"><span class="text-4xl">🏷️</span>
         <p class="font-bold text-red-600 mt-2">ลดราคา 30%</p>
         <p class="text-gray-600 text-sm">สินค้าราคา 100 บาท<br>
          ลดเหลือ 70 บาท</p>
        </div>
        <div class="bg-orange-50 rounded-xl p-4 text-center"><span class="text-4xl">📊</span>
         <p class="font-bold text-orange-600 mt-2">คะแนนสอบ 80%</p>
         <p class="text-gray-600 text-sm">ได้ 80 คะแนน<br>
          จากคะแนนเต็ม 100</p>
        </div>
        <div class="bg-teal-50 rounded-xl p-4 text-center"><span class="text-4xl">💰</span>
         <p class="font-bold text-teal-600 mt-2">ดอกเบี้ย 5%</p>
         <p class="text-gray-600 text-sm">ฝากเงิน 1,000 บาท<br>
          ได้ดอกเบี้ย 50 บาท</p>
        </div>
       </div>
      </div>
     </section><!-- Practice Section -->
     <section id="section-practice" class="hidden slide-in">
      <div class="bg-white rounded-3xl card-shadow p-6 md:p-8">
       <h2 class="text-2xl font-bold text-purple-600 mb-6 flex items-center gap-2"><span class="text-3xl">✏️</span> ฝึกคำนวณร้อยละ</h2><!-- Calculator -->
       <div class="bg-gradient-to-r from-indigo-50 to-purple-50 rounded-2xl p-6 mb-6">
        <h3 class="text-xl font-bold text-indigo-700 mb-4">🧮 เครื่องคำนวณร้อยละ</h3>
        <div class="grid md:grid-cols-2 gap-6"><!-- Find Percent of Number -->
         <div class="bg-white rounded-xl p-5 shadow">
          <h4 class="font-bold text-indigo-600 mb-3">หาร้อยละของจำนวน</h4>
          <div class="space-y-3">
           <div><label class="text-gray-600 text-sm" for="calc1-percent">ร้อยละ</label> <input type="number" id="calc1-percent" placeholder="เช่น 25" class="w-full p-3 border-2 border-indigo-200 rounded-lg focus:border-indigo-500 focus:outline-none">
           </div>
           <div><label class="text-gray-600 text-sm" for="calc1-number">ของจำนวน</label> <input type="number" id="calc1-number" placeholder="เช่น 200" class="w-full p-3 border-2 border-indigo-200 rounded-lg focus:border-indigo-500 focus:outline-none">
           </div><button onclick="calculatePercentOf()" class="w-full bg-indigo-500 hover:bg-indigo-600 text-white py-3 rounded-lg font-bold transition btn-bounce"> คำนวณ </button>
           <div id="calc1-result" class="text-center text-xl font-bold text-indigo-700 p-3 bg-indigo-100 rounded-lg hidden"></div>
          </div>
         </div><!-- Find What Percent -->
         <div class="bg-white rounded-xl p-5 shadow">
          <h4 class="font-bold text-green-600 mb-3">หาว่าเป็นร้อยละเท่าไร</h4>
          <div class="space-y-3">
           <div><label class="text-gray-600 text-sm" for="calc2-part">จำนวนที่ต้องการหา</label> <input type="number" id="calc2-part" placeholder="เช่น 15" class="w-full p-3 border-2 border-green-200 rounded-lg focus:border-green-500 focus:outline-none">
           </div>
           <div><label class="text-gray-600 text-sm" for="calc2-total">จำนวนทั้งหมด</label> <input type="number" id="calc2-total" placeholder="เช่น 60" class="w-full p-3 border-2 border-green-200 rounded-lg focus:border-green-500 focus:outline-none">
           </div><button onclick="calculateWhatPercent()" class="w-full bg-green-500 hover:bg-green-600 text-white py-3 rounded-lg font-bold transition btn-bounce"> คำนวณ </button>
           <div id="calc2-result" class="text-center text-xl font-bold text-green-700 p-3 bg-green-100 rounded-lg hidden"></div>
          </div>
         </div>
        </div>
       </div><!-- Car Loan Calculator -->
       <div class="bg-gradient-to-r from-emerald-50 to-teal-50 rounded-2xl p-6 mb-6">
        <h3 class="text-xl font-bold text-emerald-700 mb-4">🚗 คำนวณการผ่อนรถ</h3>
        <div class="bg-white rounded-xl p-5 shadow space-y-4">
         <div><label class="text-gray-600 text-sm font-medium" for="car-price">ราคารถเต็ม (บาท)</label> <input type="number" id="car-price" placeholder="เช่น 500000" class="w-full p-3 border-2 border-emerald-200 rounded-lg focus:border-emerald-500 focus:outline-none">
         </div>
         <div><label class="text-gray-600 text-sm font-medium" for="down-payment">เงินดาวน์ (ร้อยละ)</label> <input type="number" id="down-payment" placeholder="เช่น 20" class="w-full p-3 border-2 border-emerald-200 rounded-lg focus:border-emerald-500 focus:outline-none">
          <p class="text-xs text-gray-500 mt-1">กรอกเป็นร้อยละ เช่น 20 หมายถึง 20%</p>
         </div>
         <div><label class="text-gray-600 text-sm font-medium" for="interest-rate">ดอกเบี้ย (ร้อยละต่อปี)</label> <input type="number" id="interest-rate" placeholder="เช่น 5" step="0.1" class="w-full p-3 border-2 border-emerald-200 rounded-lg focus:border-emerald-500 focus:outline-none">
          <p class="text-xs text-gray-500 mt-1">กรอกเป็นร้อยละต่อปี เช่น 5 หมายถึง 5%</p>
         </div>
         <div><label class="text-gray-600 text-sm font-medium" for="loan-months">จำนวนเดือนที่ผ่อน</label> <input type="number" id="loan-months" placeholder="เช่น 60" class="w-full p-3 border-2 border-emerald-200 rounded-lg focus:border-emerald-500 focus:outline-none">
          <p class="text-xs text-gray-500 mt-1">ระบุจำนวนเดือน เช่น 60 เดือน (5 ปี)</p>
         </div><button onclick="calculateCarLoan()" class="w-full bg-emerald-500 hover:bg-emerald-600 text-white py-3 rounded-lg font-bold transition btn-bounce"> 🧮 คำนวณ </button>
         <div id="car-loan-result" class="hidden bg-gradient-to-r from-emerald-100 to-teal-100 p-5 rounded-xl space-y-3">
          <h4 class="font-bold text-emerald-700 text-lg mb-3">📊 ผลการคำนวณ</h4>
          <div class="grid grid-cols-2 gap-3">
           <div class="bg-white p-3 rounded-lg">
            <p class="text-gray-600 text-sm">เงินดาวน์</p>
            <p class="text-emerald-700 font-bold text-xl" id="down-amount">0</p>
            <p class="text-gray-500 text-xs">บาท</p>
           </div>
           <div class="bg-white p-3 rounded-lg">
            <p class="text-gray-600 text-sm">ยอดจัดไฟแนนซ์</p>
            <p class="text-teal-700 font-bold text-xl" id="finance-amount">0</p>
            <p class="text-gray-500 text-xs">บาท</p>
           </div>
           <div class="bg-white p-3 rounded-lg">
            <p class="text-gray-600 text-sm">ดอกเบี้ยรวม</p>
            <p class="text-orange-600 font-bold text-xl" id="total-interest">0</p>
            <p class="text-gray-500 text-xs">บาท</p>
           </div>
           <div class="bg-white p-3 rounded-lg">
            <p class="text-gray-600 text-sm">ยอดรวมทั้งหมด</p>
            <p class="text-purple-700 font-bold text-xl" id="total-payment">0</p>
            <p class="text-gray-500 text-xs">บาท</p>
           </div>
          </div>
          <div class="bg-gradient-to-r from-pink-500 to-rose-500 text-white p-4 rounded-xl text-center">
           <p class="text-sm opacity-90">ผ่อนต่อเดือน</p>
           <p class="text-3xl font-bold" id="monthly-payment">0</p>
           <p class="text-sm opacity-90">บาท/เดือน</p>
          </div>
          <div class="bg-blue-50 p-4 rounded-lg text-sm text-gray-700">
           <p class="font-medium text-blue-700 mb-2">💡 รายละเอียด:</p>
           <p id="loan-detail-text">-</p>
          </div>
         </div>
        </div>
       </div><!-- Word Problems -->
       <h3 class="text-xl font-bold text-purple-600 mb-4">📝 โจทย์ปัญหา</h3>
       <div id="practice-problem" class="bg-yellow-50 rounded-2xl p-6">
        <div class="flex items-start gap-4"><span class="text-4xl" id="problem-emoji">🛒</span>
         <div class="flex-1">
          <p class="text-lg text-gray-700 mb-4" id="problem-text">กำลังโหลดโจทย์...</p>
          <div class="flex gap-3 items-center"><input type="number" id="practice-answer" placeholder="คำตอบ" class="flex-1 p-3 border-2 border-yellow-300 rounded-lg focus:border-yellow-500 focus:outline-none text-lg"> <button onclick="checkPracticeAnswer()" class="bg-yellow-500 hover:bg-yellow-600 text-white px-6 py-3 rounded-lg font-bold transition btn-bounce"> ตรวจ </button>
          </div>
          <div id="practice-feedback" class="mt-3 text-center font-bold hidden"></div>
         </div>
        </div>
       </div><button onclick="newPracticeProblem()" class="mt-4 w-full bg-purple-100 hover:bg-purple-200 text-purple-700 py-3 rounded-xl font-bold transition"> 🔄 โจทย์ใหม่ </button>
      </div>
     </section><!-- Quiz Section -->
     <section id="section-quiz" class="hidden slide-in">
      <div class="bg-white rounded-3xl card-shadow p-6 md:p-8">
       <div id="quiz-start" class="text-center"><span class="text-6xl mb-4 inline-block float-animation">🎯</span>
        <h2 class="text-2xl font-bold text-purple-600 mb-4">ทดสอบความรู้เรื่องร้อยละ</h2>
        <p class="text-gray-600 mb-6">ตอบคำถาม 10 ข้อ เพื่อทดสอบความเข้าใจ</p><button onclick="startQuiz()" class="bg-gradient-to-r from-purple-500 to-pink-500 hover:from-purple-600 hover:to-pink-600 text-white px-8 py-4 rounded-full font-bold text-xl transition btn-bounce shadow-lg"> เริ่มทำข้อสอบ </button>
       </div>
       <div id="quiz-content" class="hidden"><!-- Progress -->
        <div class="mb-6">
         <div class="flex justify-between text-sm text-gray-600 mb-2"><span>ข้อที่ <span id="quiz-current">1</span> / 10</span> <span>คะแนน: <span id="quiz-score">0</span></span>
         </div>
         <div class="h-3 bg-gray-200 rounded-full overflow-hidden">
          <div id="quiz-progress" class="h-full bg-gradient-to-r from-purple-500 to-pink-500 progress-bar" style="width: 10%"></div>
         </div>
        </div><!-- Question -->
        <div class="bg-purple-50 rounded-2xl p-6 mb-6">
         <p class="text-xl text-gray-700" id="quiz-question">คำถาม</p>
        </div><!-- Options -->
        <div id="quiz-options" class="grid grid-cols-2 gap-4">
        </div>
        <div id="quiz-feedback" class="mt-4 text-center text-lg font-bold hidden"></div>
       </div>
       <div id="quiz-result" class="hidden text-center"><span class="text-6xl mb-4 inline-block" id="result-emoji">🎉</span>
        <h2 class="text-2xl font-bold text-purple-600 mb-2">ทำข้อสอบเสร็จแล้ว!</h2>
        <p class="text-4xl font-bold text-pink-500 mb-4"><span id="final-score">0</span>/10 คะแนน</p>
        <p class="text-gray-600 mb-6" id="result-message">เยี่ยมมาก!</p><button onclick="resetQuiz()" class="bg-purple-500 hover:bg-purple-600 text-white px-8 py-3 rounded-full font-bold transition btn-bounce"> ทำใหม่อีกครั้ง </button>
       </div>
      </div>
     </section><!-- Games Section -->
     <section id="section-games" class="hidden slide-in">
      <div class="bg-white rounded-3xl card-shadow p-6 md:p-8">
       <h2 class="text-2xl font-bold text-purple-600 mb-6 flex items-center gap-2"><span class="text-3xl">🎮</span> เกมร้อยละ</h2><!-- Discount Game -->
       <div class="bg-gradient-to-r from-red-50 to-orange-50 rounded-2xl p-6 mb-6">
        <h3 class="text-xl font-bold text-red-600 mb-4">🏷️ เกมคำนวณส่วนลด</h3>
        <p class="text-gray-600 mb-4">คำนวณราคาหลังลดให้ถูกต้องภายใน 10 วินาที!</p>
        <div id="discount-game" class="text-center">
         <div class="bg-white rounded-xl p-6 mb-4 shadow-inner">
          <p class="text-gray-600">สินค้าราคา</p>
          <p class="text-4xl font-bold text-orange-500" id="game-original-price">0</p>
          <p class="text-gray-600">บาท</p>
          <div class="inline-block bg-red-500 text-white px-4 py-2 rounded-full font-bold mt-3">
           ลด <span id="game-discount">0</span>%
          </div>
         </div>
         <div id="game-timer" class="text-2xl font-bold text-gray-600 mb-4">
          ⏱️ 10
         </div>
         <div class="flex gap-2 justify-center flex-wrap" id="game-options"></div>
         <div id="game-feedback" class="mt-4 text-xl font-bold hidden"></div>
         <div class="mt-4">
          <p class="text-gray-600">คะแนน: <span id="game-score" class="font-bold text-purple-600">0</span></p>
         </div>
        </div><button onclick="startDiscountGame()" id="game-start-btn" class="mt-4 w-full bg-red-500 hover:bg-red-600 text-white py-3 rounded-xl font-bold transition btn-bounce"> 🎮 เริ่มเกม </button>
       </div><!-- Percentage Bar Game -->
       <div class="bg-gradient-to-r from-blue-50 to-cyan-50 rounded-2xl p-6">
        <h3 class="text-xl font-bold text-blue-600 mb-4">📊 เกมประมาณค่าร้อยละ</h3>
        <p class="text-gray-600 mb-4">ประมาณว่าแถบสีเป็นร้อยละเท่าไร</p>
        <div class="bg-white rounded-xl p-6 shadow-inner">
         <div class="h-8 bg-gray-200 rounded-full overflow-hidden mb-4">
          <div id="estimate-bar" class="h-full bg-gradient-to-r from-blue-400 to-cyan-400" style="width: 50%"></div>
         </div>
         <div class="flex gap-2 justify-center flex-wrap" id="estimate-options"></div>
         <div id="estimate-feedback" class="mt-4 text-center font-bold hidden"></div>
         <p class="text-center text-gray-600 mt-3">คะแนน: <span id="estimate-score" class="font-bold text-blue-600">0</span></p>
        </div><button onclick="startEstimateGame()" id="estimate-start-btn" class="mt-4 w-full bg-blue-500 hover:bg-blue-600 text-white py-3 rounded-xl font-bold transition btn-bounce"> 🎮 เริ่มเกม </button>
       </div>
      </div>
     </section>
    </main><!-- Footer -->
    <footer class="text-center mt-8 text-white/80 pb-4">
     <p>🎓 เรียนรู้คณิตศาสตร์อย่างสนุกสนาน!</p>
     <p class="mt-2 text-white/70">สื่อการสอนครูตาว</p>
    </footer>
   </div>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      subject_name: 'วิชาคณิตศาสตร์',
      lesson_topic: 'ร้อยละ',
      welcome_message: 'เรียนรู้เรื่องร้อยละกันเถอะ',
      teacher_name: 'จัดทำโดย ครูวิรัลพัชษ์ สว่างเดือน',
      primary_color: '#667eea',
      secondary_color: '#764ba2',
      accent_color: '#f093fb'
    };

    let config = { ...defaultConfig };

    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange: async (newConfig) => {
          config = { ...defaultConfig, ...newConfig };
          document.getElementById('subject-name').textContent = config.subject_name || defaultConfig.subject_name;
          document.getElementById('lesson-topic').textContent = config.lesson_topic || defaultConfig.lesson_topic;
          document.getElementById('welcome-text').textContent = (config.welcome_message || defaultConfig.welcome_message) + ' 🚀';
          document.getElementById('teacher-name').textContent = config.teacher_name || defaultConfig.teacher_name;
        },
        mapToCapabilities: (config) => ({
          recolorables: [],
          borderables: [],
          fontEditable: undefined,
          fontSizeable: undefined
        }),
        mapToEditPanelValues: (config) => new Map([
          ['subject_name', config.subject_name || defaultConfig.subject_name],
          ['lesson_topic', config.lesson_topic || defaultConfig.lesson_topic],
          ['welcome_message', config.welcome_message || defaultConfig.welcome_message],
          ['teacher_name', config.teacher_name || defaultConfig.teacher_name]
        ])
      });
    }

    // Section Navigation
    function showSection(section) {
      const sections = ['learn', 'practice', 'quiz', 'games'];
      sections.forEach(s => {
        document.getElementById(`section-${s}`).classList.add('hidden');
        document.getElementById(`tab-${s}`).classList.remove('bg-white', 'text-purple-600', 'shadow-lg');
        document.getElementById(`tab-${s}`).classList.add('bg-white/30', 'text-white');
      });
      document.getElementById(`section-${section}`).classList.remove('hidden');
      document.getElementById(`tab-${section}`).classList.remove('bg-white/30', 'text-white');
      document.getElementById(`tab-${section}`).classList.add('bg-white', 'text-purple-600', 'shadow-lg');
      
      if (section === 'practice') {
        newPracticeProblem();
      }
    }

    // Initialize Grid
    function initGrid() {
      const grid = document.getElementById('percent-grid');
      grid.innerHTML = '';
      for (let i = 0; i < 100; i++) {
        const cell = document.createElement('div');
        cell.className = 'rounded-sm transition-colors duration-200';
        cell.style.backgroundColor = i < 25 ? '#8b5cf6' : '#e5e7eb';
        grid.appendChild(cell);
      }
    }

    function updateGrid(value) {
      const grid = document.getElementById('percent-grid');
      const cells = grid.children;
      for (let i = 0; i < 100; i++) {
        cells[i].style.backgroundColor = i < value ? '#8b5cf6' : '#e5e7eb';
      }
      document.getElementById('slider-value').textContent = value;
      document.getElementById('grid-label').textContent = value + '%';
    }

    // Calculators
    function calculatePercentOf() {
      const percent = parseFloat(document.getElementById('calc1-percent').value);
      const number = parseFloat(document.getElementById('calc1-number').value);
      const resultDiv = document.getElementById('calc1-result');
      
      if (isNaN(percent) || isNaN(number)) {
        resultDiv.textContent = '❌ กรุณากรอกตัวเลขให้ครบ';
        resultDiv.classList.remove('hidden', 'bg-indigo-100', 'text-indigo-700');
        resultDiv.classList.add('bg-red-100', 'text-red-700');
        return;
      }
      
      const result = (percent * number) / 100;
      resultDiv.textContent = `✅ ${percent}% ของ ${number} = ${result}`;
      resultDiv.classList.remove('hidden', 'bg-red-100', 'text-red-700');
      resultDiv.classList.add('bg-indigo-100', 'text-indigo-700');
    }

    function calculateWhatPercent() {
      const part = parseFloat(document.getElementById('calc2-part').value);
      const total = parseFloat(document.getElementById('calc2-total').value);
      const resultDiv = document.getElementById('calc2-result');
      
      if (isNaN(part) || isNaN(total) || total === 0) {
        resultDiv.textContent = '❌ กรุณากรอกตัวเลขให้ครบ';
        resultDiv.classList.remove('hidden', 'bg-green-100', 'text-green-700');
        resultDiv.classList.add('bg-red-100', 'text-red-700');
        return;
      }
      
      const result = (part * 100) / total;
      resultDiv.textContent = `✅ ${part} คิดเป็น ${result.toFixed(2)}% ของ ${total}`;
      resultDiv.classList.remove('hidden', 'bg-red-100', 'text-red-700');
      resultDiv.classList.add('bg-green-100', 'text-green-700');
    }

    // Car Loan Calculator
    function calculateCarLoan() {
      const carPrice = parseFloat(document.getElementById('car-price').value);
      const downPaymentPercent = parseFloat(document.getElementById('down-payment').value);
      const interestRate = parseFloat(document.getElementById('interest-rate').value);
      const loanMonths = parseInt(document.getElementById('loan-months').value);
      const resultDiv = document.getElementById('car-loan-result');
      
      if (isNaN(carPrice) || isNaN(downPaymentPercent) || isNaN(interestRate) || isNaN(loanMonths)) {
        resultDiv.classList.remove('hidden');
        document.getElementById('loan-detail-text').textContent = '❌ กรุณากรอกข้อมูลให้ครบทุกช่อง';
        return;
      }
      
      if (carPrice <= 0 || downPaymentPercent < 0 || downPaymentPercent > 100 || interestRate < 0 || loanMonths <= 0) {
        resultDiv.classList.remove('hidden');
        document.getElementById('loan-detail-text').textContent = '❌ กรุณากรอกข้อมูลที่ถูกต้อง';
        return;
      }
      
      // Calculate down payment
      const downAmount = (downPaymentPercent / 100) * carPrice;
      
      // Calculate finance amount
      const financeAmount = carPrice - downAmount;
      
      // Calculate monthly interest rate
      const monthlyRate = interestRate / 100 / 12;
      
      // Calculate monthly payment using formula: P * [r(1+r)^n] / [(1+r)^n - 1]
      let monthlyPayment;
      if (monthlyRate === 0) {
        monthlyPayment = financeAmount / loanMonths;
      } else {
        const power = Math.pow(1 + monthlyRate, loanMonths);
        monthlyPayment = financeAmount * (monthlyRate * power) / (power - 1);
      }
      
      // Calculate totals
      const totalPayment = monthlyPayment * loanMonths;
      const totalInterest = totalPayment - financeAmount;
      
      // Display results
      document.getElementById('down-amount').textContent = downAmount.toLocaleString('th-TH', {maximumFractionDigits: 0});
      document.getElementById('finance-amount').textContent = financeAmount.toLocaleString('th-TH', {maximumFractionDigits: 0});
      document.getElementById('total-interest').textContent = totalInterest.toLocaleString('th-TH', {maximumFractionDigits: 0});
      document.getElementById('total-payment').textContent = totalPayment.toLocaleString('th-TH', {maximumFractionDigits: 0});
      document.getElementById('monthly-payment').textContent = monthlyPayment.toLocaleString('th-TH', {maximumFractionDigits: 0});
      
      const years = Math.floor(loanMonths / 12);
      const months = loanMonths % 12;
      let periodText = '';
      if (years > 0) periodText += years + ' ปี';
      if (months > 0) periodText += (years > 0 ? ' ' : '') + months + ' เดือน';
      
      document.getElementById('loan-detail-text').textContent = 
        `ราคารถ ${carPrice.toLocaleString('th-TH')} บาท วางเงินดาวน์ ${downPaymentPercent}% (${downAmount.toLocaleString('th-TH')} บาท) ` +
        `จัดไฟแนนซ์ ${financeAmount.toLocaleString('th-TH')} บาท ดอกเบี้ย ${interestRate}% ต่อปี ผ่อนชำระ ${periodText} ` +
        `(${loanMonths} งวด) จ่ายเดือนละ ${monthlyPayment.toLocaleString('th-TH', {maximumFractionDigits: 0})} บาท`;
      
      resultDiv.classList.remove('hidden');
    }

    // Practice Problems
    const practiceProblems = [
      { emoji: '🛒', text: 'สินค้าราคา 200 บาท ลดราคา 25% จะเหลือกี่บาท?', answer: 150 },
      { emoji: '📊', text: 'นักเรียน 40 คน สอบผ่าน 30 คน คิดเป็นร้อยละเท่าไร?', answer: 75 },
      { emoji: '💰', text: '15% ของ 300 บาท คือเท่าไร?', answer: 45 },
      { emoji: '🍕', text: 'พิซซ่า 1 ถาดมี 8 ชิ้น กินไป 4 ชิ้น กินไปร้อยละเท่าไร?', answer: 50 },
      { emoji: '📚', text: 'หนังสือมี 80 หน้า อ่านไปแล้ว 20% อ่านไปกี่หน้า?', answer: 16 },
      { emoji: '🎁', text: 'ของขวัญราคา 500 บาท ลด 10% ต้องจ่ายกี่บาท?', answer: 450 },
      { emoji: '🏀', text: 'ทีมบาสได้ 60 คะแนน ยิง 3 แต้มได้ 30% ได้กี่คะแนนจากลูก 3 แต้ม?', answer: 18 },
      { emoji: '🌳', text: 'สวนมีต้นไม้ 50 ต้น เป็นต้นมะม่วง 40% มีต้นมะม่วงกี่ต้น?', answer: 20 }
    ];

    let currentPracticeProblem = null;

    function newPracticeProblem() {
      currentPracticeProblem = practiceProblems[Math.floor(Math.random() * practiceProblems.length)];
      document.getElementById('problem-emoji').textContent = currentPracticeProblem.emoji;
      document.getElementById('problem-text').textContent = currentPracticeProblem.text;
      document.getElementById('practice-answer').value = '';
      document.getElementById('practice-feedback').classList.add('hidden');
    }

    function checkPracticeAnswer() {
      const userAnswer = parseFloat(document.getElementById('practice-answer').value);
      const feedback = document.getElementById('practice-feedback');
      
      if (isNaN(userAnswer)) {
        feedback.textContent = '❌ กรุณากรอกคำตอบ';
        feedback.className = 'mt-3 text-center font-bold text-red-500';
        feedback.classList.remove('hidden');
        return;
      }
      
      if (userAnswer === currentPracticeProblem.answer) {
        feedback.textContent = '✅ ถูกต้อง! เก่งมาก!';
        feedback.className = 'mt-3 text-center font-bold text-green-500 celebrate';
      } else {
        feedback.textContent = `❌ ไม่ถูกต้อง คำตอบคือ ${currentPracticeProblem.answer}`;
        feedback.className = 'mt-3 text-center font-bold text-red-500';
      }
      feedback.classList.remove('hidden');
    }

    // Quiz System
    const quizQuestions = [
      { q: '50% ของ 100 คือเท่าใด?', options: [25, 50, 75, 100], answer: 50 },
      { q: '25% ของ 80 คือเท่าใด?', options: [15, 20, 25, 30], answer: 20 },
      { q: '10% ของ 250 คือเท่าใด?', options: [20, 25, 30, 35], answer: 25 },
      { q: '20 เป็นร้อยละเท่าใดของ 100?', options: [10, 15, 20, 25], answer: 20 },
      { q: '15 เป็นร้อยละเท่าใดของ 60?', options: [15, 20, 25, 30], answer: 25 },
      { q: 'ลดราคา 20% จาก 150 บาท เหลือกี่บาท?', options: [100, 110, 120, 130], answer: 120 },
      { q: '75% ของ 40 คือเท่าใด?', options: [25, 30, 35, 40], answer: 30 },
      { q: '30% ของ 200 คือเท่าใด?', options: [40, 50, 60, 70], answer: 60 },
      { q: '12 เป็นร้อยละเท่าใดของ 48?', options: [20, 25, 30, 35], answer: 25 },
      { q: 'ลดราคา 50% จาก 80 บาท เหลือกี่บาท?', options: [30, 35, 40, 45], answer: 40 },
      { q: '5% ของ 400 คือเท่าใด?', options: [15, 20, 25, 30], answer: 20 },
      { q: '40% ของ 50 คือเท่าใด?', options: [15, 20, 25, 30], answer: 20 }
    ];

    let quizState = { current: 0, score: 0, questions: [] };

    function shuffleArray(array) {
      const newArray = [...array];
      for (let i = newArray.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [newArray[i], newArray[j]] = [newArray[j], newArray[i]];
      }
      return newArray;
    }

    function startQuiz() {
      quizState = { current: 0, score: 0, questions: shuffleArray(quizQuestions).slice(0, 10) };
      document.getElementById('quiz-start').classList.add('hidden');
      document.getElementById('quiz-content').classList.remove('hidden');
      document.getElementById('quiz-result').classList.add('hidden');
      showQuizQuestion();
    }

    function showQuizQuestion() {
      const q = quizState.questions[quizState.current];
      document.getElementById('quiz-current').textContent = quizState.current + 1;
      document.getElementById('quiz-score').textContent = quizState.score;
      document.getElementById('quiz-progress').style.width = ((quizState.current + 1) * 10) + '%';
      document.getElementById('quiz-question').textContent = q.q;
      document.getElementById('quiz-feedback').classList.add('hidden');
      
      const optionsDiv = document.getElementById('quiz-options');
      optionsDiv.innerHTML = '';
      shuffleArray(q.options).forEach(opt => {
        const btn = document.createElement('button');
        btn.className = 'bg-purple-100 hover:bg-purple-200 text-purple-700 p-4 rounded-xl font-bold text-xl transition btn-bounce';
        btn.textContent = opt;
        btn.onclick = () => checkQuizAnswer(opt, q.answer);
        optionsDiv.appendChild(btn);
      });
    }

    function checkQuizAnswer(selected, correct) {
      const feedback = document.getElementById('quiz-feedback');
      const buttons = document.getElementById('quiz-options').children;
      
      for (let btn of buttons) {
        btn.disabled = true;
        if (parseInt(btn.textContent) === correct) {
          btn.classList.remove('bg-purple-100', 'hover:bg-purple-200');
          btn.classList.add('bg-green-500', 'text-white');
        } else if (parseInt(btn.textContent) === selected && selected !== correct) {
          btn.classList.remove('bg-purple-100', 'hover:bg-purple-200');
          btn.classList.add('bg-red-500', 'text-white');
        }
      }
      
      if (selected === correct) {
        quizState.score++;
        feedback.textContent = '🎉 ถูกต้อง!';
        feedback.className = 'mt-4 text-center text-lg font-bold text-green-500 celebrate';
      } else {
        feedback.textContent = `❌ ไม่ถูกต้อง คำตอบคือ ${correct}`;
        feedback.className = 'mt-4 text-center text-lg font-bold text-red-500';
      }
      feedback.classList.remove('hidden');
      
      setTimeout(() => {
        quizState.current++;
        if (quizState.current < 10) {
          showQuizQuestion();
        } else {
          showQuizResult();
        }
      }, 1500);
    }

    function showQuizResult() {
      document.getElementById('quiz-content').classList.add('hidden');
      document.getElementById('quiz-result').classList.remove('hidden');
      document.getElementById('final-score').textContent = quizState.score;
      
      let emoji, message;
      if (quizState.score === 10) {
        emoji = '🏆';
        message = 'ยอดเยี่ยมมาก! คะแนนเต็ม!';
      } else if (quizState.score >= 8) {
        emoji = '🌟';
        message = 'เก่งมาก! เข้าใจเรื่องร้อยละดีมาก!';
      } else if (quizState.score >= 6) {
        emoji = '👍';
        message = 'ดีมาก! ลองทบทวนอีกนิด!';
      } else if (quizState.score >= 4) {
        emoji = '💪';
        message = 'พยายามดี! ลองเรียนรู้เพิ่มเติมนะ!';
      } else {
        emoji = '📚';
        message = 'ลองกลับไปอ่านทบทวนก่อนนะ!';
      }
      
      document.getElementById('result-emoji').textContent = emoji;
      document.getElementById('result-message').textContent = message;
    }

    function resetQuiz() {
      document.getElementById('quiz-start').classList.remove('hidden');
      document.getElementById('quiz-result').classList.add('hidden');
    }

    // Discount Game
    let discountGameState = { score: 0, timer: null, timeLeft: 10 };

    function startDiscountGame() {
      discountGameState.score = 0;
      document.getElementById('game-score').textContent = 0;
      document.getElementById('game-start-btn').textContent = '🔄 เริ่มใหม่';
      newDiscountQuestion();
    }

    function newDiscountQuestion() {
      clearInterval(discountGameState.timer);
      discountGameState.timeLeft = 10;
      
      const originalPrice = [100, 150, 200, 250, 300, 400, 500][Math.floor(Math.random() * 7)];
      const discount = [10, 20, 25, 30, 40, 50][Math.floor(Math.random() * 6)];
      const correctAnswer = originalPrice - (originalPrice * discount / 100);
      
      document.getElementById('game-original-price').textContent = originalPrice;
      document.getElementById('game-discount').textContent = discount;
      document.getElementById('game-timer').textContent = '⏱️ 10';
      document.getElementById('game-feedback').classList.add('hidden');
      
      // Generate options
      const options = [correctAnswer];
      while (options.length < 4) {
        const wrong = correctAnswer + (Math.floor(Math.random() * 6) - 3) * 10;
        if (wrong > 0 && wrong !== correctAnswer && !options.includes(wrong)) {
          options.push(wrong);
        }
      }
      
      const optionsDiv = document.getElementById('game-options');
      optionsDiv.innerHTML = '';
      shuffleArray(options).forEach(opt => {
        const btn = document.createElement('button');
        btn.className = 'bg-orange-100 hover:bg-orange-200 text-orange-700 px-6 py-3 rounded-xl font-bold text-xl transition btn-bounce';
        btn.textContent = opt + ' บาท';
        btn.onclick = () => checkDiscountAnswer(opt, correctAnswer);
        optionsDiv.appendChild(btn);
      });
      
      // Start timer
      discountGameState.timer = setInterval(() => {
        discountGameState.timeLeft--;
        document.getElementById('game-timer').textContent = '⏱️ ' + discountGameState.timeLeft;
        if (discountGameState.timeLeft <= 0) {
          clearInterval(discountGameState.timer);
          showDiscountFeedback(false, correctAnswer);
          setTimeout(newDiscountQuestion, 2000);
        }
      }, 1000);
    }

    function checkDiscountAnswer(selected, correct) {
      clearInterval(discountGameState.timer);
      
      if (selected === correct) {
        discountGameState.score++;
        document.getElementById('game-score').textContent = discountGameState.score;
        showDiscountFeedback(true);
      } else {
        showDiscountFeedback(false, correct);
      }
      
      setTimeout(newDiscountQuestion, 1500);
    }

    function showDiscountFeedback(isCorrect, correctAnswer) {
      const feedback = document.getElementById('game-feedback');
      if (isCorrect) {
        feedback.textContent = '🎉 ถูกต้อง!';
        feedback.className = 'mt-4 text-xl font-bold text-green-500 celebrate';
      } else {
        feedback.textContent = `❌ คำตอบคือ ${correctAnswer} บาท`;
        feedback.className = 'mt-4 text-xl font-bold text-red-500';
      }
      feedback.classList.remove('hidden');
    }

    // Estimate Game
    let estimateScore = 0;

    function startEstimateGame() {
      estimateScore = 0;
      document.getElementById('estimate-score').textContent = 0;
      document.getElementById('estimate-start-btn').textContent = '🔄 เริ่มใหม่';
      newEstimateQuestion();
    }

    function newEstimateQuestion() {
      const actualPercent = Math.floor(Math.random() * 10) * 10 + 10; // 10-100 in steps of 10
      document.getElementById('estimate-bar').style.width = actualPercent + '%';
      document.getElementById('estimate-feedback').classList.add('hidden');
      
      const options = [actualPercent];
      const possibleOptions = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100].filter(x => x !== actualPercent);
      while (options.length < 4) {
        const idx = Math.floor(Math.random() * possibleOptions.length);
        options.push(possibleOptions.splice(idx, 1)[0]);
      }
      
      const optionsDiv = document.getElementById('estimate-options');
      optionsDiv.innerHTML = '';
      shuffleArray(options).forEach(opt => {
        const btn = document.createElement('button');
        btn.className = 'bg-blue-100 hover:bg-blue-200 text-blue-700 px-6 py-3 rounded-xl font-bold text-xl transition btn-bounce';
        btn.textContent = opt + '%';
        btn.onclick = () => checkEstimateAnswer(opt, actualPercent);
        optionsDiv.appendChild(btn);
      });
    }

    function checkEstimateAnswer(selected, correct) {
      const feedback = document.getElementById('estimate-feedback');
      
      if (selected === correct) {
        estimateScore++;
        document.getElementById('estimate-score').textContent = estimateScore;
        feedback.textContent = '🎉 ถูกต้อง!';
        feedback.className = 'mt-4 text-center font-bold text-green-500 celebrate';
      } else {
        feedback.textContent = `❌ คำตอบคือ ${correct}%`;
        feedback.className = 'mt-4 text-center font-bold text-red-500';
      }
      feedback.classList.remove('hidden');
      
      setTimeout(newEstimateQuestion, 1500);
    }

    // Initialize
    initGrid();
    newPracticeProblem();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c0ec68cb3367334',t:'MTc2ODkxNDI0NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
