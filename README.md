# UNIXA Closet — clickable prototype

## HOW TO OPEN
  Double-click index.html (any modern browser). No install, no server, no backend.
  Only Google Fonts needs internet; everything else is local. Keep the "a" folder next to index.html (photos, logo, guide images).

## WHAT IT IS
  A front-end-only UX/IA prototype of UNIXA as a student-to-student CLOTHING marketplace
  (Thai/English, light/dark, desktop + mobile). All data is mock. It is a reference for the
  redesign, not production code. Port the ideas into the real Next.js app; do not copy this file in.

## HOW TO LOOK AROUND
  - Bottom of the left sidebar: "Prototype - <role>" menu. Switch Guest / Buyer / Seller, reset the demo data,
    and open "Redesign notes". (On phone: Menu button in the bottom bar.)
  - "Redesign notes" page (also linked in the footer) = the part for you:
      * old UI term -> new term -> backend name table
      * which clothing fields already exist in the backend vs which need adding
      * every removed global UI element, with real file:line references in the current repo
      * real bugs found while reading the code (e.g. CartPage.jsx:1190 compares the coin balance object to a number;
        profileCard.jsx shows the public student ID; formPostItem.jsx defaults condition to "new";
        privacy policy still says "SPU BUS Marketplace")
  - Language / theme toggles are in the top bar.

CODE LAYOUT (single file, vanilla JS, no framework)
  One <style> (design tokens + components), one <script> containing, in order: art (drawn garment SVGs),
  data (45 mock listings, sellers, orders), i18n DICT (TH/EN, keys like [th, en]), then the app modules
  (core/router, shell, cards, home+browse, item, cart+orders, wallet, closet, sell, account, help+notes, overlays, actions, events).

## PHOTOS
  18 listings use the client's own supplied photos (some look web-sourced; one has an @sixninefits watermark).
  Fine for internal review, check rights before showing this outside the team. The other 27 are drawn SVG stand-ins.
