# Sample nodes

Two worked examples of the Unoverse node format, one of each kind. They are real,
working nodes: wire them into a workflow and they run.

| Node | Kind | What it teaches |
|---|---|---|
| `nodes/AcmeWeather` | `PromiseNode` | Two chained calls, a config form, computed outputs. No API key. |
| `nodes/AcmeChatStream` | `CallbackNode` | Streaming, and how credentials work. Needs an OpenAI key. |

## Where to start

Read `AcmeWeather` first, file by file, in this order:

1. `node.yaml` says what the node IS: its identity, its kind, and when a planner
   should pick it.
2. `interface.yaml` says what it CONNECTS TO: inputs, outputs. Output names become
   what someone types in a template later, so they are named for what they carry.
3. `config.yaml` is the settings form a builder sees on the canvas. It is a JSON
   schema; the platform draws the form from it.
4. `api/run.yaml` is the calls the node makes, always a list, each entry named.
5. `api/events.yaml` is everything that leaves the node: one row per output.
6. `test.yaml` is a fixture that runs against the real service.

Then read `AcmeChatStream` for the two things weather cannot show you: a reply
that arrives as a stream of events rather than one body, and a call that has to
prove itself to the service with a credential.

## Running them

Open Studio (`unoverse studio`) and go to the Nodes screen. Pick a node, load its
sample, and run it. Running is the only proof: a node that lints but has never run
is not done.

`AcmeWeather` runs as-is. `AcmeChatStream` needs a key: credentials are read
from your `.env` as `<CREDENTIAL>_<FIELD>` in upper snake case, so
`openAICredential.apiKey` is:

```
OPENAI_API_KEY=sk-...
```

The credential FILE in this package (`credentials/openAICredential.yaml`) declares
only the shape. No value ever lives in a node file, which is why the folder is safe
to commit and to share.

## Making your own

Copy the closer of the two samples into a new folder under `nodes/<your-package>/`
and change it one file at a time, running as you go. The guide behind every file:

- The format in full: https://docs.unoverse.ai/nodes/manifest-nodes
- One answer or many: https://docs.unoverse.ai/nodes/node-types
- Credentials: https://docs.unoverse.ai/nodes/credentials
- The settings form: https://docs.unoverse.ai/nodes/config-schema
- Paging, batching, polling: https://docs.unoverse.ai/nodes/calls-that-loop
- Getting picked by the planner: https://docs.unoverse.ai/nodes/node-discoverability
- Testing: https://docs.unoverse.ai/nodes/testing-nodes
- When something goes wrong: https://docs.unoverse.ai/nodes/troubleshooting

The condensed rulebook, written for coding agents and just as useful to people:
https://docs.unoverse.ai/nodes/CLAUDE.md
