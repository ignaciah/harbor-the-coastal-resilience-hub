Harbor — The Coastal Resilience Hub
Build, Ship, Shape: Amazon Developer Hackathon 2026
[Fire TV](https://developer.amazon.com/tv) [Alexa+](https://developer.amazon.com/alexa) [Ring](https://developer.ring.com) [Bee](https://developer.amazon.com/bee) [AWS Builder](https://aws.amazon.com) [Open Source](https://github.com) [License: MIT](https://opensource.org/licenses/MIT) [Gloucester MA](#)
One calm place when the storm rolls in.
Harbor unifies Ring, Alexa+, Bee, and Fire TV into a single safety network for 60M coastal Americans. When high tide floods a porch, Ring sees it, Bee remembers who needs meds, Alexa+ builds an evacuation plan via MCP, and Fire TV shows the whole street as a calm community dashboard.
Devpost: https://amazonappdev2026.devpost.com — Deadline Oct 23, 2026 3pm EDT
Demo Video: (2:45) [YouTube link — add yours]
Built in: Gloucester, MA — for neighbors everywhere

What it does — 60 sec
Ring Dome Cam 4K detects water on steps with computer vision
Alexa+: "Harbor, status?" → calls MCP tools get_tide, check_neighbors, create_evac_plan
Bee wearable recalls yesterday's conversation: "Mrs. Ruiz needs meds before 4pm tide"
Fire TV Vega OS Hub auto-launches: 4-house Ring mosaic + evacuation route + one-tap neighbor check
Consent-based Ring broadcast to consented homes only
Tracks — How we use each tech (judges check this)
Track
What we built
Why it's real usage
Fire TV
React Native Vega OS app, live tiles, Ring mosaic, Alexa+ overlay
Uses Vega SDK, not web wrapper
Alexa+
Agent Skill + MCP Server (Node.js) with 4 tools
Real MCP tools, Bedrock Claude 3.5 reasoning
Bee
Bee SDK + Apple Watch BeeOS + memory graph
Captures intent, vector memory
Ring
Ring Appstore app + Smart Video Search + flood CV
Real API + CV segmentation


Mini-challenges: AWS Builder (IoT Core, Lambda, DynamoDB, Bedrock) + Open Source (MIT, public repo, issues)
Architecture
Ring API + CV ──┐
                ├─> Harbor Core (Lambda + Bedrock) ──> Alexa+ MCP ──> Alexa+ Skill
Bee Wearable ───┤            │
                └─> Memory Graph (DynamoDB + OpenSearch) ──> Fire TV Hub (Vega OS)
                                     │
                                     └─> Town Dashboard (IoT Core)

See ARCHITECTURE.md + deck: /mnt/data/harbor_deck
Quick Start
git clone https://github.com/YOURNAME/harbor
cd harbor
cp .env.example .env
# Fire TV
cd fire-tv && npm i && npm run start:vega
# Alexa MCP
cd ../alexa-mcp && npm i && npm run dev
# Ring CV
cd ../ring-service && pip install -r requirements.txt && python flood_detector.py
# Bee Memory
cd ../bee-service && pip install boto3 && python memory_graph.py

Demo Video Script
See docs/demo-script.md — 2:45, captioned, no music over voice.
Product Feedback (Required)
See docs/feedback.md — detailed notes on Vega OS, MCP latency, Ring staging, Bee API.
Team
Ignacia Heyer — Gloucester-based builder, coastal community advocate — heyeri20
License
MIT — free for towns, paid town license for municipal dashboard later.
