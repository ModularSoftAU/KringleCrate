# KringleCrate Player Guide

## Getting Started
- **Opt-in:** Join the event with `/kc join`. Joining is blocked during the redemption window to keep pairings fair.
- **Wishlist setup:** After joining, your wishlist is initialized automatically. Use it to hint at the gifts you want.
- **Calendar:** Key dates are configured by the server admins. You can always ask staff for the configured reveal and redemption dates.

## Secret Santa Workflow
1. **Join the event** using `/kc join`.
2. **Build your wishlist** with `/kc wishlist add <item description>` and review it with `/kc wishlist`.
3. **Reveal your recipient** on or after the reveal date using `/kc reveal` (admins with `kringlecrate.override` can reveal early).
4. **Send gifts** after the reveal date and before the redemption window opens:
   - Hold an item in your main hand and run `/kc submit` to send it to your assigned recipient.
   - If Vault is installed, send money with `/kc submit currency <amount>`; the funds will be withdrawn immediately.
5. **Redeem gifts** during the redemption period with `/kc redeem`.

## Wishlist Commands
- `/kc wishlist` or `/kc wishlist view` — Show your current wishlist.
- `/kc wishlist add <item description>` — Add a new wishlist entry. Duplicate or blank entries are rejected.
- `/kc wishlist remove <item description>` — Remove an entry that matches your description (case-insensitive).

## Gifting Rules and Tips
- You must wait until the reveal date to submit gifts. Gifts cannot be submitted once the redemption window begins.
- Item gifts are removed from your hand when submitted. All item metadata (enchantments, lore, names) is preserved.
- Currency gifts require Vault and a compatible economy plugin; ensure you have sufficient balance before sending.
- If you are told you have no assigned recipient, contact an admin—assignments require at least two participants.

## Redeeming Gifts
- Redemption only works inside the configured redemption window.
- Have enough empty inventory slots for all item gifts; the plugin will block redemption if space is insufficient.
- Currency gifts (when available) are deposited directly into your balance during redemption.

## Troubleshooting
- **"You are not part of the Secret Santa event"** — Run `/kc join` first.
- **"Not enough participants to assign a recipient"** — Wait for more players to join.
- **"You don't have enough inventory space"** — Clear slots before redeeming.
- **Economy messages** — If currency options are unavailable, ask an admin to check the Vault setup.
