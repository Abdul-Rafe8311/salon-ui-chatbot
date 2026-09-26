# salon-ui-chatbot

Standalone Glow & Go Salon demo page, deployed at
https://salon-ui-chatbot.abdul-rafe8311.workers.dev.

The page source is public/index.html. It posts { message, session_id } directly
to https://whatsapp-salon-bot.abdul-rafe8311.workers.dev/api/chat. Concurrent
posts share the conversation session; the Worker buffers them using the
production quiet window and turn lock. A request that joins an active turn
receives 202 pending, while the owning request displays the single merged
reply. The page no longer uses the legacy Render mock API.

wrangler.toml deploys only public/ assets under the existing Worker name. Run
wrangler dev for a local preview and wrangler deploy to publish.
