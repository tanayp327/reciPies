<style>
      @import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
      body {
        font-family: "Poppins", sans-serif;
        background-color: #f6f6ef;
      }
      .main-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
      header {
          background-color: #333;
          color: #fff;
          padding: 20px;
          font-size: 20px;
          display: flex;
          justify-content: center;
          align: center;
          text-align: center;
          width: 1400px;
          height: 75px;
          position: absolute;
          top: 0px;
        }
        header a {
          color: #fff;
          text-decoration: none;
          margin: 0 10px;
          align: center;
          font-size: 16px;
          padding: 10px;
        }
        header a:hover {
          text-decoration: underline;
        }
        header h1 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
        }
        header h2 {
          font-size: 24px;
          margin: 0;
          padding: 10px;
        }
      .login-container {
        background-color: #2E2E2E;
        padding: 20px;
        border-radius: 10px;
        height: 300px;
        width: 400px;
        align: auto;
        text-align: center;
        box-shadow: 0px 0px 10px 0px #ccc;
        color: white;
      }
      form {
        margin-top: 10px;
      }
      input {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        box-sizing: border-box;
        border: none;
        border-bottom: 2px solid #ccc;
        background-color: #f4f4f4;
        color: #444;
        font-family: "Poppins", sans-serif;
        box-shadow: 0px 2px 4px #888888;
      }
      button {
        width: 100%;
        background-color: #0070f3;
        color: #fff;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        font-family: "Poppins", sans-serif;
      }
      button:hover {
        background-color: #3066be;
      }
      .signup-link a {
        color: #0070f3;
        text-align: center;
        display: block;
        font-family: "Poppins", sans-serif;
        text: 19px;
      }
    </style>


<body>

<div class="container">
  <img src="/reciPies/images/OneSkilletChickenwithButteryOrzo.png" alt="OneSkilletChickenwithButteryOrzo" style="width:100%;">
  <div class="bottom-right">One Skillet Chicken with Buttery Orzo</div>
</div>
<div class="container">
  <img src="/reciPies/images/BakedStuffedLobster.png" alt="BakedStuffedLobster" style="width:100%;">
  <div class="bottom-right">Baked Stuffed Lobster</div>
</div>

</body>


<!-- <div class="gallery-container">
  <div class="thumbnails"></div>
  <div class="slides">
    <div><img src="/images/OneSkilletChickenwithButteryOrzo.png"></div>
    <div class="bottom-right">One Skillet Chicken with Buttery Orzo</div>
    <div><img src="/images/BakedStuffedLobster.png"></div>
    <div class="bottom-right">Baked Stuffed Lobster</div>
  </div>
</div>

<style>
.gallery-container {
  position: relative;
  display: flex;
  justify-content: center;
}

.thumbnails {
  position: absolute;
  bottom: 8px;
  display: flex;
  flex-direction: row;
  gap: 6px;
}

.thumbnails div {
  width: 8px;
  height: 8px;
  cursor: pointer;
  background: #aaa;
  border-radius: 100%;
}

.thumbnails div.highlighted {
  background-color: #777;
}

.slides {
  margin: 0 16px;
  display: grid;
  grid-auto-flow: column;
  gap: 1rem;
  width: 540px;
  padding: 0 0.25rem;
  height: 720px;
  overflow-y: auto;
  overscroll-behavior-x: contain;
  scroll-snap-type: x mandatory;
  scrollbar-width: none;
}

.slides > div {
  scroll-snap-align: start;
}

.slides img {
  width: 540px;
  object-fit: contain;
}

.slides::-webkit-scrollbar {
  display: none;
}
</style>
<script>
const slideGallery = document.querySelector('.slides');
const slides = slideGallery.querySelectorAll('div');
const thumbnailContainer = document.querySelector('.thumbnails');
const slideCount = slides.length;
const slideWidth = 540;

const highlightThumbnail = () => {
  thumbnailContainer
    .querySelectorAll('div.highlighted')
    .forEach(el => el.classList.remove('highlighted'));
  const index = Math.floor(slideGallery.scrollLeft / slideWidth);
  thumbnailContainer
    .querySelector(`div[data-id="${index}"]`)
    .classList.add('highlighted');
};

const scrollToElement = el => {
  const index = parseInt(el.dataset.id, 10);
  slideGallery.scrollTo(index * slideWidth, 0);
};

thumbnailContainer.innerHTML += [...slides]
  .map((slide, i) => `<div data-id="${i}"></div>`)
  .join('');

thumbnailContainer.querySelectorAll('div').forEach(el => {
  el.addEventListener('click', () => scrollToElement(el));
});

slideGallery.addEventListener('scroll', e => highlightThumbnail());

highlightThumbnail();
</script> -->
