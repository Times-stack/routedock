---
"@routedock/routedock": patch
---

Fix mpp-session provider adapters (Hono and Express) committing an unverified Payment header's signature and payer to session state before mppx verified the credential. Voucher state is now written only from a credential onVerifiedCredential has confirmed mppx actually verified, so a crafted, unverified header can no longer poison the signature or payer a later close or orphan-recovery uses.
