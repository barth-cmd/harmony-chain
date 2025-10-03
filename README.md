# HarmonyChain 🎵

**Decentralized Music Rights & Royalty Distribution Protocol**

HarmonyChain is a **trustless protocol** for transparent music royalty distribution built on **Stacks (Bitcoin L2)**. It leverages **cryptographic audio fingerprinting**, **immutable ownership records**, and **community-governed dispute resolution** to ensure fair and tamper-proof compensation for all music contributors.

Every transaction is secured by Bitcoin’s finality, ensuring **durable, censorship-resistant music rights management** for the creator economy.

---

## 🌐 System Overview

Traditional music royalty systems are plagued by:

* Opaque intermediaries
* Delayed and inaccurate payments
* Disputes over contribution attribution

HarmonyChain solves this by introducing a **self-executing, decentralized, and transparent protocol** that enables:

* **Fair attribution** of contributors with cryptographic audio fingerprinting
* **Automatic proportional royalty distribution** with sub-cent precision
* **Immutable ownership & payment records** on Bitcoin L1 via Stacks
* **Community-driven dispute resolution** by a decentralized expert panel
* **Reputation-based trust layer** for artists, producers, and collaborators

---

## 🏛 Contract Architecture

The protocol is composed of **modular smart contract components**:

### 1. **Track Management**

* Register new tracks with metadata and cryptographic audio hash.
* Add and verify contributors with role-based attribution.
* Lock tracks once contributor percentages sum to **100%**.

### 2. **Royalty Distribution**

* Supports **multi-contributor royalties** (up to 10).
* Earnings are automatically split based on predefined contribution percentages.
* **Platform fee** (default 2.5%) sustains operations.

### 3. **Dispute Resolution**

* Contributors can raise disputes with proposed changes.
* **Expert panel voting** determines outcomes.
* Protocol enforces **minimum votes** and auto-resolution when thresholds are met.

### 4. **User Profiles & Reputation**

* Tracks each user’s reputation, total tracks, and earnings.
* Builds a **trust layer** for long-term collaboration in the creator economy.

---

## 📊 Data Flow

**1. Track Registration**

```
Artist → (register-track) → Track stored with metadata & audio-hash
```

**2. Contributor Attribution**

```
Uploader → (add-contributor) → Contributor & percentage recorded
Uploader → (verify-contribution) → Contributor verified
```

**3. Locking Tracks**

```
When contributions = 100% → (lock-track) → Track finalized & immutable
```

**4. Royalty Distribution**

```
Distributor → (distribute-royalties) → Platform fee deducted
→ Funds split proportionally among contributors
→ Earnings recorded per contributor
```

**5. Dispute Handling**

```
Contributor → (create-dispute) → Dispute stored
Experts → (vote-on-dispute) → Votes tallied
System → (resolve-dispute) → Resolved or rejected
```

---

## ⚙️ Key Features

* **Audio Fingerprinting:** Contributors prove authorship with cryptographic audio hashes.
* **Immutable Records:** Rights and earnings secured by Bitcoin finality.
* **Community-Governed Disputes:** Experts ensure fairness without centralized arbitration.
* **Reputation System:** Incentivizes honest contributions and governance.
* **Flexible Governance:** Contract owner can adjust platform fee and manage expert panel.

---

## 📑 Contract Components

* **`tracks` map** → Stores metadata, ownership, and earnings per track
* **`track-contributors` map** → Records contributors, roles, and percentages
* **`contributor-earnings` map** → Tracks earnings distribution
* **`disputes` map** → Manages dispute lifecycle & voting outcomes
* **`expert-panel` map** → Tracks authorized dispute resolution experts
* **`user-profiles` map** → Stores reputation and track history

---

## 🚀 Deployment & Usage

### Register a Track

```clarity
(register-track "Song Title" "Artist Name" 0x123abc "ipfs://metadata")
```

### Add a Contributor

```clarity
(add-contributor u1 'ST123... "Producer" u3000 0x456def)
```

### Lock a Track

```clarity
(lock-track u1)
```

### Distribute Royalties

```clarity
(distribute-royalties u1 u1000000) ;; 1,000,000 µSTX
```

### Create a Dispute

```clarity
(create-dispute u1 "Dispute Reason" "Proposed Changes")
```

---

## 🛡 Governance & Security

* **Platform Fee:** Adjustable, capped at **10% max**.
* **Expert Panel:** Managed by contract owner for dispute resolution.
* **Immutable Rights:** Once a track is locked, contribution percentages are final.
* **Bitcoin Settlement:** All state changes are anchored to Bitcoin for maximum security.

---

## 🔮 Future Extensions

* **NFT-based rights representation** (per-track rights as transferable tokens).
* **Cross-chain royalty payments** in BTC or stablecoins.
* **AI-assisted audio verification** for contributor authenticity.
* **Marketplace integration** for licensing and sync deals.

---

## 📜 License

MIT License – open for community use, research, and contribution.
