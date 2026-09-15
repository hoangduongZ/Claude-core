# Claude Code trên máy của bạn — sổ tay trực quan

Tài liệu tiếng Việt giải thích cách Claude Code hoạt động trên máy host: cây thư mục `.claude`, thứ tự ưu tiên của `settings.json`, cơ chế memory, hooks, MCP và permission model. Viết theo phương pháp Feynman, mỗi khái niệm kèm một hình tương tác.

Hai bản riêng cho hai họ hệ điều hành, cùng 14 mục nên đọc song song được.

## Nội dung

| File | Nội dung |
|---|---|
| `index.html` | Trang chủ, chọn nền tảng |
| `windows.html` | Bản Windows 10 / 11 (native và WSL2) |
| `macos-linux.html` | Bản macOS và Linux, có nút chuyển macOS ⇄ Linux ngay trong trang |

Không có bước build, không có dependency, không gọi API. Mỗi file là một HTML đứng độc lập; JavaScript chỉ chạy các widget trong trang. Thứ duy nhất tải từ ngoài là font Google Fonts — xoá thẻ `<link>` đó đi thì trang vẫn đọc được bằng font hệ thống.

## Deploy lên GitHub Pages

```bash
git init
git add .
git commit -m "docs: so tay Claude Code tren may host"
git branch -M main
git remote add origin git@github.com:<user>/<repo>.git
git push -u origin main
```

Sau đó vào **Settings → Pages**, chọn **Deploy from a branch**, branch `main`, thư mục `/ (root)`, rồi Save. Vài phút sau site có ở `https://<user>.github.io/<repo>/`.

Nếu muốn để tài liệu trong thư mục con thì chọn `/docs` thay vì root và di chuyển ba file vào đó.

Không cần `.nojekyll` vì không có file hay thư mục nào bắt đầu bằng dấu gạch dưới.

## Kiểm tra trước khi publish

Nội dung được viết mà không đối chiếu trực tiếp được với tài liệu chính thức, nên mỗi khẳng định đều mang nhãn độ tin cậy: **docs chính thức** / **quan sát thực tế** / **tôi không chắc**. Cả hai bản đều có nút làm mờ những phần chưa chắc chắn.

Trước khi công bố, nên mở **mục 13** của bản hợp với máy bạn, chạy đoạn script ở đó, và sửa lại những chỗ lệch so với thực tế trên máy.

Nguồn chính thức để đối chiếu: <https://docs.claude.com/en/docs/claude-code/overview>

## Ghi chú

Tài liệu không chính thức, không liên kết với Anthropic.
