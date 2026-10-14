# tvpl-cron

Đồng hồ (cron) miễn phí cho bot theo dõi **Thư Viện Pháp Luật** trên Vercel.

Vercel Hobby chỉ cho cron 1 lần/ngày, mà serverless không tự chạy vòng lặp. Repo này
dùng **GitHub Actions** gọi endpoint `https://discord-tvpl-bot.vercel.app/api/check`
đều đặn để bot tự kiểm tra văn bản mới.

- `poll.yml`: cứ 5 phút khởi động 1 job, bên trong tự gọi lại mỗi 60 giây (~1 phút/lần).
- `keepalive.yml`: commit nhỏ mỗi tháng để GitHub không tắt workflow theo lịch.

URL đầy đủ (kèm token) nằm trong **GitHub Secret** `CHECK_URL`, không lộ ra ngoài.

Repo chỉ chứa 2 workflow + file này; không chứa mã bot hay bí mật nào.
