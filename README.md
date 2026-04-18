# Paypal.login
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giao diện Hệ thống</title>
    <style>
        * { box-sizing: border-box; }
        body { font-family: 'Segoe UI', Arial, sans-serif; margin: 0; background-color: #f5f7fa; color: #333; }

        /* --- TRANG ĐĂNG NHẬP --- */
        #login-page {
            display: flex; flex-direction: column; align-items: center; padding: 50px 20px;
            background: white; min-height: 100vh;
        }
        .logo { font-size: 35px; font-weight: bold; font-style: italic; color: #003087; margin-bottom: 40px; }
        .login-container { width: 100%; max-width: 350px; text-align: center; }
        .user-info { margin-bottom: 20px; font-size: 15px; }
        input[type="password"] {
            width: 100%; padding: 15px; border: 1px solid #ccc; border-radius: 5px;
            margin-bottom: 15px; font-size: 16px;
        }
        .btn-blue {
            width: 100%; background: #003087; color: white; border: none;
            padding: 15px; border-radius: 30px; font-weight: bold; cursor: pointer; font-size: 16px;
        }
        .btn-outline {
            width: 100%; background: transparent; border: 1px solid #333;
            padding: 15px; border-radius: 30px; font-weight: bold; cursor: pointer; margin-top: 20px;
        }

        /* --- TRANG DASHBOARD (Ẩn lúc đầu) --- */
        #dashboard-page { display: none; } /* Mặc định ẩn */
        .wrapper { display: flex; min-height: 100vh; }
        
        .sidebar { width: 260px; background: #002169; color: white; padding: 25px; }
        .sidebar div { padding: 15px 0; border-bottom: 1px solid rgba(255,255,255,0.1); cursor: pointer; }
        
        .content { flex: 1; padding: 30px; }
        .card { background: white; border-radius: 15px; padding: 25px; margin-bottom: 20px; box-shadow: 0 4px 12px rgba(0,0,0,0.05); }
        .balance-num { font-size: 40px; font-weight: bold; color: #001c64; margin: 10px 0; }
        
        /* Profile Header */
        .profile-bg { background: #003087; height: 80px; border-radius: 15px 15px 0 0; margin: -25px -25px 40px -25px; position: relative; }
        .avatar { width: 70px; height: 70px; border-radius: 50%; border: 3px solid white; background: #eee; position: absolute; bottom: -35px; left: 20px; }
    </style>
</head>
<body>

    <div id="login-page">
        <div class="logo">PayPal</div>
        <div class="login-container">
            <div class="user-info">
                Hugoallah0@gmail.com <a href="#" style="color:#0070ba; text-decoration:none; font-weight:bold;">Thay đổi</a>
            </div>
            <input type="password" id="pass" placeholder="Nhập mật khẩu bất kỳ">
            <button class="btn-blue" onclick="checkLogin()">Đăng nhập</button>
            <div style="margin: 20px 0; color: #666;">hoặc</div>
            <button class="btn-outline">Đăng ký</button>
        </div>
    </div>

    <div id="dashboard-page">
        <div class="wrapper">
            <div class="sidebar">
                <h3 style="font-size:12px; opacity:0.7;">ĐĂNG XUẤT</h3>
                <div>Trang chủ</div>
                <div>Gửi và Yêu cầu</div>
                <div>Ví</div>
                <div>Hoạt động</div>
            </div>
            <div class="content">
                <div class="card">
                    <div class="profile-bg"><div class="avatar"></div></div>
                    <h2 style="margin:0;">Nour Allah</h2>
                    <p style="color:#0070ba; font-weight:bold; font-size:14px;">Hoàn tất hồ sơ cá nhân của bạn</p>
                </div>

                <div class="card">
                    <div style="font-weight:bold;">Số dư PayPal</div>
                    <div class="balance-num">$4,290.00</div>
                    <div style="color:#666; margin-bottom:15px;">Có sẵn</div>
                    <button class="btn-blue">Chuyển tiền</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Hàm xử lý logic chuyển trang
        function checkLogin() {
            var pass = document.getElementById('pass').value;
            if (pass === "") {
                alert("Vui lòng nhập mật khẩu!");
            } else {
                // Ẩn trang đăng nhập
                document.getElementById('login-page').style.display = 'none';
                // Hiện trang Dashboard
                document.getElementById('dashboard-page').style.display = 'block';
            }
        }
    </script>

</body>
</html>
