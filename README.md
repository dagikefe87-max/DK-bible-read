
<!DOCTYPE html>
<html lang="am">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DK Bible Read</title>

<style>
*{box-sizing:border-box}
body{
  margin:0;
  font-family:Arial,sans-serif;
  background:#f4f6f8;
  color:#172033;
}
.splash{
  position:fixed;
  inset:0;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  background:#172033;
  color:white;
  z-index:10;
}
.splash img{
  width:130px;
  height:130px;
  border-radius:50%;
  object-fit:cover;
  border:4px solid white;
  margin-bottom:18px;
}
.splash h1{margin:0;font-size:30px}
.splash p{opacity:.8}

.app{
  max-width:600px;
  margin:auto;
  padding:20px;
}
header{
  display:flex;
  justify-content:space-between;
  align-items:center;
}
header h1{font-size:24px}

button{
  border:0;
  border-radius:12px;
  padding:12px 16px;
  background:#172033;
  color:white;
}

.search{
  width:100%;
  padding:14px;
  border:1px solid #ddd;
  border-radius:12px;
  margin:20px 0;
  font-size:16px;
}

.grid{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:12px;
}

.book{
  background:white;
  border-radius:16px;
  padding:18px;
  box-shadow:0 3px 12px rgba(0,0,0,.08);
}

.book h3{margin:0 0 6px}
.book p{margin:0;color:#667085}

.reader{
  display:none;
  background:white;
  border-radius:16px;
  padding:20px;
  margin-top:20px;
  line-height:1.9;
}

.dark{
  background:#101318;
  color:#f4f4f4;
}
.dark .book,.dark .reader{background:#1b2028}
.dark .search{
  background:#1b2028;
  color:white;
  border-color:#333;
}
</style>
</head>

<body>

<div class="splash">
  <img src="profile.jpg" alt="DK">
  <h1>DK Bible Read</h1>
  <p>የቃሉን ቃል እናንብብ 📖</p>
</div>

<div class="app">

<header>
  <h1>DK Bible Read 📖</h1>
  <button onclick="toggleDark()">☾</button>
</header>

<input
 class="search"
 id="search"
 placeholder="መጽሐፍ ፈልግ..."
 oninput="filterBooks()">

<div class="grid" id="books">

<div class="book">
<h3>ዘፍጥረት</h3>
<p>Genesis</p>
</div>

<div class="book">
<h3>መዝሙረ ዳዊት</h3>
<p>Psalms</p>
</div>

<div class="book">
<h3>ማቴዎስ</h3>
<p>Matthew</p>
</div>

<div class="book">
<h3>ዮሐንስ</h3>
<p>John</p>
</div>

<div class="book">
<h3>ኤፌሶን</h3>
<p>Ephesians</p>
</div>

</div>

</div>

<script>
setTimeout(function(){
  document.querySelector('.splash').style.display='none';
},1800);

function toggleDark(){
  document.body.classList.toggle('dark');
}

function filterBooks(){
  let q=document.getElementById('search').value.toLowerCase();
  document.querySelectorAll('.book').forEach(function(book){
    book.style.display =
      book.innerText.toLowerCase().includes(q) ? 'block' : 'none';
  });
}
</script>

</body>
</html>
