<div align="center">

<img src="https://img.shields.io/badge/version-1.5.0-6C63FF?style=for-the-badge" />
<img src="https://img.shields.io/badge/platform-macOS%20%7C%20Linux%20%7C%20Windows-00B4A6?style=for-the-badge" />
<img src="https://img.shields.io/badge/shell-bash-1E1E2E?style=for-the-badge&logo=gnubash&logoColor=white" />
<img src="https://img.shields.io/badge/license-MIT-F4A261?style=for-the-badge" />

# 🚀 Developer CLI Toolkit

**أداة سطر أوامر شاملة تجمع كل ما يحتاجه المطور في مكان واحد**

*A comprehensive CLI toolkit that unifies your entire development workflow*

[العربية](#-الدليل-العربي) · [English](#-english-guide) · [الأوامر](#-جميع-الأوامر--all-commands)

</div>

---

## 📖 الدليل العربي

### ما هو هذا السكريبت؟

**Developer CLI Toolkit** هو سكريبت Bash متكامل يختصر عشرات الأوامر اليومية في واجهة موحدة وبسيطة. بدل أن تتذكر أوامر git المعقدة، أو تفتح Docker Desktop، أو تبحث عن أوامر Flutter — كل شيء يصبح `dev <أمر>`.

### ✨ المميزات الرئيسية

- **🌍 متعدد الأنظمة** — يعمل على macOS وLinux وWindows (WSL) تلقائياً
- **⚡ Git مبسّط** — push وsync وbranches بأوامر قصيرة
- **📱 Flutter كامل** — إنشاء وتشغيل وبناء مع إصلاح تلقائي لمشاكل CocoaPods وGradle
- **🐳 Docker** — إدارة كاملة للـ containers وcompose
- **📂 مدير مشاريع** — احفظ مشاريعك وانتقل بينها فوراً
- **🔔 إشعارات** — إشعار نظام عند اكتمال أو فشل أي عملية طويلة
- **🔄 تحديث ذاتي** — يحدّث نفسه من GitHub مع دعم الـ rollback
- **⚡ Aliases** — اصنع اختصاراتك الخاصة
- **🏥 Doctor** — يفحص بيئتك ويصلح المشاكل تلقائياً
- **💡 رسائل خطأ ذكية** — عند الفشل يقترح الحل مباشرة

### 📦 التثبيت

```bash
# 1. استنساخ المستودع
git clone git@github.com:m199671ms/dotfiles.git ~/scripts

# 2. إضافة المجلد لـ PATH
echo 'export PATH="$HOME/scripts:$PATH"' >> ~/.zshrc
source ~/.zshrc

# 3. تفعيل الصلاحيات
chmod +x ~/scripts/dev

# 4. الإعداد الأول (سيطلب منك البيانات تلقائياً)
dev info
```

### 🗂️ هيكل الملفات

```
scripts/
├── dev              ← الملف الرئيسي (الموزّع)
└── lib/
    ├── utils        ← الألوان، اللوغ، الـ Spinner، الإشعارات
    ├── config       ← الإعدادات و SSH
    ├── git          ← عمليات Git
    ├── flutter      ← Flutter كاملاً
    ├── docker       ← Docker وCompose
    ├── frameworks   ← Node.js · Vue · .NET · Web
    ├── projects     ← مدير المشاريع
    ├── repo         ← إنشاء المستودعات
    ├── doctor       ← فحص وإصلاح البيئة
    ├── aliases      ← الاختصارات المخصصة
    ├── update       ← التحديث والـ Rollback
    └── help         ← المساعدة وعرض اللوغ
```

### ⚙️ المتطلبات

| الأداة | الاستخدام | مطلوب؟ |
|--------|-----------|---------|
| `git` | عمليات Git الأساسية | ✅ ضروري |
| `gh` | إنشاء المستودعات والتحديث | ✅ ضروري |
| `flutter` | أوامر Flutter | اختياري |
| `docker` | أوامر Docker | اختياري |
| `node / npm` | أوامر Node.js | اختياري |
| `dotnet` | أوامر .NET | اختياري |

---

## 🌐 English Guide

### What is this?

**Developer CLI Toolkit** is a comprehensive Bash script that consolidates your entire development workflow into one simple interface. Instead of memorizing complex git commands, opening Docker Desktop, or searching for Flutter commands — everything becomes `dev <command>`.

### ✨ Key Features

- **🌍 Cross-platform** — Runs natively on macOS, Linux, and Windows (WSL)
- **⚡ Simplified Git** — push, sync, and branch management with short commands
- **📱 Full Flutter** — create, run, build with auto-fix for CocoaPods & Gradle issues
- **🐳 Docker** — complete container and compose management
- **📂 Project Manager** — save projects and jump between them instantly
- **🔔 Notifications** — system notification on completion or failure of long tasks
- **🔄 Self-Update** — updates itself from GitHub with rollback support
- **⚡ Aliases** — create your own custom shortcuts
- **🏥 Doctor** — checks your environment and auto-fixes issues
- **💡 Smart Errors** — on failure, suggests the fix immediately

### 📦 Installation

```bash
# 1. Clone the repository
git clone git@github.com:m199671ms/dotfiles.git ~/scripts

# 2. Add to PATH
echo 'export PATH="$HOME/scripts:$PATH"' >> ~/.zshrc
source ~/.zshrc

# 3. Make executable
chmod +x ~/scripts/dev

# 4. First-time setup (will prompt for your details)
dev info
```

---

## 📋 جميع الأوامر / All Commands

### 📦 المستودعات / Repository

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev create-repo` | إنشاء مستودع GitHub جديد مع .gitignore و README | Create a new GitHub repo with .gitignore & README |

---

### ⚡ Git

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev push "msg"` | add + commit + push بأمر واحد | Stage, commit and push in one command |
| `dev sync` | pull --rebase من الـ remote | Pull with rebase from remote |
| `dev status` | حالة المشروع + آخر 7 commits | Project status + last 7 commits |
| `dev log` | git log بشكل جميل ومنظم | Pretty git log with graph |
| `dev new-branch <name>` | إنشاء branch جديد والتبديل إليه | Create and switch to a new branch |
| `dev switch-branch` | قائمة بالـ branches للتبديل | List branches to switch to |
| `dev merge-clean` | دمج الـ branch الحالي وحذفه | Merge current branch and delete it |
| `dev clean-branches` | حذف كل الـ branches المدمجة | Delete all merged branches |
| `dev undo` | التراجع عن آخر commit (soft reset) | Undo last commit, keep changes staged |

---

### 📂 المشاريع / Projects

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev save-project <name>` | حفظ مسار المشروع الحالي | Save current directory as a project |
| `dev goto <name>` | الانتقال السريع لمشروع + فتح المحرر | Jump to project and open editor |
| `dev projects` | عرض قائمة المشاريع المحفوظة | List all saved projects |
| `dev remove-project <name>` | حذف مشروع من القائمة | Remove a project from the list |

---

### 📱 Flutter

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev flutter-new <name>` | إنشاء مشروع Flutter جديد | Create a new Flutter project |
| `dev flutter-run [name]` | تشغيل مع قائمة الأجهزة | Run with device selection menu |
| `dev flutter-build` | بناء (APK/iOS/Web/Desktop) + إشعار | Build for target platform + notification |
| `dev flutter-test` | تشغيل الاختبارات + إشعار | Run tests + notification |
| `dev flutter-upgrade` | ترقية Flutter و packages | Upgrade Flutter and packages |
| `dev clean` | flutter clean | Clean build artifacts |

> **ملاحظة / Note:** `flutter-run` يصلح مشاكل CocoaPods وGradle تلقائياً حتى 2 محاولات
> Auto-fixes CocoaPods & Gradle issues with up to 2 retry attempts

---

### 🐳 Docker

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev docker-build <name>` | بناء Docker image + إشعار | Build Docker image + notification |
| `dev docker-run <name>` | تشغيل container مع port mapping | Run container with port mapping |
| `dev docker-list` | عرض كل الـ images والـ containers | List all images and containers |
| `dev docker-stop` | إيقاف جميع الـ containers | Stop all running containers |
| `dev docker-clean` | تنظيف Docker (containers + images) | Clean Docker system |
| `dev compose-up` | docker compose up -d | Start compose services |
| `dev compose-down` | docker compose down | Stop compose services |

---

### 🟢 Node.js / Vue

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev npm-install` | npm install | Install dependencies |
| `dev npm-run <script>` | npm run \<script\> | Run npm script |
| `dev npm-build` | npm run build + إشعار | Build project + notification |
| `dev vue-new <name>` | إنشاء مشروع Vue جديد | Create a new Vue project |

---

### 💜 .NET

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev dotnet-new <name>` | إنشاء مشروع .NET (console/webapi/mvc...) | Create new .NET project |
| `dev dotnet-run` | تشغيل المشروع | Run the project |
| `dev dotnet-build` | بناء + إشعار | Build + notification |
| `dev dotnet-test` | تشغيل الاختبارات + إشعار | Run tests + notification |

---

### 🌐 Web

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev web-serve [port]` | تشغيل local server (افتراضي: 3000) | Start local server (default: 3000) |

---

### 🏥 Doctor

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev doctor` | فحص كامل لبيئة التطوير | Full environment health check |
| `dev doctor --fix` | فحص + إصلاح تلقائي | Check and auto-fix issues |

يفحص / Checks: Git · GitHub CLI · SSH Keys · Flutter · CocoaPods · Android SDK · Docker · Node.js · .NET · مساحة القرص / Disk space

---

### 🔧 أدوات أخرى / Other Tools

| الأمر | الوصف | Description |
|-------|-------|-------------|
| `dev ssh-check` | إعداد SSH keys (personal/company) | Setup SSH keys |
| `dev config` | تعديل الإعدادات | Edit configuration |
| `dev info` | معلومات البيئة والأدوات المثبتة | Show environment info |
| `dev logs` | سجل النشاط مع إحصائيات | Activity log with stats |
| `dev update` | تحديث السكريبت من GitHub | Update script from GitHub |
| `dev rollback` | الرجوع لإصدار سابق | Rollback to a previous version |
| `dev help` | عرض قائمة الأوامر | Show all commands |

---

### ⚡ Aliases — الاختصارات المخصصة

```bash
# إضافة اختصار / Add alias
dev alias-add pb push

# الآن يمكنك استخدام / Now you can use:
dev pb "fix login bug"

# عرض الاختصارات / List aliases
dev alias-list

# حذف اختصار / Remove alias
dev alias-remove pb
```

---

## 💡 أمثلة سريعة / Quick Examples

```bash
# إنشاء مستودع GitHub وربطه
dev create-repo

# رفع التعديلات
dev push "fix: resolve login issue"

# بناء APK وانتظر الإشعار
dev flutter-build

# حفظ موقعك الحالي والرجوع إليه لاحقاً
dev save-project myapp
dev goto myapp

# فحص وإصلاح البيئة
dev doctor --fix
```

---

## 🔔 نظام الإشعارات / Notification System

الأوامر الطويلة تُرسل إشعار نظام عند الانتهاء:

```
✅ Flutter Build APK — اكتمل في 1m 23s
❌ Docker Build — فشل بعد 45s
```

عند الفشل يظهر اقتراح تلقائي للحل حسب نوع الخطأ.

On failure, a smart suggestion is shown based on the error context.

---

## 🗒️ اللوغ / Activity Log

```bash
dev logs
# يعرض:
# - آخر 30 حدث ملوّن (نجاح / فشل)
# - عدد العمليات الناجحة والفاشلة
# - حجم الملف وعدد الأسطر
# اللوغ يُدار تلقائياً (حد أقصى 1000 سطر)
```

---

## 🤝 المساهمة / Contributing

```bash
# تعديل السكريبت
dev update   # سيرفع تعديلاتك المحلية ثم يسحب الأحدث من GitHub
dev rollback # إذا حدث خطأ، ارجع لإصدار سابق
```

---

<div align="center">

صُنع بـ ❤️ · Made with ❤️

</div>