# Codex plan and usage limits: what to do when Codex says you've hit your limit

**Short answer:** Codex signed in with ChatGPT runs on your plan's allowance. When it runs out you can wait for the reset time shown by `/status`, add Codex credits on Plus or Pro, or move to a larger Pro tier. None of this applies if Codex is signed in with an API key; that usage is billed to your API account.

Plan rules below were checked against OpenAI's Help Center on November 15, 2026. Prices are Pay2GPT's current prices and are refreshed when they change.

## 1. Check which account Codex is billing

```bash
codex login status
```

| Output | What it means |
|---|---|
| Logged in using ChatGPT | Codex uses your ChatGPT plan. Credits and plan upgrades apply. |
| Logged in using an API key | Codex bills your OpenAI API account. Plans and credits don't change anything. |

Switching back: remove `OPENAI_API_KEY`, `OPENAI_BASE_URL` and `CODEX_API_KEY` from your environment, delete any `forced_login_method = "api"` or custom `model_provider` lines in `~/.codex/config.toml`, then `codex logout` and `codex login` with ChatGPT.

## 2. See how much is left

- In a CLI session: `/status` shows the allowance used and when it resets.
- In ChatGPT: Settings → Usage.
- In the Codex app: Usage & Billing.

OpenAI support can't reset usage limits; they only look into miscounted usage. The reset time shown there is the real one.

## 3. Pick a fix

| Your situation | Fix | Card | Alipay | USDT / USDC |
|---|---|---|---|---|
| Limit hit once, deadline can wait | Wait for the reset | free | free | free |
| Free or Go, want daily Codex and Codex Cloud | Plus, one month | $25.19 | $24.93 | $23.90 |
| Plus, a crunch week | 250 Codex credits | $15.82 | $15.66 | $14.90 |
| Plus, limit hit most weeks | Pro 100, one month | $130.29 | $128.94 | $124.90 |
| Pro 100 still runs out | Pro 200, one month | $223.00 | $220.71 | $214.00 |
| You need Ultrafast | Pro 500, one month | $550.79 | $545.11 | $529.00 |
| Codex signed in with an API key | Top up the API account | n/a | n/a | n/a |

## 4. Why the allowance drains faster than expected

- **It's shared.** On Plus and Pro, Codex, ChatGPT Work, Excel and PowerPoint use the same agentic allowance.
- **Speed modes multiply usage.** Fast counts at 2.5 times the Standard rate, Ultrafast at 8 times. Ultrafast is Pro 500 only.
- **Model and context matter.** Bigger contexts and heavier reasoning use more per task.
- **Auto-review doesn't count.** Signed in with ChatGPT, auto-review safety checks are outside plan limits.

## 5. Codex credit packs

Credits are used only after the plan's included usage is gone. They go onto an active Plus or Pro personal plan and stay valid for 12 months.

| Credits | Card | Alipay | USDT / USDC |
|---|---|---|---|
| 250 | $15.82 | $15.66 | $14.90 |
| 500 | $29.35 | $29.05 | $27.90 |
| 1000 | $52.24 | $51.70 | $49.90 |
| 2500 | $112.60 | $111.44 | $107.90 |
| 5000 | $223.94 | $221.63 | $214.90 |

Ordering takes an email and a payment; then you paste the login details from a browser where you're signed in to ChatGPT, check the account and plan shown, and confirm. No password is asked for. Order on [Pay2GPT](https://pay2gpt.com/en/codex-credits?utm_source=github_repo&utm_campaign=offsite).

## FAQ

**Can a Free or Go account add Codex credits?**
Not through Pay2GPT. Credits need an active Plus or Pro personal plan; Free, Go and Business workspace accounts can't take them.

**Do credits change my plan or renewal date?**
No. They sit on top of the plan.

**Can the credit balance go negative?**
Yes, with parallel tasks. A task that starts while the balance is positive can finish after other tasks used it up. The next purchase covers the negative part first.

**Will "ask me before using credits" in my instructions stop spending?**
No. It isn't a billing setting. Once the allowance is used, Codex draws on available credits automatically.

**Are Codex credits the same as API credits?**
No. They work in ChatGPT and Codex signed in with ChatGPT, not with an API key.

**Credits or Pro?**
Credits for the odd heavy week. If you run into the limit most weeks, a Pro tier gives a much larger monthly allowance.

## Sources

- [Using Codex with your ChatGPT plan](https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan)
- [Using Credits for Flexible Usage in ChatGPT](https://help.openai.com/en/articles/12642688)
- [About ChatGPT Pro tiers](https://help.openai.com/en/articles/9793128-what-is-chatgpt-pro)

Pay2GPT is an independent top-up service, not affiliated with OpenAI. Content licensed CC BY 4.0.

Maintained by Pay2GPT — https://pay2gpt.com
