# Turn any form into a floating widget

_Document Picture-in-Picture opens a new lane for always-on UI_

A useful browser feature just got more interesting for builders: picture-in-picture is no longer only for video. That opens up a clean way to create floating, persistent UI for workflows that need to stay visible while users keep working.

---

## Always-on UI, not just always-on video

![A modern browser window showing a floating compact widget with form fields, notes, and controls, rendered in a clean product illustration style.](https://cdn.itwcreativeworks.com/newsletters/slapform/content/-P2nOiWAYeE69mQj9Adh/section-1.png)

The newer picture-in-picture window can hold real HTML, not just media playback. That makes it a good fit for small utility surfaces that need to stay on screen: a live lead form, a status panel, a notes box, or a compact control center. For static-site builders, the appeal is obvious. You can keep the main page lightweight and push the persistent interaction into a separate floating window. If you already use forms as workflow triggers, this opens the door to a much more focused experience around submission, review, and follow-up.

[Read the full article →](https://slapform.com/blog/what-to-put-in-an-always-on-ui-window)

---

## Move a form out of context, and styles can break

![Split-screen illustration of the same form on a main page and in a floating browser window, with a few broken style callouts and highlighted CSS rules.](https://cdn.itwcreativeworks.com/newsletters/slapform/content/-P2nOiWAYeE69mQj9Adh/section-2.png)

Cloning UI into a separate window sounds easy until the CSS stops behaving. Anything that depends on the original page layout, ancestor selectors, or surrounding spacing may look off once it is detached. The safer move is to treat the floating window like its own mini app: scope styles carefully, test component states in isolation, and use browser-specific hooks when needed. If you are building a contact form, registration panel, or feedback widget, verify the labels, focus states, and error messages still read clearly when the form lives on its own.

---

**Sponsored**

---

## Use it for workflows people keep open

![A designer-developer workspace with a floating widget beside a code editor, showing a compact intake form and a live submission list.](https://cdn.itwcreativeworks.com/newsletters/slapform/content/-P2nOiWAYeE69mQj9Adh/section-3.png)

This pattern makes the most sense for tasks that are small, active, and revisited often. Think support chats, live dashboards, collection queues, and quick-entry forms that sit beside the work. For Slapform-style setups, that could mean a tiny intake form for internal requests, a floating feedback widget for an agency project, or a submission panel that stays visible while a builder edits content in another tab. The goal is not to replace full pages, but to keep one useful surface available without forcing users to bounce around.

---

## Browser support still needs a fallback plan

![A browser compatibility checklist next to a floating widget and a normal fallback form, illustrated like a product launch planning board.](https://cdn.itwcreativeworks.com/newsletters/slapform/content/-P2nOiWAYeE69mQj9Adh/section-4.png)

This is the part to plan for early. Picture-in-picture support for document-based content is not universal, and it will not behave the same way inside every embedded playground or nested frame. If you ship this pattern, make sure the core experience still works as a normal page, then treat the floating window as an enhancement. That way the form still submits, the webhook still fires, and the automation still runs even when the fancy window is unavailable.

---

Best,  
The Slapform Team

_Tags: #web-development #jamstack #ui-patterns #browser-apis_

---
_You're receiving this because you subscribed to [Slapform](https://slapform.com)._
