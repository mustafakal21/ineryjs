# ineryjs
# Inery Json RPC 4.Görev
Inery Blockchain'de JSON RPC'yi çağırmak için örnek kod

## 🟢Bilgiler

JSON RPC Örnek kodu örnek dizinde mevcuttur, [example](https://github.com/mustafakal21/ineryjs/blob/master/example/) değiştirmeyi deneyebilir ve nasıl çalıştığını anlayabilirsiniz, ayrıca kodunuzu çalıştırabilmek ve değerli sözleşme işlevini çağırabilmek için Hesabınızda Değerli Akıllı Sözleşmeye (Görev 3) sahip olmanız gerekir.


## 1) Başlayın
Eski Nodejs kaldırın
<br>

```shell
sudo apt-get remove nodejs
```

Curl'ü yükleyin

```shell
sudo apt-get install curl
```

Curl'ü yükleyin

```shell
    curl -fsSL https://deb.nodesource.com/setup_19.x | sudo -E bash - &&\
    sudo apt-get install -y nodejs
```

     
## 2) NPM kurulumu

```shell
sudo apt install npm
```



## 3) Kurulum

* Repoyu klonlayın

   ```
   git clone https://github.com/mustafakal21/ineryjs.git
   ```

* Dizine Girin

   ```
   cd ineryjs
   ```

* NPM Paket kurun

   ```
   npm install
   ```

* Aşağıdaki Kod ile env-sample dosyasının ismini .env yapın 

   ```
   cp .env-sample .env
   ```

*  ```.env``` bilgileriniz düzenleyin

  ```
   nano .env
   ```

Burada açılan pencerede <br><br>

Aşağıdaki Bilgileri inery testnet Dashboard kısmında bulabilirsiniz.<br><br>

INERY_ACCOUNT="HESAP ADINIZ" <br>
PRIVATE_KEY="KEYİNİZ"<br>
NODE_URL="http://NODEİPADRESİ:8888" 
<br><br>

ctrl +X  Yes diyip çıkıyoruz.


## 4) 8888 port açma 

RPC Örneği Çalıştır

```
sudo ufw allow 8888
```

<br>

## 5) Çalıştırma

```
npm run rpc-example
```




<br><br>
## 🟢 Hata Çözümleri

Serialization time limit 15000us exceeded<br>


* config.ini dosyanda max-transaction-time değerini 15000 olarak değiştir<br>

```
nano ./inery-node/inery.setup/master.node/blockchain/config/config.ini
```

<img src="https://camo.githubusercontent.com/6036fa176fe713bfa7e8151aef13b77710b589c33dff2f7ae459d2b8785e0efc/68747470733a2f2f736e6970626f6172642e696f2f61306472474e2e6a7067" width="550">

<br><br>

* connect ECONNREFUSED<br>


```
sudo ufw allow 8888
```

<img src="https://camo.githubusercontent.com/d7bfd0c198035faa303e9a8b5714668384dd1d00a681b444718757b7a4872365/68747470733a2f2f736e6970626f6172642e696f2f5567534d48322e6a7067" width="550">


<br><br>

* missing create.issuer ( type=name )<br>
* Bu, hesabınızda Görev 3'te oluşturduğunuz Değerli Akıllı Sözleşme olmadığı anlamına gelir.
* Hesabınızda CRUD Akıllı Sözleşmenizin olup olmadığını kontrol etmek için

```
cline get abi ineryi-hesap-isminiz
```

<img src="https://camo.githubusercontent.com/35161f3c497c316d89925c7d1300ddaa78354daed4b783f615bd1561fd2bdba7/68747470733a2f2f736e6970626f6172642e696f2f615442484c332e6a7067" width="550">

* bu çıktıya sahip olduğunuzdan emin olun<br><br>

<img src="https://camo.githubusercontent.com/107661c26d281a09dcc3495a03f04ab90e90148f506479ad54f2d5df26e82150/68747470733a2f2f736e6970626f6172642e696f2f3076736e4f712e6a7067" width="550">
