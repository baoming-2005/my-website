<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>🍡 CineTicket - Đặt Vé Xem Phim Phô Mai Que 🍡</title>
  <meta name="description" content="Đặt vé xem phim cute, thêm combo bắp nước cực chill tại CineTicket Việt Nam.">
  
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: #fff0f5;
      color: #444;
      padding: 20px;
    }

    header {
      text-align: center;
      background: linear-gradient(135deg, #ffccff, #ffe6e6);
      color: #ff6699;
      padding: 30px 20px;
      border-radius: 15px;
      margin-bottom: 30px;
      box-shadow: 0 5px 15px rgba(255,192,203,0.5);
    }

    main {
      max-width: 1000px;
      margin: auto;
      background: #fff;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 5px 20px rgba(255,182,193,0.4);
    }

    section {
      margin-bottom: 40px;
    }

    h1, h2 {
      color: #ff6699;
      margin-bottom: 20px;
    }

    p {
      margin-bottom: 20px;
      line-height: 1.6;
    }

    .movies-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
    }

    .movie-item {
      background: #fff8fb;
      border-radius: 12px;
      padding: 10px;
      text-align: center;
      box-shadow: 0 2px 6px rgba(255,182,193,0.4);
      cursor: pointer;
      transition: transform 0.2s ease, background 0.3s;
    }

    .movie-item:hover {
      transform: scale(1.05);
      background: #ffe0ec;
    }

    .movie-item.selected {
      background: #ff99cc;
      color: white;
      font-weight: bold;
      box-shadow: 0 0 10px rgba(255, 105, 180, 0.6);
    }

    form label {
      font-weight: bold;
      display: block;
      margin-top: 15px;
      color: #d6336c;
    }

    form select, form input {
      width: 100%;
      padding: 10px;
      margin-top: 8px;
      border: 1px solid #ffcce0;
      border-radius: 8px;
      background: #fff9fb;
    }

    button {
      background: #ff66a3;
      color: white;
      padding: 12px 20px;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      margin-top: 20px;
      width: 100%;
      transition: background 0.3s ease;
    }

    button:hover {
      background: #ff3385;
    }

    #priceDisplay {
      margin-top: 20px;
      font-size: 18px;
      color: #e91e63;
      font-weight: bold;
      text-align: center;
    }

    footer {
      text-align: center;
      font-size: 14px;
      color: #999;
      margin-top: 50px;
    }
  </style>
</head>

<body>

<header>
  <h1>🍡 CineTicket Tứ Đại Anh Hài Việt Nam 🍡</h1>
  <p>Đặt vé phim feel - Thêm nước, bắp chill chill 🍿✨</p>
</header>

<main>

  <section id="chon-phim">
    <h2>🎬 Chọn Phim Hot Nhất</h2>
    <div class="movies-grid" id="moviesGrid">
      <div class="movie-item" data-movie="Mai">Mai</div>
      <div class="movie-item" data-movie="Lật Mặt 7: Một Điều Ước">Lật Mặt 7: Một Điều Ước</div>
      <div class="movie-item" data-movie="Chị Mười Ba 3">Chị Mười Ba 3</div>
      <div class="movie-item" data-movie="Trạng Tí 2">Trạng Tí 2</div>
      <div class="movie-item" data-movie="Người Vợ Cuối Cùng">Người Vợ Cuối Cùng</div>
      <div class="movie-item" data-movie="Đảo Độc Đắc">Đảo Độc Đắc</div>
      <div class="movie-item" data-movie="Thanh Sói">Thanh Sói</div>
      <div class="movie-item" data-movie="Bóng Đè 2">Bóng Đè 2</div>
      <div class="movie-item" data-movie="Em và Trịnh 2">Em và Trịnh 2</div>
      <div class="movie-item" data-movie="Tết Ở Làng Địa Ngục">Tết Ở Làng Địa Ngục</div>
    </div>
    <p id="selectedMovie">Bạn chưa chọn phim</p>
  </section>

  <section id="chon-rap-lich">
    <h2>🏢 Chọn Rạp Và Lịch Chiếu</h2>
    <form id="bookingForm">
      <label for="theater">Rạp Chiếu:</label>
      <select id="theater" name="theater" required>
        <option value="">-- Chọn rạp --</option>
        <option value="CGV Vạn Hạnh Mall">CGV Vạn Hạnh Mall</option>
        <option value="Lotte Cinema Gò Vấp">Lotte Cinema Gò Vấp</option>
        <option value="Galaxy Kinh Dương Vương">Galaxy Kinh Dương Vương</option>
        <option value="BHD Bitexco">BHD Bitexco</option>
      </select>

      <label for="showtime">Suất Chiếu:</label>
      <select id="showtime" name="showtime" required>
        <option value="">-- Chọn giờ --</option>
        <option value="10h00">10:00</option>
        <option value="13h00">13:00</option>
        <option value="16h00">16:00</option>
        <option value="19h00">19:00</option>
        <option value="21h30">21:30</option>
      </select>

  </section>

  <section id="dat-ve">
    <h2>🎟️ Đặt Vé Và Combo</h2>
      <label for="tickets">Số Vé:</label>
      <input type="number" id="tickets" name="tickets" min="1" max="10" value="1" required>

      <label for="combo">Combo Nước + Bắp:</label>
      <select id="combo" name="combo">
        <option value="0">Không thêm</option>
        <option value="45000">Combo Nhỏ (45k)</option>
        <option value="70000">Combo Vừa (70k)</option>
        <option value="95000">Combo Lớn (95k)</option>
      </select>

      <div id="priceDisplay">💖 Tổng Tiền: 0 VNĐ</div>

      <button type="submit">Đặt Vé Ngay</button>
    </form>
  </section>

</main>

<footer>
  <p>&copy; 2025 CineTicket Việt Nam 🍡 Phô Mai Que Team</p>
</footer>

<script>
  const ticketPrice = 90000; // 1 vé phim 90k
  const ticketsInput = document.getElementById('tickets');
  const comboSelect = document.getElementById('combo');
  const priceDisplay = document.getElementById('priceDisplay');
  const form = document.getElementById('bookingForm');
  const selectedMovieDisplay = document.getElementById('selectedMovie');
  
  // Phần chọn phim
  const movies = document.querySelectorAll('.movie-item');
  movies.forEach(movie => {
    movie.addEventListener('click', function() {
      movies.forEach(m => m.classList.remove('selected')); // Xóa chọn tất cả trước
      this.classList.add('selected'); // Chỉ chọn cái vừa bấm
      const movieName = this.getAttribute('data-movie');
      selectedMovieDisplay.textContent = `Bạn đang chọn: ${movieName}`;
    });
  });

  // Cập nhật giá vé
  function updatePrice() {
    const tickets = parseInt(ticketsInput.value) || 0;
    const combo = parseInt(comboSelect.value) || 0;
    const total = (tickets * ticketPrice) + combo;
    priceDisplay.textContent = `💖 Tổng Tiền: ${total.toLocaleString('vi-VN')} VNĐ`;
  }

  ticketsInput.addEventListener('input', updatePrice);
  comboSelect.addEventListener('change', updatePrice);

  form.addEventListener('submit', function(e) {
    e.preventDefault();
    alert("🍿 Vé đã được đặt thành công! Chúc bạn xem phim vui vẻ nhaaa!");
  });

  updatePrice();
</script>

</body>
</html>
