# Project-Spectre-C2
By Ghost C2 Control Panel
# Project Spectre: A Modern C2 Framework for Red Team Operations

**Author:** Oğulcan Erarslan (ByGhost)  
**Official Website:** [https://byghost.tr](https://byghost.tr)  
**Status:** Operational Prototype v1.2 (Source code is classified for OPSEC reasons)

---

## (EN) English Manifesto

### 1. Mission Doctrine

Project Spectre is not merely a tool; it is a complete weapon system designed for authorized **Red Team engagements** and **advanced penetration tests**. Conceived with a "stealth-first" philosophy, its core architecture prioritizes **evasion, operational flexibility, and deep system telemetry** over brute force. It was engineered to simulate the Tactics, Techniques, and Procedures (TTPs) of sophisticated Advanced Persistent Threats (APTs) in a controlled, ethical environment.

### 2. Live Operational Demonstration

The framework features a real-time, reactive web interface built with React, capable of managing multiple implants simultaneously via a secure WebSocket channel. The following demonstration showcases the system's core capabilities: live agent connection, deep system reconnaissance (`sysinfo`), and instant surveillance (`screenshot`).

![Ghost C2 Operational Demo]
<a href="https://hizliresim.com/qn1n4i2"><img src="https://i.hizliresim.com/qn1n4i2.png" alt="ff"></a>


*This demo highlights the framework's ability to establish a covert channel, fingerprint the target system's hardware and security posture, and execute surveillance commands in real-time.*

### 3. Architectural Pillars & Core Capabilities

Spectre is built on a foundation of modern technologies and advanced evasion techniques, setting it apart from standard Remote Access Trojans (RATs).

*   **Stealth & Evasion (The Ghost Protocol):**
    *   **Malleable C2 Profiles:** Network traffic is cloaked to impersonate legitimate services (DNS, HTTPS, common web APIs), bypassing signature-based Intrusion Detection Systems (IDS) and network analysis tools.
    *   **In-Memory Execution:** Payloads and modules are executed directly in memory to minimize disk footprint, effectively blinding filesystem-based antivirus (AV) and endpoint detection (EDR) solutions.
    *   **Anti-Analysis & Sandbox Detection:** The implant actively detects and refuses to run in known analysis environments (VMs, debuggers), significantly delaying reverse engineering and signature creation.

*   **Modularity & Control (The Architect's Toolkit):**
    *   **Reactive Frontend (React & TypeScript):** A clean, multi-agent dashboard provides unparalleled situational awareness and intuitive control over multiple compromised assets.
    *   **Asynchronous Backend (Node.js & WebSocket):** A robust API server manages agent communications and tasking through a custom, end-to-end encrypted (E2EE) protocol, ensuring secure and reliable command execution.
    *   **Dynamic Payload Loading:** Only a minimalistic stager is initially deployed. All other modules (keylogger, file browser, surveillance tools) are dynamically and securely loaded post-exploitation, keeping the initial implant small and difficult to detect.

*   **Deep Telemetry & Exfiltration:**
    *   The `sysinfo` command provides a comprehensive system profile, including detailed hardware specifications (CPU, GPU, BIOS), OS version, running processes, network configuration, and security posture (Firewall/AV status).
    *   The framework includes modules for exfiltrating sensitive data such as browser tokens, clipboard contents, and credentials **for authorized testing purposes only**, demonstrating the potential impact of a breach.

### 4. Ethical Use Case & Non-Disclosure Mandate

This framework was developed **exclusively** for legal, authorized, and ethical purposes, such as professional Red Teaming, corporate security assessments, and academic research. Its capabilities are meant to proactively identify and remediate security vulnerabilities by simulating real-world attack scenarios.

**The source code for Project Spectre is and will remain classified. This is a non-negotiable operational security (OPSEC) measure to prevent its misuse by malicious actors.**

---
---

## (TR) Türkçe Manifesto

### 1. Misyon Doktrini

Project Spectre, sadece bir araç değil; yetkilendirilmiş **Red Team operasyonları** ve **ileri seviye sızma testleri** için tasarlanmış bütüncül bir silah sistemidir. "Önce gizlilik" felsefesiyle tasarlanan sistemin temel mimarisi, kaba kuvvet yerine **tespitten kaçınma (evasion), operasyonel esneklik ve derin sistem telemetrisini** önceliklendirir. Kontrollü ve etik bir ortamda, sofistike Gelişmiş Kalıcı Tehditlerin (APT) Taktik, Teknik ve Prosedürlerini (TTP'ler) simüle etmek üzere geliştirilmiştir.

### 2. Canlı Operasyonel Gösterim

Sistem, güvenli bir WebSocket kanalı üzerinden birden fazla implantı (ajan) eş zamanlı olarak yönetebilen, React ile inşa edilmiş gerçek zamanlı ve reaktif bir web arayüzüne sahiptir. Aşağıdaki gösterim, sistemin temel yeteneklerini sergilemektedir: canlı ajan bağlantısı, `sysinfo` ile derinlemesine sistem keşfi ve `screenshot` ile anlık gözetim.

![Ghost C2 Operasyonel Demosu]
<a href="https://hizliresim.com/1ok2656"><img src="https://i.hizliresim.com/1ok2656.png" alt="ff"></a>

*Bu demo, sistemin gizli bir kanal kurma, hedef sistemin donanımını ve güvenlik duruşunu parmak iziyle tanıma ve gözetim komutlarını gerçek zamanlı olarak yürütme yeteneğini vurgulamaktadır.*

### 3. Mimarinin Temel Dayanakları ve Ana Yetenekler

Spectre, modern teknolojiler ve gelişmiş kaçınma teknikleri üzerine kurulmuştur, bu da onu standart Uzaktan Erişim Trojanlarından (RAT) ayırır.

*   **Gizlilik & Tespitten Kaçınma (Hayalet Protokolü):**
    *   **Değişken C2 Profilleri:** Ağ trafiği, DNS, HTTPS veya yaygın web API'leri gibi meşru servisleri taklit edecek şekilde gizlenir, böylece imza tabanlı Saldırı Tespit Sistemlerini (IDS) ve ağ analiz araçlarını atlatır.
    *   **Hafızada Çalışma:** Yükler ve modüller doğrudan bellekte çalıştırılarak disk üzerindeki izler en aza indirilir ve dosya sistemi tabanlı antivirüs (AV) ve uç nokta tespiti (EDR) çözümleri etkili bir şekilde kör edilir.
    *   **Analiz Karşıtı & Sandbox Tespiti:** İmplant, bilinen analiz ortamlarında (sanal makineler, hata ayıklayıcılar) çalışmayı aktif olarak reddederek tersine mühendislik ve imza oluşturma çabalarını önemli ölçüde geciktirir.

*   **Modülerlik & Kontrol (Mimarın Araç Seti):**
    *   **Reaktif Arayüz (React & TypeScript):** Temiz, çoklu ajan destekli bir dashboard, ele geçirilmiş birden fazla varlık üzerinde benzersiz bir durumsal farkındalık ve sezgisel kontrol sağlar.
    *   **Asenkron Arka Uç (Node.js & WebSocket):** Sağlam bir API sunucusu, özel ve uçtan uca şifreli (E2EE) bir protokol aracılığıyla ajan iletişimini ve görevlendirmeyi yönetir, böylece güvenli ve güvenilir komut yürütmeyi garanti eder.
    *   **Dinamik Yükleme:** Başlangıçta yalnızca minimalist bir stager dağıtılır. Diğer tüm modüller (keylogger, dosya gezgini, gözetim araçları) sömürü sonrası dinamik ve güvenli bir şekilde yüklenerek ilk implantın küçük ve tespit edilmesi zor kalması sağlanır.

*   **Derin Telemetri & Veri Sızdırma:**
    *   `sysinfo` komutu, detaylı donanım özellikleri (CPU, GPU, BIOS), işletim sistemi sürümü, çalışan işlemler, ağ yapılandırması ve güvenlik duruşu (Güvenlik Duvarı/AV durumu) dahil olmak üzere kapsamlı bir sistem profili sunar.
    *   Sistem, bir ihlalin potansiyel etkisini göstermek amacıyla, **yalnızca yetkilendirilmiş test amaçları için**, tarayıcı token'ları, pano içeriği ve kimlik bilgileri gibi hassas verileri sızdırmak için modüller içerir.

### 4. Etik Kullanım ve Gizlilik Zorunluluğu

Bu araç, **sadece** profesyonel Red Teaming, kurumsal güvenlik denetimleri ve akademik araştırmalar gibi yasal, yetkilendirilmiş ve etik amaçlar için geliştirilmiştir. Yetenekleri, gerçek dünya saldırı senaryolarını simüle ederek güvenlik açıklarını proaktif olarak tespit etmeyi ve düzeltmeyi amaçlamaktadır.

**Project Spectre'nin kaynak kodları, kötü niyetli aktörler tarafından kötüye kullanılmasını önlemek amacıyla, müzakere edilemez bir operasyonel güvenlik (OPSEC) tedbiri olarak gizlidir ve gizli kalacaktır.**
