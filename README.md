# 🤖 SimpleChain Testnet Auto Bot

> **Layer Airdrop ID (LYID) Premium Edition**  
> Multi-Wallet | Proxy Support | Daily Automation

🌐 **Website:** https://task.simplechain.com
🔗 **Referral:** Invite code `9v6m0j5bde0`

SimpleChain adalah Institutional OS untuk Real World Assets (RWA) yang raised $15M Seed Round. Bot ini mengautomasi daily check-in, task completion, dan faucet claim di SimpleChain Testnet.

---

## ✨ Fitur

- ✅ **Multi-wallet support** (unlimited)
- ✅ **Proxy rotation** otomatis
- ✅ **Daily check-in** automation
- ✅ **Task completion** (authenticated API with smart task filtering)
- ✅ **Faucet claim** (dengan Turnstile token / 2Captcha auto-solve)
- ✅ **User info & points tracking** dengan rank delta
- ✅ **Daily Report** — completed tasks + points history + rank
- ✅ **Interactive CLI menu** + `--daily` + `--report` flags
- ✅ **Anti-detection** (random delay, proxy rotation)
- ✅ **Smart task handling** — skip on-chain tasks (swap/LP), auto social

---

## 📋 Requirements

- Node.js v18+ ([download](https://nodejs.org))
- ChainBox Wallet (dengan testnet SRW tokens)
- Private key wallet Anda

---

## 🚀 Setup

### 1. Install Dependencies
```bash
cd simplechain-bot
npm install
```

### 2. Configure
Edit `config.json`:
```json
{
    "inviteCode": "9v6m0j5bde0",
    "delay_min": 2000,
    "delay_max": 6000,
    "captcha_provider": "manual",
    "chain": {
        "chainId": 1913,
        "rpc": "https://rpc-c.simplechain.com"
    }
}
```

### 3. Add Wallets
Isi `privateKey.txt` (satu private key per baris):
```
0xabc123...
0xdef456...
0x789ghi...
```

### 4. Add Proxies (Optional, Recommended for Multi-Wallet)
Isi `proxy.txt` (format: `host:port:user:pass`):
```
127.0.0.1:8080:user:pass
192.168.1.1:1080
```

---

## 📖 Usage

```bash
npm start
# atau
node index.js
```

### Menu Options:
| # | Menu | Fungsi |
|---|------|--------|
| 1 | Daily Check-in | Check-in semua wallet |
| 2 | Claim Faucet | Claim testnet tokens (butuh Turnstile) |
| 3 | Complete Tasks | Complete tasks (authenticated, smart filter) |
| 4 | Show User Info | Lihat points, rank & delta |
| 5 | Run All | Check-in + Tasks sekaligus |
| 6 | Run All + Faucet | Full Daily |
| 7 | Show Leaderboard | Top 10 leaderboard |
| 8 | Daily Report | Completed tasks + points history + rank |

### CLI Flags:
```bash
node index.js --daily          # Auto run (checkin + tasks, no menu)
node index.js --daily --faucet # Auto run + faucet claim
node index.js --report         # Daily report only
```

---

## 🔑 Tentang Turnstile / Captcha

Beberapa endpoint SimpleChain memerlukan Cloudflare Turnstile token:
1. **Faucet claim** — selalu butuh
2. **Check-in risk report** — kadang butuh

### Cara Manual (Default):
1. Buka https://task.simplechain.com di browser
2. Buka DevTools (F12) → Network tab
3. Lakukan check-in / faucet manual
4. Cari request ke `checkin/risk-report` atau `walletClaimRecord/save`
5. Copy nilai `turnstileToken` dari payload
6. Paste ke bot saat diminta

---

## ⚙️ Configuration

### config.json

| Field | Default | Description |
|-------|---------|-------------|
| `inviteCode` | `9v6m0j5bde0` | Referral code untuk login |
| `delay_min` | `2000` | Minimum delay antar request (ms) |
| `delay_max` | `6000` | Maximum delay antar request (ms) |
| `retry_count` | `3` | Jumlah retry jika request gagal |
| `retry_delay` | `5000` | Delay antar retry (ms) |
| `claim_tasks` | `true` | Auto-complete API tasks |
| `captcha_provider` | `2captcha` | `manual` atau `2captcha` (auto-solve) |

---

## 📊 SimpleChain Testnet Info

| Info | Detail |
|------|--------|
| Chain ID | 1913 (0x779) |
| RPC | https://rpc-c.simplechain.com |
| Explorer | https://testnet-explorer.simplechain.com |
| Token | SRW (Native) |
| Faucet | https://www.simplechain.com/developer/faucet |
| Task Platform | https://task.simplechain.com |
| DEX | https://dex.simpleflow.finance |

### Token Contracts
| Token | Address |
|-------|---------|
| MARS | 0xFC12Ae35889A4a6D0b1cE94a6675Ef869F6eb207 |
| MERCURY | 0x8c0c42fD298623d035eeFd8b2783c94069610d2B |

---

## ⚠️ Known Limitations

1. **Turnstile**: Faucet dan check-in risk report mendukung auto-solve via 2Captcha API. Set `captcha_api_key` di config.json atau env `CAPTCHA_API_KEY`. Jika kosong, bot fallback ke manual input.

2. **On-chain tasks**: Swap dan LP tasks memerlukan on-chain transactions. Bot ini meng-automasi API task completion, tapi swap/LP harus dilakukan manual di DEX atau dengan script terpisah.

3. **Token login structure**: Response login mungkin berbeda dari ekspektasi. Jika login gagal dengan "Token not found", check response structure dan update `src/auth.js`.

---

## 🔒 Security Notes

- **Private keys** disimpan lokal di `privateKey.txt`. Jangan share file ini!
- **Proxy** recommended untuk multi-wallet untuk menghindari sybil detection
- **Rate limit**: Bot sudah include random delay, jangan set delay terlalu rendah
- **Backup wallet**: Gunakan wallet burner, JANGAN pakai main wallet

---

## 🛒 Pembelian

Script ini adalah **Layer Airdrop Premium Script**.

**Harga:** Rp 65.000  
**DM:** @rmndkyl di Telegram  
**Payment:** DANA / GoPay / USDT (TRC20)

---

## 📞 Support

- Telegram Channel: @layerairdrop
- Discussion: @layerairdropdiskusi
- DM: @rmndkyl
- Discord: discord.gg/layerairdrop

---

## 📜 License

MIT License — Layer Airdrop ID

> Dengan membeli script ini, Anda setuju untuk tidak redistribute. Watermark pembeli tertanam di header setiap file.

---

**Layer Airdrop ID © 2026** | @layerairdrop
