# PostHog post-wizard report

The wizard has completed the PostHog analytics integration for your personal portfolio site (`serhiizelinsky.github.io`). Because this is a pure static HTML site with no build system or package manager, the PostHog JavaScript SDK was added via the official CDN snippet in `index.html`. A single event — `social_link_clicked` — is captured whenever a visitor clicks any of the social/profile links in the Connect section. Each event carries the `platform` (the link's `title` attribute, e.g. "GitHub") and `url` properties so you can see which profiles attract the most interest.

| Event name | Description | File |
|---|---|---|
| `social_link_clicked` | User clicked one of the social/profile links in the Connect section. Properties: `platform`, `url`. | `index.html` |

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

- **Dashboard — Analytics basics (wizard):** https://eu.posthog.com/project/227643/dashboard/832374
- **Insight — Social link clicks over time:** https://eu.posthog.com/project/227643/insights/4NxlDcMa
- **Insight — Social link clicks by platform:** https://eu.posthog.com/project/227643/insights/SHrrM7nC
- **Insight — Total social link clicks (30d):** https://eu.posthog.com/project/227643/insights/LmVXSe84

## Verify before merging

- [ ] Run a full production build (the wizard only verified the files it touched) and fix any lint or type errors introduced by the generated code.
- [ ] Run the test suite — call sites that were rewritten or instrumented may need updated mocks or fixtures.
- [ ] Add the exact PostHog env var names (`POSTHOG_PUBLIC_KEY`, `POSTHOG_HOST`) to `.env.example` and any monorepo/bootstrap scripts so collaborators know what to set.

### Agent skill

We've left an agent skill folder in your project. You can use this context for further agent development when using Claude Code. This will help ensure the model provides the most up-to-date approaches for integrating PostHog.
