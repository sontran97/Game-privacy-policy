# Privacy Policy Template (GitHub Pages)

Repo mẫu để tạo trang **Privacy Policy URL** cho game/app, dùng khi nộp App Store. Trang có 2 ngôn ngữ (English / Tiếng Việt), hỗ trợ dark mode, chạy tốt trên điện thoại.

Mỗi lần cần dùng: **chỉ cần sửa `index.html` là xong**, không cần build hay cài gì.

## Cấu trúc

```
.
├── index.html                          # Trang chính (URL gốc của repo)
├── games/
│   └── example-game/index.html         # Ví dụ cho trường hợp nhiều game trong 1 repo
├── template/
│   └── privacy-policy-template.html    # Bản gốc để copy khi cần trang mới
└── .nojekyll                           # Bắt GitHub Pages phục vụ file y nguyên
```

## Cách dùng nhanh (1 game)

1. Tạo repo mới trên GitHub (để **Public**), ví dụ `mygame-privacy`.
2. Upload toàn bộ file trong thư mục này lên repo (kéo thả trên web GitHub là được).
3. Mở `index.html`, tìm khối `CONFIG` ở gần cuối file và sửa:

```js
var CONFIG = {
  game: "Tên game của bạn",
  dev: "Tên nhà phát triển",
  email: "email-cua-ban@example.com",
  date: "September 20, 2026",   // ngày cập nhật
  year: "2026",
  adNetworks: [
    { name: "Google AdMob", url: "https://policies.google.com/privacy" }
    // thêm hoặc bớt mạng quảng cáo bạn dùng
  ]
};
```

4. Vào **Settings > Pages**, phần *Build and deployment*:
   - Source: **Deploy from a branch**
   - Branch: **main**, thư mục **/ (root)** rồi bấm **Save**
5. Đợi 1 đến 2 phút, link sẽ có dạng:
   `https://<username>.github.io/<ten-repo>/`
6. Dán link đó vào App Store Connect: *App Information > Privacy Policy URL*.

## Dùng cho nhiều game

**Cách 1: mỗi game một repo.** Copy `template/privacy-policy-template.html` thành `index.html` của repo mới, sửa `CONFIG`. Link sạch, dễ nhớ.

**Cách 2: một repo cho tất cả game.** Copy thư mục `games/example-game`, đổi tên thành tên game (không dấu, không khoảng trắng), sửa `CONFIG` trong file `index.html` bên trong. Link sẽ là:
`https://<username>.github.io/<ten-repo>/games/<ten-game>/`

## Mẹo

- Muốn link ngắn gọn ở gốc, đặt tên repo là `<username>.github.io`, khi đó link là `https://<username>.github.io/`.
- Mở thẳng tiếng Việt bằng cách thêm `?lang=vi` vào cuối link. Trang cũng tự chuyển sang tiếng Việt nếu trình duyệt đặt tiếng Việt.
- Link phải mở được **không cần đăng nhập**, hãy thử bằng cửa sổ ẩn danh trước khi nộp.
- Khi đổi nội dung chính sách, nhớ cập nhật `date` trong `CONFIG`.

## Kiểm tra trước khi nộp App Store

- [ ] Đã thay hết `[Game Name]`, `[Developer Name]`, email trong `CONFIG`
- [ ] Danh sách mạng quảng cáo đúng với SDK trong game
- [ ] Nội dung khớp với thực tế (game có tài khoản riêng, server riêng, analytics khác thì phải bổ sung vào trang)
- [ ] Mục **App Privacy** trong App Store Connect khai báo khớp với SDK quảng cáo
- [ ] Nếu dùng IDFA: đã có hộp thoại ATT và `NSUserTrackingUsageDescription`
- [ ] Nếu phát hành ở EU/UK: đã có form đồng ý (Google UMP) và nút mở lại cài đặt quyền riêng tư trong game

## Lưu ý

Đây là mẫu tham khảo, không phải tư vấn pháp lý. Nếu game có doanh thu lớn, có tài khoản người chơi hoặc server riêng, nên nhờ chuyên gia pháp lý rà soát.
# Game-privacy-policy
