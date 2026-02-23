#!/bin/bash
# WinLiter-L Project Core Script
# Designed for Linux Mint - Open Source

echo "Initializing WinLiter-L Container..."

# 1. إنشاء مجلد الحاوية المعزول (نفس فكرة الـ Container في الموبايل)
CONTAINER_PATH="$HOME/WinLiter_Containers/Default_PC"
mkdir -p "$CONTAINER_PATH"

# 2. ضبط إعدادات Wine لتعمل داخل هذا المجلد فقط
export WINEPREFIX="$CONTAINER_PATH"
export WINEARCH=win32

# 3. التأكد من وجود مكتبات التشغيل الأساسية
echo "Checking for Wine and Core dependencies..."
sudo apt update && sudo apt install wine64 wine32 -y

# 4. تشغيل واجهة إعدادات الحاوية
echo "Container Ready. Opening Config..."
winecfg
