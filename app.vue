<template>
  <div class="min-h-screen bg-gray-100">
    <!-- Header -->
    <header class="bg-white shadow">
      <nav class="container mx-auto px-4 py-4 flex justify-between items-center">
        <div class="text-2xl font-bold text-blue-600">GameTower</div>
        <div class="space-x-4">
          <UButton color="gray" variant="ghost">登入</UButton>
          <UButton color="blue">註冊</UButton>
        </div>
      </nav>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-4 py-8">
      <!-- Hero Section -->
      <section class="mb-12 text-center bg-gradient-to-r from-blue-500 to-purple-600 text-white py-16 rounded-lg">
        <h1 class="text-5xl font-bold mb-4">歡迎來到 GameTower</h1>
        <p class="text-xl mb-6">探索精彩的遊戲世界，盡在 GameTower</p>
        <UButton color="white" variant="solid" size="lg">立即開始</UButton>
      </section>

      <!-- Featured Games -->
      <section class="mb-12">
        <h2 class="text-3xl font-bold mb-6 text-center">熱門遊戲</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="game in featuredGames" :key="game.id" class="bg-white rounded-lg shadow-md overflow-hidden transition-transform duration-300 hover:scale-105">
            <img :src="game.image" :alt="game.name" class="w-full h-48 object-cover">
            <div class="p-4">
              <h3 class="font-bold text-lg mb-2">{{ game.name }}</h3>
              <p class="text-sm text-gray-600 mb-4">{{ game.description }}</p>
              <UButton color="blue" variant="outline" class="w-full">了解更多</UButton>
            </div>
          </div>
        </div>
      </section>

      <!-- News Section -->
      <section>
        <h2 class="text-3xl font-bold mb-6 text-center">最新消息</h2>
        <ul class="space-y-4">
          <li v-for="news in latestNews" :key="news.id" class="bg-white rounded-lg shadow-md p-6 transition-colors duration-300 hover:bg-gray-50">
            <h3 class="font-bold text-xl mb-2">{{ news.title }}</h3>
            <p class="text-gray-600 mb-4">{{ news.content }}</p>
            <UButton color="gray" variant="ghost">閱讀更多</UButton>
          </li>
        </ul>
      </section>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-8 mt-12">
      <div class="container mx-auto px-4 text-center">
        <p>&copy; 2024 GameTower. All rights reserved.</p>
        <div class="mt-4">
          <UButton color="white" variant="ghost" class="mx-2">關於我們</UButton>
          <UButton color="white" variant="ghost" class="mx-2">聯繫我們</UButton>
          <UButton color="white" variant="ghost" class="mx-2">隱私政策</UButton>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
const featuredGames = [
  { id: 1, name: "星際探險", description: "探索浩瀚宇宙，建立自己的星際帝國", image: "https://images.unsplash.com/photo-1614732414444-096e5f1122d5?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" },
  { id: 2, name: "魔法世界", description: "成為強大的魔法師，拯救魔法王國", image: "https://images.unsplash.com/photo-1578632767115-351597cf2477?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" },
  { id: 3, name: "賽車狂飆", description: "體驗極速快感，成為賽道之王", image: "https://images.unsplash.com/photo-1511994298241-608e28f14fde?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" },
];

const latestNews = [
  { id: 1, title: "全新遊戲「龍之傳說」即將上線", content: "備受期待的MMORPG「龍之傳說」將於下月正式推出，玩家可提前註冊獲得獨家獎勵。" },
  { id: 2, title: "電競賽事「GameTower盃」報名開始", content: "年度最大電競賽事「GameTower盃」現已開放報名，優勝者將獲得豐厚獎金和全球知名度。" },
  { id: 3, title: "手機遊戲《口袋妖怪GO》更新", content: "《口袋妖怪GO》推出重大更新，新增100多種新的口袋妖怪和全新的對戰系統。" },
];
</script>