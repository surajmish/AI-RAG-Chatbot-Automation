# Test Queries for RAG Validation

Run each of these through your Chat Trigger and check whether the AI agent's answer matches the "expected source" row from `demo_kb_data.csv`. This tells you if retrieval is actually pulling the right chunk, not just generating a generic answer.

| # | Test message to send | Expected source (id) | What to check |
|---|----------------------|----------------------|----------------|
| 1 | "How long will my order take to arrive?" | 1 | Mentions 3-5 days standard, 1-2 days express |
| 2 | "Can I return something I bought on sale?" | 5 | Says sale items are final sale |
| 3 | "My headphones are Bluetooth, right?" | 17 | Mentions Bluetooth 5.0, Pro/Max series |
| 4 | "I want to cancel my order, is that possible?" | 12 | Mentions 1-hour free cancellation window |
| 5 | "Do you deliver outside India?" | 2 | Says India-only currently |
| 6 | "It says delivered but nothing showed up" | 14 | Suggests waiting, then contacting support |
| 7 | "What's your policy if my card gets declined?" | 11 | Lists possible reasons, suggests retry |
| 8 | "I forgot my password" | 15 | Points to Forgot Password link, 30-min validity |
| 9 | "Are you open right now?" | 19 | Mentions Mon-Fri, 9-6 IST |
| 10 | "I want to speak to a real person" | 20 | Should trigger escalation / hand-off path |
| 11 | "How long is the warranty on my earbuds?" | 7 | Distinguishes electronics (1 yr) vs accessories (90 days) |
| 12 | "asdkjf random gibberish test" | none | Should NOT hallucinate an answer — should say it can't find relevant info or ask for clarification |

### How to use this
1. Load `demo_kb_data.csv` into your Vector Store node (or Google Sheets/Airtable if using that as the tool source).
2. Send each test message one at a time through the trigger.
3. Mark pass/fail based on whether the reply matches the expected source's content.
4. Query #12 is a **negative test** — it checks your agent doesn't invent answers when nothing relevant exists in the knowledge base. If it hallucinates instead of admitting uncertainty, tighten the system prompt (e.g. "Only answer from the provided knowledge base; if unsure, say so and offer to escalate").
