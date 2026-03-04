# Project plan

## 1. Project overview

This is a small YouTube‑style UI built with plain HTML, CSS and a little
vanilla JavaScript.  
Three pages/files are currently in the workspace:

* `index.html` – home page with navbar, sidebar (`.categories`), filter
  bar, video grid, theme toggle and lightweight “login/logout” state.
* `login.html` – standalone authentication page with a basic “demo
  login” form.
* `style.css` – theming, layout and component styles for both pages.

The layout uses a flex column on `body` and a horizontal flex container
(`.mainbody`) for the sidebar+content.  Colours are controlled via CSS
variables and a small script sets `data-theme` for light/dark modes.

## 2. Current status

### Layout

* `body` is `display:flex; flex-direction:column; min-height:100vh`.
* Navbar is `position:sticky` and 56 px tall.
* `.mainbody` fills the remaining space with `height:calc(100vh - 56px)`.
* `.categories` (the `<aside>`‑equivalent) has `overflow-y:scroll`,
  `width:240px`, and custom scrollbar rules that hide the track until the
  user hovers.
* Footer links are inside `.categories-footer`; the sidebar now extends
  to the bottom of the viewport.

### Overflow/scrolling

* Sidebar scrolls independently of the video list.
* Scrollbars are hidden by default (`::-webkit-scrollbar {width:0}`)
  and shown on hover.
* Video column (`.videos`) has its own `overflow-y:scroll`.

### Authentication

* The login page replicates Google/YouTube styling using the same
  `navbar` component and theme script.
* Form submission simply writes to `localStorage`; the “login” button on
  `index.html` toggles between Login/Logout and redirects appropriately.
* There is no back‑end authentication – it’s purely for demo purposes.

### Responsiveness

* Breakpoints at 1024 px and 768 px collapse the sidebar, adjust video
  card widths, hide filters and shrink icons.
* `.mainbody` becomes a column on mobile.

## 3. Issues to address

1. **Ensure the sidebar always reaches the footer**  
   (already handled by the `.mainbody` height rule and flex behaviour,
   but keep `min-height:0` on flex children if you add nested flexboxes).

2. **Scrollbar appearance**  
   The current CSS hides the scrollbar in WebKit browsers; Firefox is
   controlled with `scrollbar-width:none`.  You may want to test
   on different platforms.

3. **`aside` tag vs `.categories` wrapper**  
   Your HTML now puts the sidebar content in a `.categories` div inside
   `.mainbody`.  Semantically you could use `<aside>` and adjust the CSS
   selectors accordingly.

4. **Navbar/menu toggle behaviour**  
   Mobile menu and search button require JS for toggling – not yet
   implemented.

5. **Accessibility**  
   * `role="tablist"`/`role="tab"` are present on filter buttons but no
     keyboard interaction is implemented.
   * `aria-live` on login errors works, but focus management could be
     improved.

## 4. Next steps

* **Styling tweaks**
  * Add `min-height:0` to `.categories` if you nest flex items inside.
  * Consider moving the footer markup outside of the scrollable area if
    you ever want it fixed.

* **JavaScript features**
  * Make filter buttons change the active tab and maybe filter the video
    array.
  * Implement search form behaviour (currently just a dummy).
  * Enhance login logic (validate email format, show real errors,
    maybe integrate with a backend or Firebase).

* **Performance**
  * Lazy‑load video thumbnails/iframes (you already use `loading="lazy"`
    on the preview iframe).
  * Debounce hover preview requests.

* **Responsive/improvements**
  * Add hamburger menu functionality.
  * Add a toggle that collapses the sidebar on desktop.
  * Convert color variables into a Sass/SCSS partial if the project
    grows.

* **Documentation**
  * Add comments in CSS explaining the scrollbar hiding rules.
  * Document the theme‑toggle script.

* **General housekeeping**
  * Rename `.cagories-footer` → `.categories-footer` (typo).
  * Remove unused selectors/JavaScript once features are complete.

## 5. File creation

Create `plan.md` with the text above; it can live next to your HTML files
and act as a check‑list as you continue working on the clone.

---

With this plan in place you’ve got a clear sense of what’s implemented
and what remains to be done.  Tackle the layout/overflow items first if
you’re still having trouble with the sidebar height, then move on to
interactivity and polish.# Project plan

## 1. Project overview

This is a small YouTube‑style UI built with plain HTML, CSS and a little
vanilla JavaScript.  
Three pages/files are currently in the workspace:

* `index.html` – home page with navbar, sidebar (`.categories`), filter
  bar, video grid, theme toggle and lightweight “login/logout” state.
* `login.html` – standalone authentication page with a basic “demo
  login” form.
* `style.css` – theming, layout and component styles for both pages.

The layout uses a flex column on `body` and a horizontal flex container
(`.mainbody`) for the sidebar+content.  Colours are controlled via CSS
variables and a small script sets `data-theme` for light/dark modes.

## 2. Current status

### Layout

* `body` is `display:flex; flex-direction:column; min-height:100vh`.
* Navbar is `position:sticky` and 56 px tall.
* `.mainbody` fills the remaining space with `height:calc(100vh - 56px)`.
* `.categories` (the `<aside>`‑equivalent) has `overflow-y:scroll`,
  `width:240px`, and custom scrollbar rules that hide the track until the
  user hovers.
* Footer links are inside `.categories-footer`; the sidebar now extends
  to the bottom of the viewport.

### Overflow/scrolling

* Sidebar scrolls independently of the video list.
* Scrollbars are hidden by default (`::-webkit-scrollbar {width:0}`)
  and shown on hover.
* Video column (`.videos`) has its own `overflow-y:scroll`.

### Authentication

* The login page replicates Google/YouTube styling using the same
  `navbar` component and theme script.
* Form submission simply writes to `localStorage`; the “login” button on
  `index.html` toggles between Login/Logout and redirects appropriately.
* There is no back‑end authentication – it’s purely for demo purposes.

### Responsiveness

* Breakpoints at 1024 px and 768 px collapse the sidebar, adjust video
  card widths, hide filters and shrink icons.
* `.mainbody` becomes a column on mobile.

## 3. Issues to address

1. **Ensure the sidebar always reaches the footer**  
   (already handled by the `.mainbody` height rule and flex behaviour,
   but keep `min-height:0` on flex children if you add nested flexboxes).

2. **Scrollbar appearance**  
   The current CSS hides the scrollbar in WebKit browsers; Firefox is
   controlled with `scrollbar-width:none`.  You may want to test
   on different platforms.

3. **`aside` tag vs `.categories` wrapper**  
   Your HTML now puts the sidebar content in a `.categories` div inside
   `.mainbody`.  Semantically you could use `<aside>` and adjust the CSS
   selectors accordingly.

4. **Navbar/menu toggle behaviour**  
   Mobile menu and search button require JS for toggling – not yet
   implemented.

5. **Accessibility**  
   * `role="tablist"`/`role="tab"` are present on filter buttons but no
     keyboard interaction is implemented.
   * `aria-live` on login errors works, but focus management could be
     improved.

## 4. Next steps

* **Styling tweaks**
  * Add `min-height:0` to `.categories` if you nest flex items inside.
  * Consider moving the footer markup outside of the scrollable area if
    you ever want it fixed.

* **JavaScript features**
  * Make filter buttons change the active tab and maybe filter the video
    array.
  * Implement search form behaviour (currently just a dummy).
  * Enhance login logic (validate email format, show real errors,
    maybe integrate with a backend or Firebase).

* **Performance**
  * Lazy‑load video thumbnails/iframes (you already use `loading="lazy"`
    on the preview iframe).
  * Debounce hover preview requests.

* **Responsive/improvements**
  * Add hamburger menu functionality.
  * Add a toggle that collapses the sidebar on desktop.
  * Convert color variables into a Sass/SCSS partial if the project
    grows.

* **Documentation**
  * Add comments in CSS explaining the scrollbar hiding rules.
  * Document the theme‑toggle script.

* **General housekeeping**
  * Rename `.cagories-footer` → `.categories-footer` (typo).
  * Remove unused selectors/JavaScript once features are complete.

## 5. File creation

Create `plan.md` with the text above; it can live next to your HTML files
and act as a check‑list as you continue working on the clone.

---

With this plan in place you’ve got a clear sense of what’s implemented
and what remains to be done.  Tackle the layout/overflow items first if
you’re still having trouble with the sidebar height, then move on to
interactivity and polish.