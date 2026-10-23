# ViralRecast MCP

Every client's weekly content plan: viral posts, transcripts and competitor ads in your AI.

ViralRecast gives Claude and ChatGPT eyes and ears on social media, built for social media managers and small agencies. Paste a link to a TikTok, Instagram reel or carousel, YouTube video, X, Threads, LinkedIn or Reddit post and your AI receives the full content: transcript with timestamps (automatically transcribed when the network has no captions), the images and text of every carousel slide, top comments, metrics and a Viral Score that shows how much of an outlier the post was for the author's size.

Ask what is trending in a client's niche this week (with a filter for small accounts up to 10K followers), which posts beat a competitor's own average, which ads a competitor is running on Meta, Google, TikTok and LinkedIn and for how many days, and what people are saying about a brand (paid plans). Your AI turns it into the weekly plan, the scripts and the captions.

Free plan with 150 credits. This is a hosted remote server: there is nothing to install.

## Connect

- **Server URL:** `https://viralrecast.com/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 (dynamic client registration and PKCE), or the `vr_...` API key from your dashboard as a Bearer token

**Claude (claude.ai or Claude Desktop):** Settings → Connectors → Add custom connector → paste the URL → Connect → Allow.

**ChatGPT:** Apps → Add → Create MCP app → name ViralRecast, URL above, OAuth → Create → Allow. Then type `@ViralRecast` and paste a link.

**Claude Code:**

```bash
claude mcp add --transport http viralrecast https://viralrecast.com/mcp
```

**Cursor, VS Code and other clients** (`mcp.json`):

```json
{
  "mcpServers": {
    "viralrecast": { "url": "https://viralrecast.com/mcp" }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `read_post` | Reads a post by link: transcript with timestamps, carousel slides, comments, metrics and Viral Score |
| `analyze_post` | Same as `read_post` without the images (kept for compatibility) |
| `search_viral_content` | What is going viral on a topic, with a `max_followers` filter for small accounts |
| `trending_now` | Trending videos right now, no topic needed (TikTok feed, YouTube Shorts) |
| `similar_content` | Posts similar to one you already read |
| `find_similar_posts` | Similarity search over indexed viral posts, to validate a post idea |
| `analyze_creator` | A creator's averages and the posts that beat their own average |
| `search_mentions` | What people are saying about a brand or product, newest first (paid plans) |
| `search_ads` | What is being advertised on a topic |
| `advertiser_ads` | The ads a competitor is running, for how many days and with how many variations |
| `read_ad` | An ad's creative and transcript |
| `transcribe_video` | Transcribes a video that has no captions |
| `download_video` | Downloads a video you own or have the rights to |
| `create_clips` | Cuts a long video into short captioned clips |
| `get_job`, `list_jobs` | Status of media jobs |
| `my_history` | Your recent queries |
| `get_account` | Plan and credit balance |

Prompts: `resumir` (summary), `mapa_mental` (mind map), `por_que_viralizou` (why it went viral), `extrair_aula` (turn it into a lesson), `roteiro_inspirado` (an original script with the same structure).

Full reference: https://viralrecast.com/docs · Guide for agents: https://viralrecast.com/llms.txt

## Try it

1. Summarize this carousel and tell me why it worked: https://www.instagram.com/p/DduGij7CRUm/
2. What is going viral about baking this week on TikTok and Instagram, only from accounts under 10K followers?
3. Which ads is Duolingo running on Meta and Google, and for how many days?
4. Read these 3 posts and build next week's content plan for my pet shop client, with a hook and a script for each.

## Links

- Website: https://viralrecast.com
- Pricing: https://viralrecast.com/pricing
- Privacy: https://viralrecast.com/privacy · Terms: https://viralrecast.com/terms
- Support: contato@viralrecast.com
- Official MCP Registry: `com.viralrecast/viralrecast`

ViralRecast only reads public content. It does not post, like or follow on anyone's account. Downloads and clips are for content you own or have the rights to use.
