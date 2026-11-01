# مدرسه‌یار معلم — Android Direct API v3.1.0 Teal Pro

نسخه‌ی Native اندروید با Jetpack Compose و اتصال مستقیم به API واقعی مدرسه‌یار.

## طراحی
این نسخه بر اساس طرح تاییدشده‌ی فیروزه‌ای/سفید بازطراحی شده است:
- صفحه ورود Native با ظاهر روشن و حرفه‌ای
- داشبورد خلاصه و سریع
- کارت‌های دسترسی سریع با آیکون‌های Material
- نمایش کلاس جاری و ثبت مستقیم حضور و غیاب
- کلاس‌ها و دانش‌آموزان با کارت‌های اختصاصی
- پیام‌ها و گفتگو با UI پیام‌رسانی Native
- بانک تمرین و کتابخانه دیجیتال با کارت‌های اختصاصی
- Bottom Navigation سبک و ساده
- آیکون اپ با پالت فیروزه‌ای جدید

طرح مرجع در `design/approved-teal-professional-ui.png` قرار دارد.

## معماری
- بدون WebView
- بدون DOM scraping
- بدون باز کردن نسخه وب
- Jetpack Compose + Material 3
- ارتباط مستقیم با API هاست

Base URL پیش‌فرض:
`https://scooljavanrood.ir/app/`

## قابلیت‌های متصل به API
- ورود معلم: `/api/staff/login`
- MFA مطابق رفتار هاست
- بررسی حساب: `/api/staff/me`
- تغییر رمز اجباری: `/api/staff/change-password`
- داشبورد: `/api/teacher/dashboard`
- Workspace معلم: `/api/teacher/workspace`
- حضور و غیاب: `/api/teacher/attendance/submit`
- دفتر نمره: `/api/staff/gradebook`
- ثبت نمره: `/api/staff/gradebook/entry`
- پیام‌ها: `/api/academic-messages/p58/*`
- تمرین‌ها: `/api/practice/p59/list`
- کتابخانه: `/api/library/p62/list`
- نشست‌های حساب: `/api/staff/sessions`
- خروج: `/api/staff/logout`

## MFA
مرحله اول فقط نام کاربری و رمز عبور است. اگر سرور `MFA_REQUIRED` برگرداند، پنجره Native فقط کد Authenticator یا در صورت مجاز بودن Recovery Code را می‌گیرد. نام کاربری و رمز دوباره از کاربر پرسیده نمی‌شوند.

## Build
از GitHub Actions با Workflow زیر استفاده کنید:
`.github/workflows/build-apk.yml`

نسخه: `3.1.0-teal-pro`  
Version Code: `14`
