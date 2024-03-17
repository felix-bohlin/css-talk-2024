# Modern CSS layouts with catchy one-liners

Scenario:
- you're new to a SASS project and your assignment is to migrate from an old frontend to a new one

Assumtions:
- UI system like MUI, Vuetify, Bootstrap, to handle colors, spacing, components etc
	- you don't have to care as much about how it looks but more about layout and edge cases
- CSS-in-JS SASS project
- IE11 is not supported

What this talk ISN'T:
	- colors, color-mix, oklch, custom properties
	- starting from scratch

If you can try it in CSS before you use JS
	- you get a lot from the browser for free
	- you'll impress your co-workers
	- probably less code

General tips when debugging CSS
- if you get stuck, remove code
	- strip it down to the basics



- one-liners
  - aspect-ratio
  - place-items: center
  - prevent input browser zoom : font-size: max(16px, 1rem);
	  - This use of max() ensures that regardless of another value provided, the font-size will be at least 16px and therefore prevent the forced browser zoom.
  - 