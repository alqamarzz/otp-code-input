# MetalForge Animated OTP Input

A fluid, Apple/MetalForge-inspired **6-Digit OTP / Verification Code Input** component built with pure HTML, modern CSS, and vanilla JavaScript. Features micro-interactions, custom spring motion curves, and verification status morphing transitions.

Inspired by [MetalForge](https://metalforge.xyz) by [@sucodeee](https://x.com/sucodeee).

---

## ✨ Features

- **Fluid Sliding Active Indicator**: A dark ring that glides smoothly across the slot track, morphing its corner curvature (`30px 18px 18px 30px` on ends, `18px` in the middle) to adapt to the capsule outline.
- **Micro-Spring Pop-Up**: Each digit typed pops upward from the bottom (`translateY(22px)` to `-3px` overshoot to center) with Apple-tuned spring physics. Existing digits remain stationary.
- **Morphing Verification Pill**:
  - Automatically collapses the 6-slot capsule into a compact status pill on completion.
  - Displays a clean spinner with `Verifying` state.
  - Transitions into a green pill (`#27C858`) with a reflective diagonal sheen animation and a pop-in checkmark (`✓ Verified`).
- **Sequential Drop Rejection**:
  - Invalid codes trigger a horizontal spring shake and pale crimson flush (`#FEE7EA`).
  - Digits drop downward and dissolve sequentially from right to left (Slot 5 → 0) with a motion-blur fade.
- **Universal Input Handling**:
  - Full clipboard paste support (`Ctrl+V` / `Cmd+V`).
  - Mobile-ready with `inputmode="numeric"` and `autocomplete="one-time-code"`.
  - Zero external libraries or framework dependencies — copy and paste directly into any project.

---

## 🚀 Live Demo & Preview

To run the component locally:

```bash
# Clone the repository
git clone https://github.com/alqamarzz/otp-code-input.git
cd otp-code-input

# Serve locally
python -m http.server 5500
```

Open [http://localhost:5500](http://localhost:5500) in your browser.

> **Default Codes for Testing**:
> - Success: `123456` *(triggers capsule shrink, spinner, and green Verified sheen)*
> - Any other 6-digit code *(triggers red flush, shake, and right-to-left drop-dissolve reject animation)*

---

## 🛠️ Customization

All design tokens are structured as CSS custom properties at the top of the stylesheet:

```css
:root {
  --canvas-bg: #F5F6F0;       /* Page background */
  --capsule-bg: #FFFFFF;      /* Outer pill surface */
  --slot-bg: #ECEFE8;         /* Slot idle background */
  --slot-err-bg: #FEE7EA;     /* Slot error tint */
  --text-color: #141414;      /* Active text & cursor */
  --text-err-color: #E5354C;  /* Error digit color */
  --active-border: #141414;   /* Gliding indicator border */
  --border-thickness: 3.5px;  /* Indicator ring stroke */
}
```

---

## 📄 License

MIT License © 2026 [alqamarzz](https://github.com/alqamarzz)
