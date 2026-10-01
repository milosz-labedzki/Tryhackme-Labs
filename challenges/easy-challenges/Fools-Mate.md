# Fools Mate Walkthrough

### Tools Used

- `curl`
- Browser (to understand the blocked move)

### Step-by-Step Methodology

- **Step 1** - Access the chess web application. The winning move (rook from a1 to a8) is blocked by client-side JavaScript.
- **Step 2** - Confirm that the restriction exists only in the browser and not on the server.
- **Step 3** - Bypass the client-side check by sending the move directly to the API using curl:

```bash
curl -X POST http://<IP>/api/move \
  -H "Content-Type: application/json" \
  -d '{"from":"a1","to":"a8"}'
```
- **Step 4** - The server accepts the move and returns the flag.
