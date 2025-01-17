# Packet Listener

- Bu yazılımı ve kullanımı kolay bir Paket Dinleyici örneğidir. MITM ile bağlandığımız bilgisayarın gönderdiği http paketlerini incelememize olanak sağlar.
- Bu uygulama scapy-http kullanılarak yazılmıştır ve scapy-http şu anda python 3.13 sürümünde çalışmadığı 3.9 sürümünde çalıştırmanız gerekecek. Bunu terminal üzerinde sanal bir şekilde nasıl yapacağınızı aşağıda anlatacağım

# Özellikler
- Ağımızdaki bilgisayarın gönderdiği http paketlerini yakalar.
- Kullanımı ve yazımı kolaydır

# Nasıl Kullanılır
- Sadece Programı Çalıştırmanız yeterlidir. Terminal üzerinde raporlar gelecektir.


# Python 3.9 için Linux terminalinde sanal ortam olarak çalıştırmak
- Öncelikle python 3.9 sürümünü python internet sitesinden tar dosyası olarak indiriyoruz.
- indirilen dosyanın dizinine giderek dosyayı çıkartıyoruz ve python derlemek için gerekli olan paketleri yüklüyoruz.
   ```bash
   tar -xvf Python3.9.12.tgz
   cd Python3.9.12.tgz
   
   sudo apt update
   sudo apt install -y build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev curl libbz2-dev
   
   ./configure --enable-optimizations
   make -j$(nproc)
   
   sudo make altinstall
- Kurulumun doğru tamamlandığından emin olmak için
   ```bash
   python3.9 --version

- Daha sonra Python 3.9 u sanal bir ortamda kullanmak için uygulamamızın dizinine geliyoruz.
   ```bash
   python3.9 -m venv myenv
   source myenv/bin/activate
   pip install scapy scapy-http
   pip install --upgrade scapy==2.4.5 scapy-http
   python3.9 packet_listener.py

- Bu uygulama yalnızca eğitim amaçlıdır. İzinsiz her türlü kullanım kesinlikle yasaktır.
