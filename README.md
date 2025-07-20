# Git Öğrenme Rehberi 🎯

Bu repo Git'i öğrenmek için oluşturulmuştur.

## 📚 Öğrenme Planı

### 1. Temel Git Komutları
- [x] `git init` - Repo başlatma ✅ TAMAMLANDI!
- [x] `git status` - Durum kontrolü ✅ TAMAMLANDI!
- [x] `git add` - Dosyaları hazırlama ✅ TAMAMLANDI!
- [ ] `git commit` - Değişiklikleri kaydetme
- [ ] `git log` - Geçmişi görme

### 2. Branch İşlemleri
- [ ] `git branch` - Dal oluşturma
- [ ] `git checkout` - Dal değiştirme
- [ ] `git merge` - Dalları birleştirme

### 3. GitHub İşlemleri
- [ ] `git remote add` - Uzak repo bağlama
- [ ] `git push` - GitHub'a gönderme
- [ ] `git pull` - Değişiklikleri alma

### 4. İleri Seviye (Daha Sonra)
- [ ] `.gitignore` - Dosyaları görmezden gelme
- [ ] `git stash` - Değişiklikleri geçici saklama
- [ ] `git revert` - Commit'i geri alma

---

## 📝 Adım Adım Notlar

### Adım 1: Git Repository Başlatma
```bash
git init
```
**Açıklama:** Bu komut mevcut klasörü Git repository'si haline getirir.

**Ne olur:**
- `.git` adında gizli bir klasör oluşturulur
- Bu klasör Git'in tüm verilerini saklar
- Artık Git komutları çalışmaya başlar

**Örnek:**
```bash
cd /Users/kenanaksoy/Desktop/codebase/gittest
git init
```
**Çıktı:** "Initialized empty Git repository in /Users/.../gittest/.git/"

**💡 İpucu:** Bir klasörde sadece 1 kez `git init` yapılır!

**🎯 VS Code İpucu:** VS Code'da terminal açtığında otomatik olarak workspace klasöründe açılır. `cd` ile uğraşmana gerek yok!

**Kontrol komutu:**
```bash
pwd  # Hangi klasördesin gösterir
ls -la  # .git klasörünü görmek için
```

### 🎯 Git Init Başarılı!
**Tebrikler!** Git repository'nizi başarıyla oluşturdunuz. Artık `.git` klasörü mevcut ve Git komutları çalışacak.

---

### Sırada Ne Var? `git status` öğrenelim! 👇

### Adım 2: Git Status - Durum Kontrolü
```bash
git status
```
**Açıklama:** Projenin mevcut durumunu gösterir.

**Ne gösterir:**
- Hangi branch'desin (main)
- Kaç commit var (henüz yok)
- Hangi dosyalar **untracked** (izlenmiyor)
- Hangi dosyalar **staged** (commit için hazır)

**🔍 "Untracked Files" Nedir?**
- **Untracked** = Git henüz bu dosyaları tanımıyor
- **Tracked** = Git bu dosyaları izliyor ve değişiklikleri takip ediyor
- Git sana "Use `git add` to track" diyor

**Örnek Çıktı:**
```
On branch main
No commits yet
Untracked files:
  README.md
  test.text
```

**💡 Mantık:** Git yeni dosyaları otomatik olarak takip etmez. Sen söylemen gerekir!

---

### Adım 3: Git Add - Dosyaları Hazırlama
```bash
git add README.md
```
**Açıklama:** Dosyayı "staging area"ya (sahne alanı) ekler. Commit edilmeye hazırlar.

**🎯 Git Add Başarılı!**
- README.md artık **yeşil** renkte = Commit için hazır!
- test.text hâlâ **kırmızı** renkte = Henüz eklenmemiş

**🎨 Git'in Renk Sistemi:**
- **🟢 YEŞİL:** "Changes to be committed" (Commit edilmeye hazır)
- **🔴 KIRMIZI:** "Untracked files" (Henüz takip edilmiyor)

**💡 Staging Area Nedir?**
Commit edilecek dosyaların bekletildiği alan. "Sahne" gibi düşün!

**Diğer dosyayı da ekle:**
```bash
git add test.text
git status  # İkisi de yeşil olacak!
```

**🚨 Önemli Durum Tespit Edildi!**
Git status çıktında hem **yeşil** hem **kırmızı** README.md var! Bu normal!

**🔍 Ne Oluyor:**
- README.md **eski hali** → Commit için hazır (yeşil)  
- README.md **yeni değişiklikler** → Henüz eklenmemiş (kırmızı)

**💡 Çözüm:**
```bash
git add README.md  # Yeni değişiklikleri de ekle
git status         # Artık sadece yeşil olacak
```

Bu Git'in **staged vs working directory** farkıdır. Çok önemli kavram!

---

### 🎯 Git Add Başarılı!
Her iki dosya da artık commit için hazır (yeşil)!

**🤔 Terminal vs VS Code Git UI:**

**Terminal Git:**
- ➕ Daha fazla kontrol
- ➖ Her değişiklikten sonra `git add` gerekli
- ➖ Komutları manuel yazmak lazım

**VS Code Git UI (Sol Panel):**
- ➕ Otomatik değişiklik takibi
- ➕ + butonuyla kolay stage
- ➕ Görsel olarak daha kolay
- ➕ Yeni başlayanlar için ideal

**💡 Sonuç:** VS Code UI gerçekten daha kolay! Terminal öğrenmek yine önemli çünkü her yerde çalışır.

---

### Sıradaki Adım: İlk Commit! 🚀
