# Git Öğrenme Rehberi 🎯

Bu repo Git'i öğrenmek için oluşturulmuştur.

## 📚 Öğrenme Planı

### 1. Temel Git Komutları
- [x] `git init` - Repo başlatma ✅ TAMAMLANDI!
- [x] `git status` - Durum kontrolü ✅ TAMAMLANDI!
- [x] `git add` - Dosyaları hazırlama ✅ TAMAMLANDI!
- [x] `git commit` - Değişiklikleri kaydetme ✅ TAMAMLANDI!
- [x] `git log` - Geçmişi görme ✅ TAMAMLANDI!

### 2. Branch İşlemleri
- [x] `git branch` - Dal oluşturma ✅ TAMAMLANDI!
- [x] `git checkout` - Dal değiştirme ✅ TAMAMLANDI!
- [x] `git merge` - Dalları birleştirme ✅ TAMAMLANDI!

### 3. GitHub İşlemleri
- [x] `git remote add` - Uzak repo bağlama ✅ VS CODE İLE TAMAMLANDI!
- [x] `git push` - GitHub'a gönderme ✅ VS CODE İLE TAMAMLANDI!
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

### Adım 4: Git Commit - Değişiklikleri Kaydetme
```bash
git commit -m "İlk commit: README ve test dosyaları eklendi"
```
**Açıklama:** Staged dosyaları kalıcı olarak Git geçmişine kaydeder.

**🎯 Git Commit Başarılı!**
```
[main (root-commit) 18bb47c] İlk commit: README ve test dosyaları eklendi
 2 files changed, 167 insertions(+)
 create mode 100644 README.md
 create mode 100644 test.text
```

**🔍 Çıktı Analizi:**
- `[main (root-commit) 18bb47c]` = Ana branch, ilk commit, ID: 18bb47c
- `2 files changed` = 2 dosya değişti  
- `167 insertions(+)` = 167 satır eklendi
- `create mode 100644` = Yeni dosyalar oluşturuldu

**💡 Commit ID Nedir?**
- Her commit'in benzersiz kimliği
- `18bb47c` = Bu commit'i ayırt etmek için
- Git bu sayede hangi değişikliği takip ediyor

**🏠 Nereye Kaydediliyor?**
- **Lokal .git klasörüne** (kendi bilgisayarında)
- GitHub'a göndermeye gerek yok
- İnternet olmasa da çalışır!

**🎨 Commit Mesajı İpuçları:**
- Kısa ve açık ol: "Ne yaptığını" yaz
- Türkçe veya İngilizce farketmez
- Örnek: "Navbar eklendi", "Bug düzeltildi"

---

### Sıradaki Adım: Commit Geçmişini Görelim! 📚

### Adım 5: Git Log - Commit Geçmişini Görme
```bash
git log
```
**Açıklama:** Tüm commit'lerin geçmişini gösterir.

**🎯 Git Log Başarılı!**
```
commit 18bb47ca4aac4279b5ed3d2618c441f1119afe97 (HEAD -> main)
Author: Kenan <kea.aksoy@gmail.com>
Date:   Mon Jul 21 01:11:32 2025 +0300

    İlk commit: README ve test dosyaları eklendi
```

**🔍 Çıktı Analizi:**
- `commit 18bb47ca4aac...` = Tam commit ID (benzersiz kimlik)
- `(HEAD -> main)` = Şu anda main branch'desin, HEAD burada
- `Author: Kenan` = Kim yaptı (Git config'inden)
- `Date: Mon Jul 21 01:11:32 2025` = Ne zaman yapıldı
- `İlk commit: README ve test dosyaları eklendi` = Commit mesajı

**💡 Önemli Kavramlar:**
- **HEAD** = "Şu anda neredesin?" işaretçisi
- **main** = Ana branch (varsayılan)
- **Commit ID** = Her commit'in parmak izi gibi

**🎨 Git Log Varyasyonları:**
```bash
git log --oneline    # Tek satırda özet
git log -3           # Son 3 commit
git log --graph      # Grafik görünüm
```

---

## 🎊 TEBRİKLER! Git Temellerini ve Branch'leri Öğrendin!

**✅ Tamamladıklarımız:**
1. **git init** - Repository başlattık
2. **git status** - Durumu kontrol ettik  
3. **git add** - Dosyaları sahnelettik
4. **git commit** - Değişiklikleri kaydettik
5. **git log** - Geçmişi gördük
6. **git branch** - Branch oluşturduk
7. **git checkout** - Branch değiştirdik
8. **git merge** - Branch'leri birleştirdik

**🚀 Henüz Öğreneceğimiz:**
- **GitHub İşlemleri** - Bulutta paylaşım
- **İleri Git Teknikleri** - .gitignore, stash, revert

**💡 Şu Ana Kadar Mükemmelsin!** Artık temel Git workflow'unu biliyorsun ve güvenle branch'lerle çalışabilirsin!

---

## 🌐 Bölüm 3: GitHub İşlemleri

### Adım 6: GitHub Repository Oluşturma
**🎯 Hedef:** Local Git repo'muzu GitHub'a bağlayacağız!

**📋 Yapılacaklar:**
1. GitHub'da yeni repository oluştur
2. Local repo'yu GitHub'a bağla (`git remote add`)
3. İlk push yap (`git push`)
4. Değişiklikleri çek (`git pull`)

### GitHub Repository Oluşturma Adımları:
1. **GitHub.com**'a git → Sign in
2. **"New Repository"** butonuna tıkla (yeşil buton)
3. **Repository name:** `gittest` (veya istediğin isim)
4. **Description:** "Git öğrenmek için test repository'si"
5. **Public** seç (herkes görebilsin)
6. ❌ **"Add a README file" tikini KALDIR** (bizde zaten var!)
7. ❌ **".gitignore" ve "license" eklemeyecek**
8. **"Create repository"** butonuna tıkla

**🎯 Repository oluşturulduktan sonra GitHub sana şu komutları gösterecek:**

```bash
git remote add origin https://github.com/USERNAME/gittest.git
git branch -M main
git push -u origin main
```

**🤔 Bu komutlar ne demek? Hemen açıklayayım! 👇**

### Adım 6A: VS Code ile GitHub'a Publish (Kolay Yöntem) ✅
**🎯 Sen bunu yaptın! Tebrikler!**

**📍 VS Code Source Control Panel'den:**
1. **Sol panelde Source Control** simgesine tıkla (Ctrl+Shift+G)
2. **"Publish to GitHub"** butonuna tıkla
3. Repository adını yaz (`gittest`)
4. **Public/Private** seç
5. **"Publish"** tıkla
6. ✨ **İşte bu kadar!** VS Code her şeyi otomatik halleder!

**🎯 Ne Oldu?**
- GitHub'da repository oluşturuldu
- Local repo GitHub'a bağlandı (`git remote add origin`)
- Tüm commit'ler GitHub'a gönderildi (`git push`)
- Artık GitHub'da kodların görünür!

**➕ VS Code GitHub Entegrasyonunun Avantajları:**
- 🚀 **Tek tık** ile GitHub'a publish
- 🔗 **Otomatik remote** bağlantısı
- 📤 **Otomatik push** işlemi
- 🔐 **GitHub Authentication** otomatik
- 💻 **GitHub hesabı** entegrasyonu
- ⚡ **En hızlı** yöntem!

**💡 Artık yapabileceklerin:**
- VS Code'da değişiklik yap → **Commit** → **Sync/Push**
- GitHub'da repository'ni görebilirsin
- Başkaları kodunu görebilir/fork edebilir

---

### Adım 6B: Terminal Yöntemi (Öğrenme Amaçlı)
**Bu bilgi için - VS Code kullanmışsan gerek yok!**

**🎯 Terminal Komutları Açıklaması:**

```bash
# 1. GitHub repo'ya bağlan
git remote add origin https://github.com/USERNAME/gittest.git
```
**Ne demek:** `origin` adında bir "remote" (uzak repo) tanımla

```bash  
# 2. Ana branch'i "main" olarak ayarla (zaten öyle)
git branch -M main
```
**Ne demek:** Branch adını `main` yap (GitHub standardı)

```bash
# 3. İlk kez GitHub'a gönder
git push -u origin main
```
**Ne demek:** 
- `main` branch'ini `origin`'e (GitHub'a) gönder
- `-u` = "upstream" ayarla (gelecekte sadece `git push` yeterli olsun)

**🔍 Sonuç:** VS Code'un yaptığı işlemler bunlar!

---

### Adım 7: Git Pull - Değişiklikleri Alma
**🎯 Hedef:** GitHub'dan değişiklikleri local'e çekmeyi öğren!

**🤔 Git Pull ne zaman lazım?**
- Başka birileri kodu değiştirip GitHub'a gönderirse
- Sen başka bilgisayardan push yaparsan  
- GitHub'da web editörle değişiklik yaparsan
- Takım çalışmasında sürekli lazım!

**💻 Pratik Yapalım: GitHub'da dosya düzenle!**

1. **GitHub.com**'a git → Repository'ne gir
2. **README.md**'ye tıkla
3. **Kalem simgesi** (Edit) tıkla  
4. Bir satır ekle: `# GitHub'dan düzenlendi! 🌐`
5. **"Commit changes"** tıkla
6. Commit mesajı yaz: `README GitHub'da düzenlendi`

**Şimdi local'e çekmeyi deneyelim! 👇**
