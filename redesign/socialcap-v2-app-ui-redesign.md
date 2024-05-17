# Socialcap v2 - App UI

This is a "draft" document just to discuss and converge on ideas.

To be used and discussed with:

- Nico 
- Lucas
- Leandro
- Mario

Main discussion channel may be Discord, please (Lucas) ?

See: [Socialcap v2 - General Redesign](./socialcap-v2-general-redesign-md)

Trello: [Roadmap 2024 03-6](https://trello.com/b/xpX9F2IY/roadmap-2024-03-06)

## Redesign

### Goals

We have tree great goals here:

- **Simplify the administration and monitoring of communities** and master plans. Community admins are among the critical users of Socialcap, so assisting them contributes to the utilization and expansion of Socialcap.

- **Facilitate user acquisition** by considering features to include in the app: home design with invite buttons, community page with easy "invite to these communities" buttons, the ability to link standalone community pages to other apps, etc.

- **Empower the users of Socialcap** who are requesting a credential and those who have obtained it, **so they can proudly display it to others using Socialcap**, thus contributing to its utilization and expansion.

### General requirements

- Support mobile and responsive layouts
- Add styling consistency to lists, tabs, forms, etc 
- Fix "branding errors" 
- Add user requested features
- Improve navigation for Admins
- Improve reuse of Masterplans for Admins
- Empower user's submission and view of own credentials
- Provide a clear path for monetization
- Provide external linking to Socialcap community page
- Improve visibility of Voting process
- **IMPORTANT**: rethink some namings (such as Masterplan) that may confuse users.

### Common features

Some requested features are common to many entities:

- Delete button for Claims, Communities, Members and Masterplans: this may be needed when some of them were created by error and we no longer need them. Question: should we allow for permanent deletion or just send to archival and make not visible ?
- Copy/Paste buttons for Claims and Masterplans: this may be needed as we usually need to copy them to create a new one and we now need to do all the Masterplan again (tedious !).
- Share/Link buttons: to help users share a link of their Credential to others, or admins to share their community links to others.
- Invite button: for admins to invite users to the community, this may also imply some "rewards" (an airdrop ?), or for users to invite other users to a program (for example zkIgnite Navigators) that may also imply some "rewards" for him.

## Layout

We need to change the Layout to include a Sidebar so we can simplify navigation for admins, making the running masterplans and admined communities more accesible to these admins.

NOTE: names used here are preliminar and items will require a better naming for best UX.

The proposed Layout should include these changes

### Navbar

The Navbar needs some additional items:

- **Sidebar toggle**: as usual will show/hide the (main) Sidebar. Used mainly in Mobile.

- **Search**: as a search button or search input which allows for searching existent users, claims, etc. Will be useful for admins, and "may be" useful to users too (not clear now)

- **Network**: select the network form the list of networks, currently: "Mainnet", "Berkeley", "Devnet"

- **Notifications**: add a notifications bell to announce when notifications are received and pending. Needed when we dispatch transactions that will take some time (minutes) to be completed. Also can display a panel with all not acknowledeged notifications.

- **User**: show the user photo, or a generated Identicon. Is a menu with items "Profile", "Activity" and "Logout". The "Activity" item will display the Activities sidebar.
- **SOS**: a help button that can display the Help sidebar.

Some styling changes: make it more light and not so high ? How can we change transparency when scrolling up ?

### Sidebar

The main sidebar will be visible in desktop and hidden by default on mobile (can be shown using the Sidebar toggle). 

It may contain this main items (with subitems):

- **Home**: redirects to "Home" page. This is the default active item after login.

- **My space**: redirects to the "My space" page. 

- **Active masterplans**: show as subitems the "running" plans that are currently running: either which are receiving claims ("active" state) or which are in the voting process ("voting" state). We may also show "drafts" here as the admin may need to have them readily available while working on them. Should display "title + state". 

  Each subitem will redirect to the corresponding "Masterplan" page.

  It may be visible to admins and normal users too. For normal users it will show only the "active" plans.

- **Admined communities**: show as subitems the "active" communities which are being admined by the current user. 

  Each subitem will redirect to the corresponding "Community" page.

  This is not visible to current users, which can access his communities using the "My space" tab. Question: current users may instead get a button where they can create a new community (not clear if good or bad now) ? 
  

### Activities

An activities sidebar (example is Trello > Tablero > ... > Actividades). It will show all actions preformed on Socialcap, but we mainly will restrict it to Transactions (not all activities). It is needed as some txns take a long time to complete, and they can sometimes fail, so we need a way to keep users informed of this. 

It "may" become an item in the main Sidebar, if it is considered as very frequent an important. For now, I rather keep it a little less visible, just linked to the user menu.

### Help

A help sidebar which can display a Help index and allows access to the Docs site or other Help site. We can start with a simple list of help items and improve later with more features, like search for some special feature, etc.

### Pages

All pages share the common Navbar, BUT may have a different Sidebar (or no Sidebar at all). The Sidebar toggle in the Navbar allows accessing the Sidebar from any other page.

As described in the goals we plan to incorporate to the pages features that help with **user acquisition**.

We may also consider to merge some pages into the same one, but different views depending on "state" and "permissions". 

Current pages are:

- Home (user)
- My space (user)
- Claim submission (user)
- Claim view (user, validator)
- Credential view (user)
- Community creator (user)
- Community editor (admin)
- Community view (user, admin)
- Masterplan editor (admin)
- Profile editor (user)

Visibility: 

- (user) indicates a page that is visible to the logged user, and only to the items he created or belongs to. Note that admins and validators are also users, so they can see these pages too.
- (admin) indicates a page that is only visible to an admin of that community.
- (validator) indicates a page that can be visible to a given validator, BUT only if the validator has been assigned to the claim.

Note:

- Some  of this pages are shown directly as editors (Admined Community, Masterplan, Profile), but may be better if we can show them as views when redirecting to them and can be edited in place or by using a "Edit" button for some sections. This should be analyzed if convenient or not ... but may change due to redesign.

## Page: Home

**Route**: `/home`

This is the page where we can easily showcase communities and "claimable" credentials for all Socialcap communities.

**Navbar**: common Navbar

**Sidebar**: common main Sidebar.

**Content**: may contain the following sections:

- **A (small) stats section**. Would it be good to have a small dashboard with some Socialcap stats ? Such as total number of communities/projects, number of claims, number of issued credentials ? 
- **An invite section** (like the Loom https://www.loom.com/home). We can also add "invites" here so users or admins can invite other users to a community or campaign/program.
- **Join & Claim**: (maybe) a carrousel or grid with all communities and claimables: we can doc click here and go directly to the Claim submission form or first join the community and then go to the claim submission.

## Page: My space

**Route**: `/my-space?{tab}`

**Navbar**: common Navbar

**Sidebar**: common main Sidebar.

We need the following views:

### Tab: My credentials

- Never used, but needs to be consistent with how we are presenting list of items (either as a list or a grid of cards)

### Tab: My claims

- Improve the List of items (make it consistent)
- Info needed on each item: "Community title", "Masterplan Title", "Masterplan Description", "Claim UID", "Current State", "Last update date". ((Ahora dice Claimed y la fecha aunque esta en Draft, y eso confunde)). Deberiamos agregar el "project name o claim title" (de donde lo sacamos ?)

### Tab: My communities

- Improve the List of items (make it consistent)
- Info in each item is ok.

### Tab: My tasks

- Improve the list display, add info and styling consistency and allow easily going to the Submitted claim view.

- NEW: Consider a small "task" editor accessible from the list so the admin/validator can add comments or info to a given claim, without leaving the list !
- NEW: Allow expanding a brief resume of the task, claim and notes so the Validator can see some info right there without opening a new page.

## Page: Claim

**Route**: `/claims/{uid}?{state}`

**Navbar**: common Navbar

**Sidebar**: HIDE main Sidebar.

**Content**: display the correct view. BUT include a BACK or CLOSE button, so we can go back to the previous page (maybe similar to whet Gmail does ?)

We need the following views:

### Editor: Claim submission

Visible: only the creator of the claim.

States: `new` or `draft`

New features: 

- Delete claim button

- IMPORTANT: Consider the Payment workflow !

### View: Submitted claim 

States: `claimed`, `voting`, `approved`or `rejected`

New features: 

- Share button ?
- Invite button ?

- Validator notes: a section only for Validators (and Admins) and only while in the "claimed" or "voting" states where they can add comments to the Claim. This may be visible to the claimer or only to validators.

## Page: Credential

**Route**: `/credential/{uid}`

We need the following views:

### View: Issued credential

States: `issued` 

New features: 

- Share button ?
- Invite button ?
- Link to Submitted Claim ? 



## Page: Community 

**Route**: `/communities/{uid}?{state}` or `/communities/:{slug}?{state}`

### View: Create community 

State: `new`

- IMPORTANT: Consider the Payment workflow !

### View: Community dashboard

State: `active` or `inactive` 

Sidebar:

### View: Community editor

State: `active` or `inactive` 

- IMPORTANT: Consider the Funding community workflow !

### 

## Page: Masterplan

### Masterplan editor

## Page: Profile 

### editor