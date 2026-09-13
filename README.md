<p align="center">
  <img src="./assets/hero-dark.svg" alt="Wassim Ahabchane — Full-Stack Software Engineer" width="100%">
</p>

<br>

<p align="center">
  <a href="https://github.com/wassimahabchane">
    <img src="https://img.shields.io/badge/GitHub-0B0B0A?style=flat-square&logo=github&logoColor=F4F1E8" />
  </a>
  <a href="https://www.linkedin.com/">
    <img src="https://img.shields.io/badge/LinkedIn-0B0B0A?style=flat-square&logo=linkedin&logoColor=F4F1E8" />
  </a>
  <a href="mailto:your-email@example.com">
    <img src="https://img.shields.io/badge/Email-0B0B0A?style=flat-square&logo=gmail&logoColor=F4F1E8" />
  </a>
</p>

<br>

<img src="./assets/profile-wave.svg" alt="Wassim engineering profile" width="100%">

<br>

## / DBER

I'm currently building **DBER**, a unified transactional engine designed around three marketplace domains:

- **SOUQ** — social group-buy marketplace
- **KHIDMA** — professional services marketplace
- **KRAYA** — rental marketplace

The interesting part isn't the marketplace UI.

It's everything that has to remain correct when reality happens:

```text
duplicate requests
      ↓
concurrency
      ↓
state transitions
      ↓
database constraints
      ↓
transactions
      ↓
audit trail
      ↓
outbox
      ↓
recoverable side effects
