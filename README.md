# اپ آنتن (iOS) — SwiftUI

اپ بومی آیفون که تمام مراحل پروژه‌ی `iPhone-antenna-profile` را داخل یک اپ انجام می‌دهد:
راهنمای قدم‌به‌قدم با تیک پیشرفت، ساخت پروفایل APN (UUID یکتا، XLAT464، انتخاب IPv4/IPv6)،
باز کردن در Safari، تایمر هواپیما، نصب/اجرای شورتکات، نکات و راهنمای حذف.

## نصب روی آیفون

### راه ۱: دارید Mac + Xcode
1. `brew install xcodegen` سپس در پوشه‌ی پروژه: `xcodegen generate`
2. `Anten.xcodeproj` را باز کنید ← Signing & Capabilities ← Team (Apple ID شخصی کافی است)
3. آیفون را وصل کنید، به‌عنوان مقصد انتخاب کنید و Run بزنید.
4. روی گوشی: Settings ← Privacy & Security ← Developer Mode را روشن کنید (و اولین بار Trust).
   (با Apple ID رایگان، اپ ۷ روز اعتبار دارد؛ دوباره Run کنید.)

### راه ۲: بدون Mac (ساخت IPA با GitHub Actions)
1. این پوشه را در یک مخزن GitHub بریزید و push کنید.
2. تب Actions ← «Build unsigned IPA» ← خروجی `Anten.ipa` را دانلود کنید.
3. با Sideloadly یا AltStore (با Apple ID خودتان) روی آیفون نصب کنید.

## نکات فنی
- iOS اجازه‌ی نصب مستقیم پروفایل از داخل اپ را نمی‌دهد. اپ فایل را روی loopback (`127.0.0.1`) سرو می‌کند و Safari آن را می‌گیرد؛ سپس نصب از Settings انجام می‌شود.
- بدون وابستگی خارجی، حداقل iOS 16، فقط iPhone.
