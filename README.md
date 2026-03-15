# 🚀 Developer CLI Toolkit

> أداة سطر أوامر شاملة تسرّع عملك اليومي في التطوير — تدعم **macOS** و**Windows** و**Linux**

![Version](https://img.shields.io/badge/version-1.5.0-blue)
![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Linux-lightgrey)
![Shell](https://img.shields.io/badge/shell-bash-green)
![License](https://img.shields.io/badge/license-MIT-orange)

---

## 📋 المحتويات

- [المتطلبات](#-المتطلبات)
- [التثبيت](#-التثبيت)
- [الأوامر المتاحة](#-الأوامر-المتاحة)
  - [Repository](#-repository)
  - [Git Shortcuts](#-git-shortcuts)
  - [Project Manager](#-project-manager)
  - [Flutter](#-flutter)
  - [Docker](#-docker)
  - [Node.js / Vue](#-nodejs--vue)
  - [.NET](#-net)
  - [Web](#-web)
  - [Aliases](#-aliases)
  - [Doctor](#-doctor)
  - [أوامر أخرى](#-أوامر-أخرى)
- [نظام الإشعارات](#-نظام-الإشعارات)
- [التحديث التلقائي](#-التحديث-التلقائي)
- [دعم أنظمة التشغيل](#-دعم-أنظمة-التشغيل)

---

## 📦 المتطلبات

| الأداة | الاستخدام | مطلوب |
|--------|-----------|--------|
| `git` | إدارة الكود | ✅ |
| `gh` | GitHub CLI | ✅ |
| `flutter` | مشاريع Flutter | اختياري |
| `docker` | الحاويات | اختياري |
| `node` / `npm` | مشاريع Node.js / Vue | اختياري |
| `dotnet` | مشاريع .NET | اختياري |

---

## ⚙️ التثبيت

### macOS / Linux

```bash
# 1. تحميل السكريبت
curl -o ~/scripts/dev https://raw.githubusercontent.com/m199671ms/dotfiles/main/dev

# 2. إعطاء صلاحية التشغيل
chmod +x ~/scripts/dev

# 3. إضافة المجلد للـ PATH
echo 'export PATH="$HOME/scripts:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

### Windows (Git Bash أو WSL)

```bash
# 1. إنشاء مجلد السكريبتات
mkdir -p ~/scripts

# 2. تحميل السكريبت
curl -o ~/scripts/dev https://raw.githubusercontent.com/m199671ms/dotfiles/main/dev

# 3. إعطاء صلاحية التشغيل
chmod +x ~/scripts/dev

# 4. إضافة المجلد للـ PATH
echo 'export PATH="$HOME/scripts:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### التحقق من التثبيت

```bash
dev info
```

---

## 📚 الأوامر المتاحة

---

### 📦 Repository

#### `dev create-repo`
إنشاء مستودع GitHub جديد ورفعه تلقائياً.

```bash
dev create-repo
```

**الخطوات التلقائية:**
1. إعداد SSH key
2. اختيار نوع المشروع (Flutter / Node.js / Vue / .NET / Web)
3. إنشاء `.gitignore` مناسب
4. إنشاء `README.md`
5. إنشاء المستودع على GitHub ورفع الكود

---

### ⚡ Git Shortcuts

#### `dev push`
إضافة جميع التغييرات + commit + push بأمر واحد.

```bash
dev push "fix login bug"
# أو بدون رسالة (سيطلب منك الإدخال)
dev push
```

#### `dev sync`
سحب آخر التغييرات من الـ remote مع rebase.

```bash
dev sync
```

#### `dev status`
عرض حالة المشروع مع آخر 7 commits.

```bash
dev status
```

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 Git Status
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Branch : main
  Remote : git@github.com:user/repo.git
  Ahead  : 2 commits

M  lib/main.dart
?? pubspec.lock

Last 7 commits:
* abc1234 fix: login button
* def5678 feat: add dark mode
```

#### `dev log`
عرض git log بشكل مرئي مع graph.

```bash
dev log
```

#### `dev new-branch`
إنشاء branch جديد والتبديل إليه.

```bash
dev new-branch feature/login
# أو بدون اسم (سيطلب منك الإدخال)
dev new-branch
```

#### `dev switch-branch`
عرض جميع الفروع والتبديل بينها.

```bash
dev switch-branch
```

#### `dev merge-clean`
دمج الـ branch الحالي في main وحذفه.

```bash
dev merge-clean
# سيسألك: Merge 'feature/login' into (default: main):
```

#### `dev clean-branches`
حذف جميع الفروع المدمجة في main.

```bash
dev clean-branches
```

#### `dev undo`
التراجع عن آخر commit مع الاحتفاظ بالتغييرات في staging.

```bash
dev undo
```

---

### 📂 Project Manager

#### `dev save-project`
حفظ مسار المشروع الحالي باسم مختصر.

```bash
cd ~/projects/my-flutter-app
dev save-project myapp
# ✅ Project 'myapp' saved → /Users/user/projects/my-flutter-app
```

#### `dev goto`
الانتقال السريع لمشروع محفوظ وفتحه في المحرر.

```bash
dev goto myapp
# ✅ Switched to: /Users/user/projects/my-flutter-app
# يفتح VS Code تلقائياً
```

#### `dev projects`
عرض جميع المشاريع المحفوظة.

```bash
dev projects
```

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📁 Saved Projects
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  ● myapp    → /Users/user/projects/my-flutter-app
  ● backend  → /Users/user/projects/api-server
  ✗ oldapp   → /Users/user/projects/old (missing)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

#### `dev remove-project`
حذف مشروع من القائمة.

```bash
dev remove-project myapp
```

---

### ⚡ Flutter

#### `dev flutter-new`
إنشاء مشروع Flutter جديد.

```bash
dev flutter-new my_app
# سيسألك عن: Organization (e.g. com.company)
```

#### `dev flutter-run`
تشغيل مشروع Flutter مع اختيار الجهاز.

```bash
# من داخل المشروع
dev flutter-run

# أو بتحديد مشروع محفوظ مباشرة
dev flutter-run myapp

# أو بمسار مباشر
dev flutter-run ~/projects/my-flutter-app
```

**خيارات التشغيل حسب النظام:**

| macOS | Windows | Linux |
|-------|---------|-------|
| Android | Android | Android |
| iOS | Windows Desktop | Linux Desktop |
| macOS Desktop | Web | Web |
| Web | جهاز محدد | جهاز محدد |
| جهاز محدد | | |

> **إصلاح تلقائي:** عند اكتشاف مشكلة CocoaPods يقوم السكريبت بإصلاحها تلقائياً بـ 3 مراحل متصاعدة.

#### `dev flutter-build`
بناء المشروع مع إشعار عند الانتهاء.

```bash
dev flutter-build
# الخيارات: APK release / APK debug / iOS / Web / Desktop
```

#### `dev flutter-test`
تشغيل الاختبارات مع إشعار عند الانتهاء.

```bash
dev flutter-test
```

#### `dev flutter-upgrade`
ترقية Flutter وجميع الـ packages.

```bash
dev flutter-upgrade
```

#### `dev clean`
تنظيف مشروع Flutter.

```bash
dev clean
```

---

### 🐳 Docker

#### `dev docker-build`
بناء Docker image مع إشعار عند الانتهاء.

```bash
dev docker-build myapp
# سيسألك عن: Tag (default: latest)
```

#### `dev docker-run`
تشغيل Docker container.

```bash
dev docker-run myapp
# سيسألك عن: Port mapping, Container name
```

#### `dev docker-list`
عرض جميع الـ images والـ containers الجارية.

```bash
dev docker-list
```

#### `dev docker-stop`
إيقاف جميع الـ containers الجارية.

```bash
dev docker-stop
```

#### `dev docker-clean`
حذف الـ containers المتوقفة والـ images غير المستخدمة.

```bash
dev docker-clean
```

#### `dev compose-up` / `dev compose-down`
تشغيل وإيقاف خدمات docker-compose.

```bash
dev compose-up    # docker compose up -d
dev compose-down  # docker compose down
```

---

### 🟢 Node.js / Vue

#### `dev npm-install`
تثبيت الـ dependencies.

```bash
dev npm-install
```

#### `dev npm-run`
تشغيل npm script.

```bash
dev npm-run dev
dev npm-run test
dev npm-run build
```

#### `dev npm-build`
بناء المشروع مع إشعار عند الانتهاء.

```bash
dev npm-build
```

#### `dev vue-new`
إنشاء مشروع Vue جديد.

```bash
dev vue-new my-vue-app
```

---

### 💜 .NET

#### `dev dotnet-new`
إنشاء مشروع .NET جديد.

```bash
dev dotnet-new MyProject
# الخيارات: console / webapi / mvc / blazorwasm / classlib
```

#### `dev dotnet-run`
تشغيل المشروع.

```bash
dev dotnet-run
```

#### `dev dotnet-build`
بناء المشروع مع إشعار عند الانتهاء.

```bash
dev dotnet-build
```

#### `dev dotnet-test`
تشغيل الاختبارات مع إشعار عند الانتهاء.

```bash
dev dotnet-test
```

---

### 🌐 Web

#### `dev web-serve`
تشغيل local server وفتح المتصفح تلقائياً.

```bash
dev web-serve        # المنفذ الافتراضي: 3000
dev web-serve 8080   # منفذ مخصص
```

> يستخدم `npx serve` إذا كان Node.js مثبتاً، وإلا يستخدم `python3 -m http.server`.

---

### ⚡ Aliases

نظام اختصارات شخصية للأوامر الأكثر استخداماً.

#### `dev alias-add`
إضافة اختصار جديد.

```bash
dev alias-add r flutter-run
dev alias-add b flutter-build
dev alias-add p push
dev alias-add s status
```

#### `dev alias-list`
عرض جميع الاختصارات.

```bash
dev alias-list
```

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚡ Custom Aliases
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  dev r → dev flutter-run
  dev b → dev flutter-build
  dev p → dev push
  dev s → dev status
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

#### `dev alias-remove`
حذف اختصار.

```bash
dev alias-remove r
```

---

### 🏥 Doctor

#### `dev doctor`
فحص شامل لبيئة التطوير واكتشاف المشاكل وإصلاحها تلقائياً.

```bash
dev doctor
```

**ما يفحصه:**

| الفحص | الإجراء عند وجود مشكلة |
|-------|------------------------|
| Git config (name, email) | يطلب منك الإدخال ويضبطه |
| SSH keys لـ GitHub | يخبرك بطريقة الإنشاء |
| Flutter doctor | يشغّل `flutter doctor` ويعرض الملخص |
| CocoaPods (macOS) | يشغّل `pod repo update` تلقائياً |
| Android SDK | يتحقق من `ANDROID_HOME` |
| Docker | يتحقق من تشغيل الـ daemon |
| GitHub CLI auth | يتحقق من `gh auth status` |
| Node.js / npm | يتحقق من الإصدار |
| disk space | يحذّر إذا كانت المساحة أقل من 5GB |

**مثال على الناتج:**

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🏥 Dev Doctor — macOS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✅ Git installed        — git version 2.39.0
✅ Git name             — Mohammed Saeed
✅ Git email            — user@gmail.com
✅ GitHub CLI           — logged in as m199671ms
✅ SSH key (personal)   — found
⚠️  SSH key (company)   — not found
✅ Flutter              — Flutter 3.16.0
⚠️  CocoaPods           — out of date → fixing...
✅ CocoaPods            — fixed!
✅ Docker               — running
❌ Android SDK          — ANDROID_HOME not set
✅ Node.js              — v20.10.0
✅ Disk space           — 45.2 GB free
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚠️  2 warnings  |  ❌ 1 error
Run 'dev doctor --fix' to auto-fix all issues
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

```bash
# فحص فقط بدون إصلاح
dev doctor

# فحص وإصلاح تلقائي لكل المشاكل
dev doctor --fix
```

---

### 🔧 أوامر أخرى

#### `dev ssh-check`
إعداد أو التحقق من مفاتيح SSH لـ GitHub.

```bash
dev ssh-check
# سيسألك: personal أو company
```

#### `dev config`
عرض وتعديل الإعدادات.

```bash
dev config
```

**الإعدادات المتاحة:**
- Personal GitHub email
- Company GitHub email
- اسمك الكامل
- المحرر الافتراضي (code / vim / nano)

#### `dev info`
عرض معلومات البيئة الكاملة.

```bash
dev info
```

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   Developer CLI Toolkit v6
   Version  : 1.3.0
   Platform : macos
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Tools:
  ✅ git    — git version 2.39.0
  ✅ gh     — gh version 2.40.0
  ✅ flutter — Flutter 3.16.0
  ✅ docker — Docker version 24.0.0
  ❌ dotnet — not installed
```

#### `dev logs`
عرض آخر 30 عملية من سجل النشاط.

```bash
dev logs
```

#### `dev update`
تحديث السكريبت — يرفع تعديلاتك المحلية أولاً ثم يتحقق من تحديثات GitHub.

```bash
dev update
```

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔄 Checking for updates...
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
▶  Local changes detected. Pushing to GitHub...
✅ Local changes pushed!
  Current version : 1.3.0
  Latest version  : 1.3.0
✅ Already up to date!
```

#### `dev rollback`
الرجوع لإصدار سابق من السكريبت.

```bash
dev rollback
```

#### `dev help`
عرض قائمة جميع الأوامر.

```bash
dev help
```

---

## 🔔 نظام الإشعارات

السكريبت يرسل إشعار نظام تلقائياً عند انتهاء العمليات الطويلة مع الوقت المستغرق.

| العملية | الإشعار |
|---------|---------|
| `flutter-build` | ✅ Flutter Build APK — اكتمل في 2m 34s |
| `docker-build` | ✅ Docker Build myapp — اكتمل في 45s |
| `flutter-test` | ❌ Flutter Tests — فشل بعد 12s |
| `dotnet-build` | ✅ .NET Build — اكتمل في 8s |
| `npm-build` | ✅ Node Build — اكتمل في 30s |

**دعم الأنظمة:**
- **macOS** — إشعار نظام مع صوت (Glass للنجاح، Basso للفشل)
- **Windows** — Windows Toast Notification عبر PowerShell
- **Linux** — `notify-send` (يتطلب `libnotify`)

---

## 🔄 التحديث التلقائي

```bash
dev update
```

**آلية العمل:**
1. يتحقق من وجود تعديلات محلية غير مرفوعة ويرفعها تلقائياً
2. يقارن الإصدار الحالي بآخر إصدار على GitHub
3. يطلب تأكيدك قبل تطبيق أي تحديث
4. يحفظ نسخة احتياطية تلقائياً قبل التحديث

**الرجوع لإصدار سابق:**
```bash
dev rollback
# يعرض قائمة بجميع النسخ الاحتياطية المتاحة
```

---

## 🖥️ دعم أنظمة التشغيل

| الميزة | macOS | Windows | Linux |
|--------|:-----:|:-------:|:-----:|
| Git commands | ✅ | ✅ | ✅ |
| Flutter (Android) | ✅ | ✅ | ✅ |
| Flutter (iOS) | ✅ | ❌ | ❌ |
| Flutter (Desktop) | macOS | Windows | Linux |
| Flutter (Web) | ✅ | ✅ | ✅ |
| Docker | ✅ | ✅ | ✅ |
| إشعارات | osascript | PowerShell | notify-send |
| فتح المتصفح | `open` | `cmd /c start` | `xdg-open` |
| SSH Agent | ✅ | OpenSSH Service | ✅ |

> **Windows:** يعمل على Git Bash أو WSL. لتثبيت WSL: `wsl --install` في PowerShell.

---

## 📁 ملفات الإعدادات

| الملف | الوظيفة |
|-------|---------|
| `~/.devtoolkit_config` | الإعدادات الأساسية (emails, name, editor) |
| `~/.devtoolkit_projects` | المشاريع المحفوظة |
| `~/.devtoolkit_aliases` | الاختصارات المخصصة |
| `~/.devtoolkit.log` | سجل النشاط |

---

## 🛠️ أمثلة الاستخدام اليومي

```bash
# بداية يوم العمل
dev doctor              # فحص البيئة وإصلاح أي مشاكل
dev goto myapp          # الانتقال للمشروع
dev sync                # سحب آخر التغييرات
dev flutter-run         # تشغيل التطبيق

# أثناء العمل
dev s                   # alias لـ dev status
dev p "fix: auth bug"   # alias لـ dev push

# قبل الـ PR
dev flutter-test        # تشغيل الاختبارات
dev new-branch feature/payment   # branch جديد
dev p "feat: add payment"
dev merge-clean         # دمج وحذف الـ branch

# تحديث السكريبت
dev update              # يرفع تعديلاتك ويتحقق من تحديثات
```

---

## 📝 الترخيص

MIT License — محمد سعيد

---

<div align="center">
  صُنع بـ ❤️ لتسريع التطوير اليومي
</div>
