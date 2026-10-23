Clutch Arena (powered by Beast Games) - go live in 4 steps

1. Upload index.html and admin.html to Netlify (drag and drop the whole folder) or Vercel.
   Open the site from the hosted link, not inside a chat app preview, or Supabase will not connect.
2. Supabase project "Clutch Arena": Authentication > Providers > Email > "Confirm email" must be OFF.
3. Supabase > SQL Editor: run these three files ONCE (any order):
     database/admin_leaderboard.sql   (admin panel can save the leaderboard)
     database/my_opponent.sql         (paid players see their opponent's UID in My bookings)
     database/set_payout_upi.sql      (saves the prize UPI ID a player types when booking)
   If one errors, the table or column names differ. Send the table structure and fix the SQL.
   Do NOT re-run the older base setup SQL on the live project.
4. Open the live link. The badge on the home page should say "Live". Register a test account,
   book a slot, scan the UPI QR (beastgames@ibl) and send a test receipt.

Booking form: the player types the game UID, sees it repeated right below, and taps
"This account is mine, confirm". The player also enters their own UPI ID for prize money.

Admin: open admin.html. Menu (3 lines, top LEFT):
  Overview, Payments, Rooms, Daily, Bracket, Leaderboard.
  Payments: mark Paid and UID ok. Prize UPI shows on each card.
  Daily: in "Place and map" write like  Custom room · Erangel  so players see the map name.
  Leaderboard: add match results per team, then press Save.

Custom rooms (online): players make their own room. When two paid players share a slot pair
(slots 1+2, 3+4, ...), each sees the other's UID in My bookings, creates a custom room,
plays, and emails the result. Offline tournaments show venue instructions instead.
(The Rooms tab in admin still works if you ever want to give a Room ID yourself.)
