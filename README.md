# Voting DApp Project
## Thành Quả
- **Voting FE**: `https://nguyen-voting-dapp.vercel.app/`

## 1. Cấu trúc dự án

- **contracts/**: Chứa file smart contract (ví dụ: `Voting.sol`)
- **scripts/**: Chứa các script để deploy, verify, và tương tác với smart contract (thêm candidate, vote, v.v.)
- **voting-dapp-frontend/**: Source code React cho frontend ứng dụng

---

## 2. Viết Smart Contract

- Viết contract trong thư mục `contracts/`, ví dụ:  
  ```
  contracts/Voting.sol
  ```
- Sử dụng OpenZeppelin nếu cần (Ownable, v.v.):  
  ```
  npm install @openzeppelin/contracts
  ```

---

## 3. Deploy Smart Contract

- Deploy lên Sepolia testnet:
  ```
  npx hardhat run scripts/deploy.js --network sepolia
  ```
- Sau khi deploy, lưu lại địa chỉ contract để dùng cho frontend và các script khác.

---

## 4. Verify Smart Contract

- Verify contract trên Etherscan:
  ```
  npx hardhat verify --network sepolia ĐỊA_CHỈ_CONTRACT "constructor arguments nếu có"
  ```
  - Thay `ĐỊA_CHỈ_CONTRACT` bằng địa chỉ contract bạn vừa deploy.
  - Nếu contract có constructor arguments thì truyền vào sau địa chỉ.

---

## 5. Tương tác với Smart Contract bằng Script

- Thêm candidate:
  ```
  node scripts/addCandidate.js
  ```
- Hoặc các script khác như vote, lấy danh sách candidate, v.v.

---

## 6. Voting DApp Frontend

### Cài đặt dependencies

```bash
cd voting-dapp-frontend
npm install
```

### Chạy local

```bash
npm run dev
```

### Deploy lên Vercel

1. Đăng nhập [Vercel](https://vercel.com/) và kết nối với repo GitHub của bạn (nếu có).
2. Chọn project `voting-dapp-frontend` để deploy.
3. Thiết lập biến môi trường (nếu cần) trong dashboard Vercel.
4. Nhấn "Deploy".

Hoặc deploy thủ công:
- Push code lên GitHub.
- Import repo vào Vercel.
- Chọn framework là **Vite** hoặc **React** (tùy bạn dùng gì).
- Deploy.

---

## 7. Một số lệnh Hardhat hữu ích

```bash
npx hardhat help
npx hardhat test
REPORT_GAS=true npx hardhat test
npx hardhat node
npx hardhat ignition deploy ./ignition/modules/Lock.js
```

---

## 8. Liên hệ

- Nếu gặp lỗi, kiểm tra lại các biến môi trường trong file `.env` (RPC URL, PRIVATE_KEY, SMART_CONTRACT_ADDRESS, v.v.)
- Đảm bảo đã cài đặt đúng các dependencies cho cả backend và frontend.
