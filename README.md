# 📛 TorrentBD Seedbonus Exploit Bug Report

## 🐛 Bug Summary

A bug has been discovered in **TorrentBD**, a private torrent tracker site, that allows users to **gain seedbonus points without successfully uploading any torrent**.

---

## 🔁 Reproduction Steps

Any authenticated user can reproduce this issue easily by following the steps below:

1. **Upload a pre-existing torrent** (i.e., one already present on TorrentBD).
2. The system will return an **upload error** (as expected).
3. **Refresh the page** (without navigating away).
4. The same error will reappear **after each refresh**.
5. Now, check your **seedbonus score** — you'll notice that **it increases after each refresh**, despite no successful upload.

---

## 💡 Expected Behavior

Seedbonus points should only be awarded **after a successful upload**. Repeated refreshes on an error page should **not grant any bonus**.

---

## ⚠️ Actual Behavior

Each refresh of the error page **incorrectly awards seedbonus points**, allowing users to exploit this and gain unfair advantages.

---

## 🎯 Impact

- Users can **farm seedbonus points** without contributing any actual content.
- This creates an **imbalance** in the seedbonus system and **rewards abuse**.
- Long-term exploitation could **disrupt the integrity** of the tracker ecosystem.

---

## 🛠️ Suggested Fix

Ensure that:
- Seedbonus increments are tied only to **successful uploads**.
- Error pages **do not trigger backend point updates**.
- Implement **cooldowns or CSRF protections** to avoid abuse through repeated requests.

---

## 🙏 Acknowledgements

Thanks to the TorrentBD community and developers. This report is made in good faith to help improve the platform’s fairness and functionality.

