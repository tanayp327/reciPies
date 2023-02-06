<style>
    body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
    }
    body {
    font-family: "Open Sans", sans-serif;
    background-color: #f6f6ef;
    }
    .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    margin: 10px auto;
    position: absolute;
    top: 20px;
    left: 50%;
    transform: translate(-50%, 0);
    }
    .container {
    position: relative;
    text-align: center;
    color: black;
    }
    .bottom-right {
    position: absolute;
    bottom: 8px;
    right: 16px;
    background-color: #ffffff;
    }
</style>


<body>

<div class="container">
  <img src="/images/OneSkilletChickenwithButteryOrzo.png" alt="Snow" style="width:100%;">
  <div class="bottom-right">One Skillet Chicken with Buttery Orzo</div>
</div>
<div class="container">
  <img src="/images/BakedStuffedLobster.png" alt="Snow" style="width:100%;">
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