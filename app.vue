<template>
  <div class="min-h-screen font-sans bg-gray-900 text-white">
    
    <!-- 🛑 1. ป้ายเตือนเพื่อการศึกษา (CRITICAL WARNING BANNER) 🛑 -->
    <div class="bg-red-800 text-white p-4 text-center font-black sticky top-0 z-50 shadow-2xl animate-pulse">
      🚨 เว็บไซต์นี้เป็น **เว็บไซต์จำลองเพื่อการศึกษาด้าน Cybersecurity เท่านั้น** 🚨
      <br class="sm:hidden">
      ห้ามกรอกข้อมูลส่วนตัวใดๆ และทุกฟังก์ชันเป็นของปลอมเพื่อใช้ในการวิเคราะห์จุดเสี่ยง
    </div>

    <!-- ---------------------------------------------------- -->
    <!-- VIEW 1: หน้าหลักของเว็บเสี่ยง (currentView === 'mainRiskSite') -->
    <!-- ---------------------------------------------------- -->
    <template v-if="currentView === 'mainRiskSite'">
      
      <!-- Header ที่ดูเร่งรีบและมีปุ่มปลอม -->
      <header class="bg-gray-800 p-4 border-b-4 border-yellow-500 shadow-xl flex flex-col md:flex-row justify-between items-center space-y-3 md:space-y-0">
        <h1 class="text-3xl font-black text-red-500 animate-bounce cursor-default">
          🎥 ดูหนังฟรี HD | รวยด้วยคลิกเดียว! 💰
        </h1>
        <div class="space-x-3 flex">
          <!-- ปุ่มที่เปลี่ยนไปหน้าโดนหลอก -->
          <button @click="triggerScam" class="bg-yellow-400 hover:bg-yellow-500 text-gray-900 font-bold py-2 px-4 rounded-full shadow-2xl transform hover:scale-105 transition duration-150 border-2 border-black">
            🔑 เข้าสู่ระบบ
          </button>
          <button @click="triggerScam" class="bg-red-600 hover:bg-red-700 text-white font-bold py-2 px-4 rounded-full shadow-2xl animate-wiggle border-2 border-yellow-400">
            🎁 ดูหนังฟรีตลอดชีพ!
          </button>
        </div>
      </header>

      <!-- 2. เนื้อหาหลักที่เต็มไปด้วย Promotion หลอกล่อ + หนังเถื่อน -->
      <main class="max-w-7xl mx-auto p-4 md:p-8">

        <!-- Banner โฆษณาปลอม 1 (ด้านบน) -->
        <a href="#" @click.prevent="triggerScam" class="block bg-green-500 text-white text-center text-xl p-3 mb-8 rounded-lg shadow-2xl font-black border-4 border-red-500 hover:opacity-80 transition duration-200">
          ⚠️ ชนะรางวัล iPhone 16 Pro Max! คลิกเพื่อรับเลย! 🏆
        </a>

        <!-- Section โปรโมชันเวอร์เกินจริง (จำลองเว็บพนัน/หาเงิน) -->
        <section class="bg-gray-800 p-6 rounded-xl shadow-2xl mb-8 border-l-8 border-red-500">
          <h2 class="text-4xl font-extrabold mb-3 text-yellow-400">
            💸 รับเงินก้อนใหญ่! ไม่ต้องฝาก ไม่ต้องแชร์! 💸
          </h2>
          <p class="text-xl text-gray-300">
            แค่กรอกอีเมลก็รวยทันที! ระบบ AI คำนวณผลตอบแทนให้คุณมากกว่า **1000%**
          </p>
          <button @click="triggerScam" class="mt-6 w-full bg-red-600 hover:bg-red-700 text-white text-2xl font-black py-4 rounded-lg shadow-2xl animate-pulse">
            คลิกที่นี่เพื่อรับโบนัสฟรี!
          </button>
        </section>
        
        <!-- Section จำลองรายการหนังเถื่อน (Pirate Site Look) -->
        <section class="mb-8">
          <h3 class="text-3xl font-bold mb-4 border-b-2 border-red-500 pb-2">
            🎬 หนังมาใหม่ (อัปเดตทุก 10 นาที!)
          </h3>
          <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-5 gap-4">
            <!-- Mock Movie Thumbnail 1 -->
            <div class="bg-gray-700 rounded-lg overflow-hidden shadow-xl transform hover:scale-105 transition duration-300 cursor-pointer" @click="triggerScam">
              <!-- Placeholder Image URL for a Movie -->
              <img 
                src="https://placehold.co/400x600/3B82F6/FFFFFF?text=MOVIE+1" 
                alt="ภาพยนตร์ปลอม 1" 
                class="w-full h-auto object-cover"
              />
              <div class="p-2 text-center">
                <p class="text-sm font-bold text-yellow-400">🔥 ซูเปอร์ฮีโร่หลุดโลก (HD)</p>
                <span class="text-xs text-red-400">ดูฟรี!</span>
              </div>
            </div>
            <!-- Mock Movie Thumbnail 2 -->
            <div class="bg-gray-700 rounded-lg overflow-hidden shadow-xl transform hover:scale-105 transition duration-300 cursor-pointer" @click="triggerScam">
              <img 
                src="https://placehold.co/400x600/10B981/FFFFFF?text=NEW+SERIES" 
                alt="ซีรีส์ปลอม" 
                class="w-full h-auto object-cover"
              />
              <div class="p-2 text-center">
                <p class="text-sm font-bold text-yellow-400">💥 สงครามดวงดาว 99 (ภาคจบ)</p>
                <span class="text-xs text-green-400">พากย์ไทย</span>
              </div>
            </div>
            <!-- Mock Movie Thumbnail 3 -->
            <div class="bg-gray-700 rounded-lg overflow-hidden shadow-xl transform hover:scale-105 transition duration-300 cursor-pointer" @click="triggerScam">
              <img 
                src="https://placehold.co/400x600/F59E0B/000000?text=ACTION" 
                alt="ภาพยนตร์ปลอม 3" 
                class="w-full h-auto object-cover"
              />
              <div class="p-2 text-center">
                <p class="text-sm font-bold text-yellow-400">🚀 โคตรคนระห่ำเมือง (ชัด 4K)</p>
                <span class="text-xs text-red-400">เพิ่งเข้า!</span>
              </div>
            </div>
            <!-- Mock Movie Thumbnail 4 -->
            <div class="bg-gray-700 rounded-lg overflow-hidden shadow-xl transform hover:scale-105 transition duration-300 cursor-pointer" @click="triggerScam">
              <img 
                src="https://placehold.co/400x600/9333EA/FFFFFF?text=COMEDY" 
                alt="ภาพยนตร์ปลอม 4" 
                class="w-full h-auto object-cover"
              />
              <div class="p-2 text-center">
                <p class="text-sm font-bold text-yellow-400">😂 ตลกบริโภค 2025</p>
                <span class="text-xs text-green-400">ซับไทย</span>
              </div>
            </div>
            <!-- Mock Movie Thumbnail 5 -->
            <div class="bg-gray-700 rounded-lg overflow-hidden shadow-xl transform hover:scale-105 transition duration-300 cursor-pointer" @click="triggerScam">
              <img 
                src="https://placehold.co/400x600/EF4444/FFFFFF?text=HORROR" 
                alt="ภาพยนตร์ปลอม 5" 
                class="w-full h-auto object-cover"
              />
              <div class="p-2 text-center">
                <p class="text-sm font-bold text-yellow-400">👻 ผีตามติด (ดูฟรี 100%)</p>
                <span class="text-xs text-red-400">คลิกเดียวจบ</span>
              </div>
            </div>
          </div>
        </section>

        <!-- Banner โฆษณาปลอม 2 (ด้านล่าง) -->
        <a href="#" @click.prevent="triggerScam" class="block bg-yellow-400 text-gray-900 text-center text-2xl p-4 mt-8 mb-4 rounded-lg shadow-2xl font-black border-4 border-red-600 animate-pulse hover:opacity-90 transition duration-200">
          🚫 โทรศัพท์ของคุณกำลังถูกสอดแนม! คลิกเพื่อแก้ไขทันที! 🛡️
        </a>
        
      </main>

      <!-- Footer ที่ดูไม่เป็นทางการ -->
      <footer class="text-center p-4 bg-gray-800 border-t-2 border-red-500 mt-12">
          <p class="text-sm text-gray-400">© {{ currentYear }} **[เว็บปลอม].** ข้อมูลทั้งหมดเป็นของปลอมเพื่อการศึกษา</p>
      </footer>

      <!-- 5. Pop-up แจ้งเตือนไวรัสปลอม (Fake Malware Modal) -->
      <Transition name="fade">
        <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-[100] p-4">
          <div class="bg-white p-6 rounded-xl shadow-2xl border-4 border-red-600 max-w-sm w-full text-center transform scale-100 animate-shake">
            <h3 class="text-2xl font-black text-red-600 mb-4">
              🚨 ข้อมูลรั่วไหล! ต้องรีบแก้! 🚨
            </h3>
            <p class="text-gray-700 mb-4 font-bold">
              ตรวจพบไวรัสที่ขโมยรหัสผ่าน! กด "ติดตั้งโปรแกรม" เพื่อปกป้องตัวเองเดี๋ยวนี้!
            </p>
            <div class="flex flex-col space-y-3">
              <button @click="triggerScam" class="bg-red-600 hover:bg-red-700 text-white font-black py-3 px-6 rounded-lg shadow-md">
                ติดตั้งโปรแกรมทันที!
              </button>
              <button @click="showModal = false" class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-3 px-6 rounded-lg shadow-md">
                ปิด
              </button>
            </div>
          </div>
        </div>
      </Transition>

      <!-- 6. Pop-up รางวัลปลอม (Fake Prize Modal - NEW) -->
      <Transition name="fade">
        <div v-if="showPrizeModal" class="fixed inset-0 bg-black bg-opacity-70 flex items-center justify-center z-[110] p-4">
          <div class="bg-yellow-100 p-8 rounded-2xl shadow-2xl border-4 border-green-600 max-w-md w-full text-center transform scale-100 animate-pulse-slow">
            <h3 class="text-4xl font-black text-green-700 mb-4">
              🎉 ยินดีด้วย! คุณถูกรางวัลใหญ่! 🎉
            </h3>
            <p class="text-gray-900 mb-4 font-extrabold text-xl">
              คุณคือผู้โชคดีคนที่ **1,000,000!**
              ได้รับเครดิตฟรี **100,000 บาท**!
            </p>
            <p class="text-sm text-red-500 mb-6 font-bold">
                **ต้องยืนยันสิทธิ์ภายใน 60 วินาทีนี้เท่านั้น!**
            </p>
            <div class="flex flex-col space-y-3">
              <button @click="triggerScamAndClosePrize" class="bg-green-600 hover:bg-green-700 text-white font-black py-4 px-6 rounded-lg shadow-xl text-2xl animate-bounce-slow">
                กดรับรางวัลเดี๋ยวนี้!
              </button>
              <button @click="showPrizeModal = false" class="text-sm text-gray-500 hover:text-gray-800">
                ไม่ต้องการเงินฟรี
              </button>
            </div>
          </div>
        </div>
      </Transition>

    </template>
    
    <!-- ---------------------------------------------------- -->
    <!-- VIEW 2: หน้าโดนหลอก (currentView === 'scamAlert') -->
    <!-- ---------------------------------------------------- -->
    <template v-else>
      <div class="flex flex-col items-center justify-center min-h-screen p-8 text-center bg-red-900">
        <h2 class="text-6xl font-black text-yellow-400 mb-6 animate-pulse">
          🚫 คุณโดนหลอกแล้ว! 🚫
        </h2>
        <p class="text-3xl text-white mb-8 max-w-2xl">
          การกดปุ่มที่ไม่น่าเชื่อถือและเร่งรีบ มักจะนำคุณมาสู่สถานการณ์แบบนี้ในโลกแห่งความเป็นจริง!
        </p>
        
        <div class="bg-gray-800 p-6 rounded-xl shadow-2xl border-4 border-yellow-500 max-w-xl w-full">
            <h3 class="text-2xl font-bold text-red-400 mb-4">
                💡 บทเรียนด้านความปลอดภัยไซเบอร์
            </h3>
            <ul class="text-left space-y-3 text-gray-300 list-disc list-inside">
                <li>**ความเร่งรีบ:** การถูกเร่งให้ตัดสินใจ (เช่น "ภายใน 60 วินาที") คือสัญญาณอันตรายที่ชัดเจน</li>
                <li>**คำมั่นสัญญาเวอร์เกินจริง:** ไม่มีใครแจกเงินฟรี 100,000 บาท เพียงแค่คลิก Pop-up</li>
                <li>**การดาวน์โหลดที่ไม่ตั้งใจ:** การคลิกปุ่ม "รับรางวัล" หรือ "ติดตั้งโปรแกรม" มักจะส่งผลเสียต่ออุปกรณ์</li>
            </ul>
        </div>

        <button @click="currentView = 'mainRiskSite'" class="mt-10 bg-green-500 hover:bg-green-600 text-white text-xl font-bold py-4 px-8 rounded-full shadow-lg transform hover:scale-105 transition duration-300">
          ⬅️ กลับไปวิเคราะห์เว็บไซต์หลักอีกครั้ง
        </button>
      </div>
    </template>
    
    <!-- NuxtPage สำหรับแสดงเนื้อหาจาก pages/ (ถ้ามี) -->
    <NuxtPage /> 
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// ------------------------------------
// State Management และ Logic
// ------------------------------------

// 1. สถานะสำหรับ Footer
const currentYear = ref(new Date().getFullYear());

// 2. สถานะสำหรับ Modal ไวรัส
const showModal = ref(false); 

// 3. สถานะสำหรับ Modal รางวัลปลอม (NEW)
const showPrizeModal = ref(false); 

// 4. สถานะสำหรับเปลี่ยน View (Simulated Routing)
const currentView = ref('mainRiskSite'); 

// ฟังก์ชันสำหรับจำลองการ "โดนหลอก"
const triggerScam = () => {
    // ปิด Modal ทั้งหมดก่อนเปลี่ยนหน้า
    showModal.value = false;
    showPrizeModal.value = false;
    // เปลี่ยนไปหน้าแจ้งเตือนทันที
    currentView.value = 'scamAlert';
};

// ฟังก์ชันสำหรับ Modal รางวัลที่นำไปสู่การโดนหลอก
const triggerScamAndClosePrize = () => {
    showPrizeModal.value = false;
    triggerScam();
};


onMounted(() => {
    // 1. Initial Pop-up ไวรัส (แสดงครั้งเดียวหลังจาก 2 วินาที)
    setTimeout(() => {
        if (currentView.value === 'mainRiskSite') {
            showModal.value = true;
        }
    }, 2000);

    // 2. Periodic Pop-up รางวัล (แสดงซ้ำทุก 20 วินาที)
    const prizeInterval = setInterval(() => {
        // ตรวจสอบว่าอยู่ในหน้าหลัก และไม่มี Modal อื่นแสดงอยู่
        if (currentView.value === 'mainRiskSite' && !showModal.value) {
            showPrizeModal.value = true;
        }
    }, 20000); // 20 วินาที

    // 3. Cleanup เมื่อ Component ถูกทำลาย
    onUnmounted(() => {
        clearInterval(prizeInterval);
    });
});

// กำหนด Meta Data ปลอม
useHead({
  title: 'เว็บอันตราย | ดูหนังฟรี | รวยไวใน 10 นาที!',
  meta: [
    { name: 'description', content: 'เว็บไซต์จำลองเพื่อการศึกษาด้านความปลอดภัยไซเบอร์เท่านั้น' }
  ]
})
</script>

<style>
/* ------------------------------------ */
/* Tailwind Custom Keyframes */
/* ------------------------------------ */

/* ทำให้ปุ่มสั่น/กระดุกกระดิก (Header Buttons) */
@keyframes wiggle {
  0%, 100% { transform: translateX(0); }
  25% { transform: translateX(-5px) rotate(-1deg); }
  50% { transform: translateX(5px) rotate(1deg); }
  75% { transform: translateX(-2px) rotate(-.5deg); }
}

.animate-wiggle {
  animation: wiggle 0.5s infinite;
}

/* ทำให้ Pop-up ไวรัสสั่น */
@keyframes shake {
  0%, 100% { transform: translateX(0); }
  10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
  20%, 40%, 60%, 80% { transform: translateX(5px); }
}

.animate-shake {
  animation: shake 0.5s ease-in-out infinite;
}

/* Animation สำหรับ Pop-up รางวัล (NEW: Pulse ช้าลง) */
@keyframes pulse-slow {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.8; }
}

.animate-pulse-slow {
  animation: pulse-slow 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

/* Animation สำหรับปุ่มรางวัล (NEW: Bounce ช้าลง) */
@keyframes bounce-slow {
  0%, 100% { transform: translateY(-5%); }
  50% { transform: translateY(0); }
}

.animate-bounce-slow {
  animation: bounce-slow 1s infinite;
}

/* Transition สำหรับ Pop-up */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

/* Body Styling (เพื่อให้พื้นหลังดำถูกต้อง) */
body {
  background-color: #111827; /* gray-900 */
}
</style>


ไฟล์ `app.vue` ใหม่นี้มีการจัดการ Pop-up สองประเภท:

1.  **Pop-up ไวรัส (Malware/Fear Tactic):** แสดงครั้งแรกหลังจากโหลด 2 วินาที (ควบคุมโดย `showModal`)
2.  **Pop-up รางวัล (Greed/Phishing Tactic):** แสดงขึ้นมาซ้ำๆ ทุก 20 วินาที (ควบคุมโดย `showPrizeModal` และ `setInterval`)

เมื่อผู้เรียนคลิกปุ่มที่เร่งเร้าทั้งใน Pop-up และบนหน้าเว็บหลัก จะถูกนำไปสู่หน้า **"คุณโดนหลอกแล้ว!"** ซึ่งเป็นบทสรุปของบทเรียนครับ