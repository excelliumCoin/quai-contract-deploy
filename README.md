<h1 align="center"> Quai Network Contract Deploy İşlemleri </h1>

> Öncelikle [Gitpod](https://gitpod.io) sitesine gidip free bir üyelik oluşturuyoruz

> [Pelagus](https://pelaguswallet.io/) Cüzdanı kuruyoruz.

> Topluluk kanalları: [Sohbet Kanalımız](https://t.me/0xnull) - [Duyurular ve Gelişmeler](https://t.me/https://t.me/nullchannell)  - [Quai Discord](https://discord.gg/ZDG3Bd44)

<h1 align="center"> Gitpod hesabınıza githubla giriş yapın </h1>

> Github'da bir repo oluşturun,Gitpod yeni bir workspace oluşturun ve oluşturduğunuz reponun linkini yapıştırıp bağlanın.

<h1 align="center"> Kurulumlar </h1>

```console
# Gitpod Terminale sırasıyla

git clone https://github.com/dominant-strategies/hardhat-example.git
cd hardhat-example/Solidity
npm install
npm i @nomicfoundation/hardhat-toolbox
npm i quais
npm i quais-polling
npm i dotenv

# .env dosyası oluşturuyoruz
cp ../.env.dist ../.env
```
## .env Ayarlamalar 
```console

# Bölgeye göre Cüzdanınızın private keyini alıp yapıştırın- Cüzdanınız hangi bölgedeyse

CYPRUS1PK="0x9800000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x00 - 0x1D
CYPRUS2PK="0x9400000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x1E - 0x3A
CYPRUS3PK="0x0200000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x3B - 0x57
PAXOS1PK="0x7100000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x58 - 0x73
PAXOS2PK="0x8500000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x74 - 0x8F
PAXOS3PK="0x0400000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0x90 - 0xAB
HYDRA1PK="0x9100000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0xAC - 0xC7
HYDRA2PK="0x5900000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0xC8 - 0xE3
HYDRA3PK="0xa700000000000000000000000000000000000000000000000000000000000000" # For pubkey starting with 0xE4 - 0xFF

# Chain ID (local: 1337, testnet: 9000, devnet: 12000)
CHAINID="9000"

# RPC endpoints
CYPRUS1URL="https://rpc.cyprus1.colosseum.quaiscan.io"
CYPRUS2URL="https://rpc.cyprus2.colosseum.quaiscan.io"
CYPRUS3URL="https://rpc.cyprus3.colosseum.quaiscan.io"
PAXOS1URL="https://rpc.paxos1.colosseum.quaiscan.io"
PAXOS2URL="https://rpc.paxos2.colosseum.quaiscan.io"
PAXOS3URL="https://rpc.paxos3.colosseum.quaiscan.io"
HYDRA1URL="https://rpc.hydra1.colosseum.quaiscan.io"
HYDRA2URL="https://rpc.hydra2.colosseum.quaiscan.io"
HYDRA3URL="https://rpc.hydra3.colosseum.quaiscan.io"

# SolidtyX standartında NFT Bilgileriniz
QRC721_NAME="TestQRC721" # Name of collection
QRC721_SYMBOL="TQ721" # Collection symbol
QRC721_BASE_URI="ipfs://METADATA_CID/" # Base URI for token metadata (make sure to keep the slash at the end)

# Solidity standartında NFT Bilgileriniz
ERC721_NAME="TestQRC721" # Name of collection
ERC721_SYMBOL="TQ721" # Collection symbol
ERC721_BASE_URI="ipfs://METADATA_CID/" # Base URI for token metadata (make sure to keep the slash at the end)

# SolidtyX standartında Token Bilgileriniz
QRC20_NAME="TestQRC20" # Name of token
QRC20_SYMBOL="TQ20" # Symbol of token
QRC20_INITIALSUPPLY=1000000 # Initial supply of token, will be minted to deployer

# Solidty standartında Token Bilgileriniz
ERC20_NAME="TestQRC20" # Name of token
ERC20_SYMBOL="TQ20" # Symbol of token
ERC20_INITIALSUPPLY=1000000 # Initial supply of token, will be minted to deployer
```


<h1 align="center"> Deploy İşlemi </h1>

```console
npx hardhat compile

```
```console
# Eğer cüzdanınız paos1 ise --network sonuna aşağıdaki gibi paxos1...cyprus1....hydra1 gibi gibi
npx hardhat run scripts/deployERC20.js --network paxos1

# Bu da NFT deploy için
npx hardhat run scripts/deployERC721.js --network hydra2
```
## Böyle bir çıktı alacaksınız işlem tamamdır.
![image](https://tan-select-duck-40.mypinata.cloud/ipfs/QmapqBEFBkr8zPADkaqfhjWHT3vXfeJqSbhmSvLFomzAfP)

