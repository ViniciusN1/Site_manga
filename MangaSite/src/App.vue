<template>
  <div>
    <nav class="navbar">
      <div class="logo">MangaSite</div>
      <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Genres</a></li>
        <li><a href="#">My Library</a></li>
      </ul>
      <div class="auth-buttons">
        <a href="#" class="login">Login</a>
        <button class="signup">Sign Up</button>
      </div>
    </nav>

    <section class="banner">
      <img :src="banner.image" alt="Banner" class="banner-image" />
      <div class="banner-text">
        <h1>{{ banner.title }}</h1>
        <p class="genre">{{ banner.genre }}</p>
        <p class="description">{{ banner.description }}</p>
        <button class="read-btn">Read Now</button>
      </div>
    </section>

    <section class="latest-chapters">
      <h2>Latest Chapters</h2>
      <div class="chapter-list">
        <div v-for="chapter in latestChapters" :key="chapter.title" class="chapter-item">
          <img :src="chapter.image" alt="chapter image" />
          <h3>{{ chapter.title }}</h3>
          <p>Chapter {{ chapter.chapter }}</p>
        </div>
      </div>
    </section>

    <section class="bottom-sections">
      <div class="top-manga">
        <h2>Top Manga</h2>
        <ul>
          <li v-for="manga in topManga" :key="manga.title">
            <img :src="manga.image" alt="manga icon" />
            <span>{{ manga.title }}</span>
          </li>
        </ul>
      </div>

      <div class="browse-genre">
        <h2>Browse by Genre</h2>
        <div class="genre-buttons">
          <button v-for="genre in genres" :key="genre" class="genre-btn">{{ genre }}</button>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const banner = ref({
  image: '/5924372f-b107-41d3-96f8-d164c9be1464.png', // coloque a imagem no public/
  title: 'The Avenger',
  genre: 'Action',
  description: 'A lone swordsman sets out to avenge his clan.'
});

const latestChapters = ref([
  {
    image: '/5924372f-b107-41d3-96f8-d164c9be1464.png', // Substitua por imagens reais
    title: 'Dragon Heart',
    chapter: 50
  },
  {
    image: '/some-image-2.png',
    title: 'Candy & Devil',
    chapter: 30
  },
  {
    image: '/some-image-3.png',
    title: 'Magi’s Apprentice',
    chapter: 24
  },
  {
    image: '/some-image-4.png',
    title: 'Chrono Trigger',
    chapter: 12
  }
]);

const topManga = ref([
  {
    image: '/5924372f-b107-41d3-96f8-d164c9be1464.png',
    title: 'The Avenger'
  },
  {
    image: '/some-image-2.png',
    title: 'Dragon Heart'
  },
  {
    image: '/some-image-3.png',
    title: 'Magi’s Apprentice'
  }
]);

const genres = ref(['Action', 'Comedy', 'Fantasy', 'Romance']);
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #fff;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background: #f9f9f9;
  box-shadow: 0 1px 4px rgb(0 0 0 / 0.1);
}

.logo {
  font-weight: bold;
  font-size: 1.5rem;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-links a {
  text-decoration: none;
  color: #222;
  font-weight: 500;
}

.auth-buttons {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.auth-buttons .login {
  color: #222;
  text-decoration: none;
  font-weight: 500;
}

.auth-buttons .signup {
  background: #222;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  cursor: pointer;
}

.banner {
  margin: 2rem auto;
  max-width: 900px;
  border-radius: 10px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 1px 6px rgb(0 0 0 / 0.1);
}

.banner-image {
  width: 100%;
  object-fit: cover;
  height: 250px;
}

.banner-text {
  padding: 1rem 1.5rem;
}

.banner-text h1 {
  margin: 0;
  font-size: 2rem;
}

.banner-text .genre {
  font-weight: 600;
  margin-top: 0.5rem;
  color: #333;
}

.banner-text .description {
  margin-top: 0.5rem;
  color: #444;
  font-size: 1rem;
}

.read-btn {
  margin-top: 1rem;
  background: #222;
  color: white;
  border: none;
  padding: 0.5rem 1.25rem;
  font-weight: 600;
  border-radius: 5px;
  cursor: pointer;
}

.latest-chapters {
  max-width: 900px;
  margin: 2rem auto;
  padding: 0 1rem;
}

.latest-chapters h2 {
  margin-bottom: 1rem;
}

.chapter-list {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.chapter-item {
  width: 150px;
  border-radius: 10px;
  overflow: hidden;
  background: #f7f7f7;
  box-shadow: 0 0 8px rgb(0 0 0 / 0.05);
  text-align: center;
  padding-bottom: 0.75rem;
}

.chapter-item img {
  width: 100%;
  height: 140px;
  object-fit: cover;
  border-bottom: 1px solid #ddd;
}

.chapter-item h3 {
  margin: 0.5rem 0 0.25rem 0;
  font-size: 1rem;
  font-weight: 600;
}

.chapter-item p {
  margin: 0;
  color: #666;
  font-size: 0.9rem;
}

.bottom-sections {
  max-width: 900px;
  margin: 2rem auto;
  display: flex;
  justify-content: space-between;
  padding: 0 1rem;
}

.top-manga ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.top-manga li {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1rem;
  font-weight: 600;
}

.top-manga img {
  width: 40px;
  height: 40px;
  border-radius: 8px;
  object-fit: cover;
}

.browse-genre {
  max-width: 400px;
}

.genre-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  margin-top: 0.5rem;
}

.genre-btn {
  background: #eee;
  border: none;
  border-radius: 8px;
  padding: 0.5rem 1.2rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.3s ease;
}

.genre-btn:hover {
  background: #ccc;
}
</style>
