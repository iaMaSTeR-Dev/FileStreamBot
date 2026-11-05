<div dir="rtl" align="center">

# 🚀 Telegram File Stream Bot

<p>
یک ربات تلگرامی قدرتمند و کارآمد که برای فایل‌های شما لینک مستقیم با قابلیت استریم تولید می‌کند. این ربات به همراه یک پنل مدیریت امن و پایدار ارائه می‌شود که با Redis کار می‌کند.
</p>

</div>

---

<div dir="rtl">

### ✨ ویژگی‌ها

-   **تولید لینک آنی**: برای هر فایلی که به ربات ارسال کنید، به سرعت یک لینک مستقیم برای دانلود یا پخش آنلاین دریافت نمایید.
-   **پشتیبانی از فایل‌های حجیم**: بدون محدودیت در حجم فایل (البته با در نظر گرفتن محدودیت‌های خود تلگرام).
-   **سرعت بالا**: لینک‌ها بدون نیاز به دانلود اولیه فایل روی سرور شما ساخته می‌شوند که باعث افزایش سرعت دسترسی می‌شود.
-   **پنل مدیریت وب امن و پایدار**: کاربران را مدیریت کرده و آمار ربات را از طریق یک پنل وب ساده و امن مشاهده کنید. این پنل دارای رمزنگاری برای رمز عبور، حفاظت در برابر حملات CSRF است.
-   **امنیت**: دسترسی به ربات را به کاربران مجاز محدود کنید.
-   **راه‌اندازی آسان**: ربات خود را به سادگی و با چند دستور ساده، فعال و راه‌اندازی کنید.

### 🔧 نصب و راه‌اندازی

برای راه‌اندازی این ربات، مراحل زیر را دنبال کنید:

1.  **کلون کردن پروژه:**
    ```bash
    git clone https://github.com/iamast3r/FileStreamBot.git
    cd FileStreamBot
    ```

2.  **نصب پیش‌نیاز (Redis):**
    این پروژه برای پایداری جلسات ورود ادمین به Redis نیاز دارد. آن را روی سرور خود نصب کنید.
    ```bash
    sudo apt update
    sudo apt install redis-server -y
    sudo systemctl enable redis-server.service
    ```

3.  **ایجاد و فعال‌سازی محیط مجازی:**
    ```bash
    python3 -m venv ./venv
    source ./venv/bin/activate
    ```
    *(اگر از ویندوز استفاده می‌کنید، از دستور `.\venv\Scripts\activate` استفاده کنید)*

4.  **نصب پیش‌نیازها:**
    ```bash
    pip3 install -r requirements.txt
    ```

5.  **تنظیم متغیرهای محیطی:**
    یک فایل `.env` با ساختار زیر ایجاد کرده و اطلاعات خود را وارد کنید.

 ```ini
    # Get this from my.telegram.org
    API_ID=
    API_HASH=

    # Get this from @BotFather
    BOT_TOKEN=

    # This is a channel ID for storing files. The bot must be an admin in this channel.
    # It can be a public or private channel. For private channels, use its negative ID (e.g., -100123456789).
    BIN_CHANNEL=

    # Your Telegram user ID. The bot will recognize you as the owner.
    OWNER_ID=

    # The port on which the web server will listen. Default is 8080.
    PORT=

    # Your server's public IP address or a Fully Qualified Domain Name (FQDN).
    FQDN=

    # Set to "true" if you are using SSL/TLS (HTTPS), otherwise "false".
    HAS_SSL=

    # Set to "true" to save pyrogram session files.
    USE_SESSION_FILE=

    # Credentials for the web admin panel.
    ADMIN_USERNAME=
    ADMIN_PASSWORD_HASH= # Generate this in the next step

    # Redis URL for persistent admin sessions
    REDIS_URL=redis://localhost:6379/0
  ```


6.  **تنظیم رمز عبور مدیر (به روش امن):**
    اسکریپت موجود در پروژه را اجرا کنید تا یک نسخه هش شده (امن) از رمز عبور دلخواهتان بسازید.
    ```bash
    python3 generate_hash.py
    ```
    پس از اجرای دستور، رمز عبور مورد نظر خود را وارد کرده و `Enter` را بزنید. اسکریپت یک رشته هش شده به شما می‌دهد. این رشته را به طور کامل کپی کرده و به عنوان مقدار `ADMIN_PASSWORD_HASH` در فایل `.env` خود قرار دهید.

7.  **اجرای ربات:**
    ```bash
    python3 -m WebStreamer
    ```

اکنون ربات شما فعال است و می‌توانید از آن استفاده کنید!

### 🌐 استفاده از پنل وب

-   **دسترسی**: شما می‌توانید با مراجعه به آدرس `http://<Your_FQDN>:<PORT>/admin/login` در مرورگر خود به پنل مدیریت دسترسی پیدا کنید.
-   **ورود**: برای ورود از `ADMIN_USERNAME` و رمز عبوری که در **مرحله ۶** تنظیم کردید، استفاده کنید. جلسه ورود شما حتی پس از ری‌استارت کردن ربات نیز پایدار خواهد بود.
-   **امکانات**: از طریق داشبورد می‌توانید آمار ربات را مشاهده کرده، کاربران را مدیریت (حذف/اضافه) کنید و سایر اقدامات مدیریتی را انجام دهید.


### ❤️ حمایت مالی و دونیت

اگر این پروژه برای شما مفید بوده و تمایل به حمایت از توسعه آن دارید، می‌توانید از طریق آدرس‌های زیر کمک‌های مالی خود را ارسال کنید:

-   **USDT (TRC20):** `TWKQ8QSinouRAMZ4cSorMNfWb2XBHFSRL1`
-   **USDT (BEP20):** `0x10E8170eb6251801093e9388e2Ff09419E4cf365`
-   **LTC:** `ltc1qnhcus0jmvxhhc3mdshf3hg832nwglukk6a2kxs`
-   **GRAM:** `UQAgMDdXQEkJwdAAY7AxWB8ULXU7J1Up74pyG-_DJPSQbEJh`

از حمایت شما بسیار سپاسگزاریم!

### 🤝 مشارکت

از مشارکت شما در این پروژه استقبال می‌کنیم. اگر پیشنهاد یا ایده‌ای برای بهبود دارید، لطفاً یک [Issue](https://github.com/iamast3r/TG-File2Link/issues) باز کنید یا یک [Pull Request](https://github.com/iamast3r/TG-File2Link/pulls) ارسال کنید.

### 📝 لایسنس

این پروژه تحت لایسنس [GNU AGPLv3](LICENSE) منتشر شده است.

### 🌟 اعتبار

این پروژه یک نسخه فورک شده و بهبود یافته از پروژه [TG-FileStreamBot](https://github.com/EverythingSuckz/TG-FileStreamBot) است.

---
<div align="center">
  <p>ساخته شده با ❤️ و پایتون</p>
</div>

</div>
