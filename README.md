# telegram1-alert-bot
import requests

# بيانات التليجرام
TOKEN = '7835995666:AAFebqcawO79wgWvT7VaZpljgXWxRAwcBiM'
CHAT_ID = '7853842422'

# الرسالة المخصصة
message = "🚨 إشعار مباشر من Replit! تم ربط البوت بنجاح وجاهز للإرسال 🔥"

# إعداد الرابط
url = f'https://api.telegram.org/bot{TOKEN}/sendMessage'
params = {
    'chat_id': CHAT_ID,
    'text': message
}

# تنفيذ الطلب
response = requests.get(url, params=params)

# النتيجة
if response.status_code == 200:
    print("✅ تم إرسال الإشعار بنجاح إلى تليجرام.")
else:
    print("❌ خطأ في الإرسال:", response.text)
