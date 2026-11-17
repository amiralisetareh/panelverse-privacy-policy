# TYTO Privacy Policy
**The Keeper of Stories**  
**Effective date:** 17 November 2026  
**Version:** 1.0  
**Bot:** [@titoarchivebot](https://t.me/titoarchivebot)

TYTO is the current name of the project previously known as PanelVerse. This notice describes the application behavior visible in the connected `panelverse_v2` source repository on the effective date. It is an operational description, not legal advice. The actual deployment may differ; the operator must update this policy whenever its software, providers, or data practices change.

## 1. Who operates TYTO
TYTO is an independently operated Telegram bot and digital archive. It is not affiliated with, sponsored by, or endorsed by Telegram, Marvel, DC, or any publisher, author, artist, or media company unless an explicit written statement says otherwise.

**Operator contact:** An official, monitored privacy contact address has not yet been supplied for this project. Before public launch, the operator must add a private contact method here and in the bot profile. Do not post personal data, identity documents, or private rights claims in public GitHub issues.

## 2. What information is involved

### A. Telegram interactions
Telegram sends bot updates needed to deliver messages and button actions. Depending on the interaction, those updates can include Telegram account identifiers, chat identifiers, public profile fields such as a display name or username, and the command, callback, or message content involved in that interaction.

In the inspected application code:
- Ordinary users are not registered in a TYTO user-account database.
- The application does not persist ordinary users' Telegram IDs, usernames, profile names, or message history in its own SQLite database.
- Telegram identifiers are checked for administrator authorization. Temporary state for administrator upload workflows is held in process memory and is not a persistent user profile.
- The bot's public interface is primarily archive browsing, buttons, and deep links. The ordinary-user message handler does not save arbitrary messages as a user history.

Telegram independently processes information under its own terms and privacy policy. TYTO does not control Telegram's platform-level retention or processing.

### B. Archive and catalogue information
The application database stores catalogue and operational records, including titles, descriptions, categories, chapters, series, episodes, Telegram file references, archive status, processing jobs, and publication state. These are archive records, not ordinary user profiles.

### C. Administrator uploads
Authorized administrators can add files through the bot's admin workflow or the protected web-admin interface. For web-admin ingestion, the application can store:
- the uploaded file and its storage path;
- original filename, file extension, MIME type, and file size;
- a SHA-256 file hash used for duplicate detection;
- metadata extracted from the file, which may include title, author, publisher, language, description, page count, duration, codec, artist, album, or other format-specific fields;
- cover images or preview images generated from the file;
- processing status, quality-control results, and administrative audit events.

These records are stored in the operator-controlled SQLite database and configured archive-storage directory. The inspected web-admin code records actions under an administrative actor label such as `web-admin`; it does not use these records as a public-user activity tracker.

### D. Administrator authentication
The web-admin interface is protected by a configured administrator token. The current implementation uses an HTTP-only, SameSite cookie for administrator sessions, with a maximum age of 24 hours. This cookie is for administrators, not a tracking cookie for ordinary bot users. Administrators should access the web-admin interface only over HTTPS and keep the token secret.

### E. Logs and technical information
The application writes operational logs, including timestamps, severity levels, and diagnostic error details. A hosting provider may separately process network information such as IP addresses, request timestamps, and access logs as part of operating the server. The exact hosting provider and its log-retention settings depend on the operator's deployment.

### F. AI features
The inspected code labels the AI assistant as “coming next”; it does not currently implement an active AI conversation feature. The presence of an optional API-key variable in an example configuration does not mean user messages are currently sent to an AI provider. If an AI feature or another external processor is enabled, this policy must be updated before that feature is offered.

## 3. Why information is used
Information is used only as needed to:
- receive and respond to Telegram bot interactions;
- display and deliver archive entries;
- authenticate administrators and manage archive content;
- process administrator-submitted archive files and extract catalogue metadata;
- detect duplicate files, run quality checks, publish approved archive items, and maintain system reliability and security.

## 4. Storage and retention
The current code does not define an automatic retention period for archive files, catalogue records, or operational logs. Archive material and its metadata may remain in the operator's database and storage until an administrator removes them or the service is retired. Temporary administrator workflow state is held in memory and is lost when the bot process stops or restarts.

Telegram and the hosting provider apply their own retention rules to information they process. TYTO cannot set those independent retention periods.

## 5. Sharing and service providers
TYTO does not sell personal information. Information may be processed by:
- **Telegram**, to provide the bot and messaging platform;
- **the server/hosting provider**, to run the bot, database, archive storage, and web-admin interface;
- **GitHub Pages or GitHub**, to host this policy site and its source repository.

The current inspected code does not send ordinary users' messages to an AI provider. Any future integration with an external service must be disclosed in an updated policy.

## 6. Your choices
You can stop interacting with the bot, block it, or delete the conversation from your Telegram client. Those actions do not necessarily erase records independently held by Telegram or archive material maintained by TYTO.

The current application does not provide user accounts, a user-data dashboard, or an automated self-service personal-data deletion command. Because ordinary user profiles and message histories are not persisted in the inspected application database, there may be no TYTO user record to delete. Requests concerning administrator-uploaded archive material should identify the relevant title or archive item.

A private privacy-request contact must be added by the operator before this policy is treated as complete for a public launch. Do not send sensitive personal data through public issue trackers.

## 7. Security
The application uses administrator-ID checks for bot administration and token authentication for the web-admin interface. No online service can guarantee absolute security. Deployment security also depends on the operator's server, network, HTTPS configuration, backups, access controls, and secret management. Bot tokens and administrator tokens must never be committed to a public repository.

## 8. Changes
This policy must be revised when TYTO adds user accounts, analytics, comments, public uploads, payments, AI processing, new third-party services, or other material data practices. The version and effective date at the top will be updated when changes are made.

## 9. Related policies
- [Terms of Service](TERMS_OF_SERVICE.md)
- [Copyright Policy](COPYRIGHT_POLICY.md)
- [Community Guidelines](COMMUNITY_GUIDELINES.md)
- [Data Deletion Policy](DATA_DELETION.md)

---

# سیاست حریم خصوصی TYTO
**نگهبان داستان‌ها**  
**تاریخ اجرا:** ۱۷ نوامبر ۲۰۲۶  
**نسخه:** ۱٫۰  
**ربات:** [@titoarchivebot](https://t.me/titoarchivebot)

TYTO نام فعلی پروژه‌ای است که پیش‌تر با نام PanelVerse شناخته می‌شد. این سند رفتار قابل مشاهده در کد مخزن متصل `panelverse_v2` را در تاریخ اجرای بالا توضیح می‌دهد. این متن راهنمای شفافیت عملیاتی است و مشاوره حقوقی محسوب نمی‌شود. ممکن است نسخه عملیاتی ربات با کد بررسی‌شده تفاوت داشته باشد؛ مالک پروژه باید با هر تغییر در نرم‌افزار، سرویس‌دهندگان یا شیوه پردازش داده، این سند را به‌روزرسانی کند.

## ۱. گرداننده TYTO
TYTO یک ربات تلگرامی و آرشیو دیجیتال مستقل است. این پروژه وابسته، تحت حمایت یا مورد تأیید تلگرام، مارول، دی‌سی، ناشران، نویسندگان، هنرمندان یا شرکت‌های رسانه‌ای نیست؛ مگر آنکه چنین رابطه‌ای به‌صورت رسمی و کتبی اعلام شود.

**راه ارتباطی مالک:** هنوز نشانی رسمی و فعالی برای درخواست‌های حریم خصوصی در اختیار پروژه قرار نگرفته است. مالک باید پیش از انتشار عمومی، یک راه ارتباطی خصوصی و قابل‌پیگیری را در این قسمت و در پروفایل ربات درج کند. اطلاعات شخصی، مدارک هویتی یا درخواست‌های خصوصی حقوقی را در Issues عمومی GitHub منتشر نکنید.

## ۲. چه اطلاعاتی درگیر هستند؟

### الف) تعاملات تلگرام
تلگرام برای اجرای ربات، به‌روزرسانی‌هایی را به ربات می‌فرستد. بسته به نوع تعامل، این داده‌ها ممکن است شناسه حساب تلگرام، شناسه گفتگو، اطلاعات عمومی پروفایل مانند نام نمایشی یا نام کاربری و محتوای فرمان، دکمه یا پیامی را که برای پردازش لازم است، شامل شوند.

در کد بررسی‌شده:
- برای کاربران عادی حساب کاربری TYTO ساخته نمی‌شود.
- شناسه تلگرام، نام کاربری، نام پروفایل یا تاریخچه پیام کاربران عادی در پایگاه داده SQLite برنامه ذخیره نمی‌شود.
- شناسه تلگرام برای تشخیص مدیر مجاز بررسی می‌شود. وضعیت موقت مراحل بارگذاری مدیران در حافظه موقت فرایند نگهداری می‌شود و پروفایل دائمی کاربر نیست.
- رابط عمومی ربات عمدتاً برای مرور آرشیو، استفاده از دکمه‌ها و لینک‌های مستقیم است. پیام‌های دلخواه کاربران عادی به‌عنوان تاریخچه کاربر ذخیره نمی‌شوند.

تلگرام اطلاعات را مستقل از TYTO و طبق شرایط و سیاست حریم خصوصی خودش پردازش می‌کند. TYTO بر نگهداری یا پردازش در سطح پلتفرم تلگرام کنترل ندارد.

### ب) اطلاعات آرشیو و کاتالوگ
پایگاه داده برنامه اطلاعات کاتالوگ و عملیات را نگهداری می‌کند؛ از جمله عنوان‌ها، توضیحات، دسته‌بندی‌ها، فصل‌ها، مجموعه‌ها، قسمت‌ها، شناسه فایل‌های تلگرام، وضعیت آرشیو، وظایف پردازش و وضعیت انتشار. این‌ها سوابق آرشیو هستند، نه پروفایل کاربران عادی.

### ج) فایل‌های بارگذاری‌شده توسط مدیران
مدیران مجاز می‌توانند از طریق بخش مدیریت ربات یا پنل وب محافظت‌شده فایل اضافه کنند. در ورود محتوا از پنل وب، برنامه ممکن است این موارد را ذخیره کند:
- خود فایل بارگذاری‌شده و مسیر ذخیره آن؛
- نام اصلی، پسوند، نوع MIME و اندازه فایل؛
- هش SHA-256 برای تشخیص فایل تکراری؛
- فراداده استخراج‌شده از فایل، مانند عنوان، نویسنده، ناشر، زبان، توضیح، تعداد صفحات، مدت‌زمان، کدک، نام هنرمند یا آلبوم و سایر اطلاعات متناسب با قالب فایل؛
- تصویر جلد یا پیش‌نمایشی که از فایل ساخته می‌شود؛
- وضعیت پردازش، نتیجه کنترل کیفیت و رویدادهای ثبت‌شده مدیریتی.

این داده‌ها در پایگاه داده SQLite و پوشه ذخیره‌سازی آرشیو که مالک پروژه تنظیم کرده است نگهداری می‌شوند. کد فعلی رویدادها را با برچسب مدیریتی مانند `web-admin` ثبت می‌کند و از آن‌ها برای ردیابی فعالیت عمومی کاربران استفاده نمی‌کند.

### د) احراز هویت مدیر
پنل وب مدیریت با یک توکن مدیریتی محافظت می‌شود. پیاده‌سازی فعلی برای نشست مدیر از کوکی HTTP-only و SameSite با حداکثر عمر ۲۴ ساعت استفاده می‌کند. این کوکی برای مدیران است و کوکی ردیابی کاربران عادی ربات نیست. مدیران باید فقط از طریق HTTPS به پنل دسترسی داشته باشند و توکن را محرمانه نگه دارند.

### هـ) گزارش‌ها و اطلاعات فنی
برنامه گزارش‌های عملیاتی شامل زمان، سطح خطا و جزئیات فنی خطاها را ثبت می‌کند. شرکت میزبان سرور نیز ممکن است برای ارائه سرویس، اطلاعات شبکه مانند IP، زمان درخواست و گزارش دسترسی را پردازش کند. شرکت میزبان و مدت نگهداری این گزارش‌ها به تنظیمات استقرار پروژه بستگی دارد.

### و) قابلیت‌های هوش مصنوعی
در کد بررسی‌شده، دستیار هوش مصنوعی با عبارت «به‌زودی» نمایش داده می‌شود و قابلیت گفت‌وگوی فعال با هوش مصنوعی پیاده‌سازی نشده است. وجود متغیر اختیاری کلید API در فایل نمونه تنظیمات به این معنا نیست که پیام کاربران در حال حاضر به سرویس هوش مصنوعی ارسال می‌شود. پیش از فعال‌سازی چنین قابلیتی یا هر پردازشگر خارجی جدید، این سیاست باید به‌روزرسانی شود.

## ۳. هدف استفاده از اطلاعات
اطلاعات فقط در حد نیاز برای دریافت و پاسخ به تعاملات تلگرام، نمایش و ارسال آثار آرشیو، احراز هویت مدیران، مدیریت محتوا، پردازش فایل‌های آرشیوی مدیران و استخراج فراداده، تشخیص فایل تکراری، کنترل کیفیت، انتشار آثار تأییدشده و حفظ پایداری و امنیت سیستم استفاده می‌شود.

## ۴. ذخیره‌سازی و مدت نگهداری
در کد فعلی، مدت نگهداری خودکار مشخصی برای فایل‌های آرشیو، سوابق کاتالوگ یا گزارش‌های عملیاتی تعریف نشده است. فایل‌ها و فراداده آرشیو ممکن است تا زمان حذف توسط مدیر یا پایان فعالیت سرویس در پایگاه داده و فضای ذخیره‌سازی باقی بمانند. وضعیت موقت فرایندهای مدیریتی در حافظه است و با توقف یا راه‌اندازی مجدد فرایند ربات از بین می‌رود.

تلگرام و شرکت میزبان، اطلاعاتی را که خودشان پردازش می‌کنند طبق قواعد مستقل خود نگهداری می‌کنند. TYTO مدت‌های نگهداری مستقل آن‌ها را تعیین نمی‌کند.

## ۵. اشتراک‌گذاری و سرویس‌دهندگان
TYTO اطلاعات شخصی را نمی‌فروشد. داده‌ها ممکن است توسط این سرویس‌ها پردازش شوند:
- **تلگرام** برای ارائه ربات و پیام‌رسان؛
- **شرکت میزبان سرور** برای اجرای ربات، پایگاه داده، فایل‌های آرشیو و پنل وب؛
- **GitHub یا GitHub Pages** برای میزبانی این صفحه و مخزن اسناد.

کد بررسی‌شده پیام کاربران عادی را به سرویس هوش مصنوعی ارسال نمی‌کند. هر اتصال آینده به سرویس خارجی باید در نسخه جدید سیاست اعلام شود.

## ۶. انتخاب‌های شما
می‌توانید تعامل با ربات را متوقف کنید، آن را مسدود کنید یا گفتگوی آن را از برنامه تلگرام خود حذف کنید. این اقدامات الزاماً اطلاعاتی را که تلگرام یا آرشیو TYTO مستقلاً نگهداری می‌کنند حذف نمی‌کند.

نسخه فعلی برنامه حساب کاربری، داشبورد داده‌های شخصی یا فرمان خودکار حذف اطلاعات شخصی ندارد. از آنجا که پروفایل کاربران عادی و تاریخچه پیام‌هایشان در پایگاه داده برنامه ذخیره نمی‌شود، ممکن است اساساً رکورد کاربری‌ای در TYTO برای حذف وجود نداشته باشد. درخواست‌های مربوط به محتوای بارگذاری‌شده توسط مدیران باید عنوان یا شناسه مورد آرشیو را مشخص کند.

پیش از آنکه این سند برای انتشار عمومی کامل تلقی شود، مالک باید راه ارتباطی خصوصی درخواست‌های حریم خصوصی را اضافه کند. اطلاعات حساس را از طریق سامانه‌های عمومی ثبت Issue ارسال نکنید.

## ۷. امنیت
برنامه برای مدیریت ربات از بررسی شناسه مدیر و برای پنل وب از احراز هویت توکنی استفاده می‌کند. هیچ سرویس آنلاین نمی‌تواند امنیت مطلق را تضمین کند. امنیت استقرار به سرور، شبکه، HTTPS، پشتیبان‌گیری، کنترل دسترسی و مدیریت محرمانه کلیدها نیز وابسته است. توکن ربات و توکن مدیر نباید هرگز در مخزن عمومی قرار گیرند.

## ۸. تغییرات
با اضافه شدن حساب کاربری، تحلیل رفتار، دیدگاه، بارگذاری عمومی، پرداخت، پردازش هوش مصنوعی، سرویس‌دهندگان جدید یا هر شیوه مهم دیگری برای پردازش داده، این سیاست باید بازبینی شود. نسخه و تاریخ اجرا در ابتدای سند به‌روزرسانی خواهد شد.

## ۹. سیاست‌های مرتبط
- [شرایط استفاده](TERMS_OF_SERVICE.md)
- [سیاست حق نشر](COPYRIGHT_POLICY.md)
- [قوانین جامعه](COMMUNITY_GUIDELINES.md)
- [سیاست حذف داده](DATA_DELETION.md)
