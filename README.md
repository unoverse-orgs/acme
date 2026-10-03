# Acme: the unoverse demo org

A complete org, laid out the way every org's own repo is. Clone it to see how one is built, copy
what you need into your own org, or connect it to a universe and watch it arrive.

```
acme/
  unoverse.yaml   org: acme   (this repo is one org; the name is declared here)
  styles/         Acme's tokens, on top of the shared design system
  identity/       organisation, brand, purpose, story
  components/     welcome, and text-chat (the chat surface)
  apps/           chat: a conversational app that draws text-chat
  skills/         sample-complaint-handling: how an Agent handles a complaint
  blocks/         sample-concise-answers: a reusable prompt fragment
  nodes/          AcmeWeather (a call that settles) and AcmeChatStream (a reply that streams)
```

## Use it

- **Read it.** Open the folder in Studio (`unoverse studio`) or your editor.
- **Copy from it.** Take any folder into your own org repo. Node types are one per platform, so
  give a copied node your own type (`AcmeWeather` becomes `YourWeather`).
- **Run it.** On your universe, connect an org to this repo (org page, Source tab) and press Sync
  now. Every universe pulls an org's work from Git; nothing is pushed in.

## Make your own org

```
mkdir my-org && cd my-org
unoverse create
```

You get the baseline (your tokens, your identity, Git, the pull-request check). Bring in what you
need from here.

Docs: https://docs.unoverse.ai
