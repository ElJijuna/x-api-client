# Roadmap

## Legend
- ✅ Implemented
- ⬜ Pending

---

## Phase 0 — Project Setup

| Task | Status |
|------|--------|
| `package.json` (ESM, exports, scripts) | ⬜ |
| `tsconfig.json` | ⬜ |
| `tsup.config.ts` (CJS + ESM dual build) | ⬜ |
| `jest.config.ts` (ts-jest) | ⬜ |
| `typedoc.json` | ⬜ |
| `.releaserc` (semantic-release) | ⬜ |
| GitHub Actions — CI workflow (test on PRs) | ⬜ |
| GitHub Actions — Release workflow (semantic-release + npm publish + GitHub Pages) | ⬜ |
| GitHub Actions — TypeDoc workflow (manual dispatch) | ⬜ |
| `.github/CONTRIBUTING.md` | ⬜ |
| `.github/pull_request_template.md` | ⬜ |
| `.github/ISSUE_TEMPLATE/` | ⬜ |

---

## XClient (entry point)

| Method | Endpoint | Status |
|--------|----------|--------|
| `tweet(id)` | — chainable | ⬜ |
| `user(id)` | — chainable | ⬜ |
| `userByUsername(username)` | — chainable | ⬜ |
| `me()` | — chainable (authenticated user) | ⬜ |
| `search(params)` | `GET /2/tweets/search/recent` | ⬜ |
| `searchAll(params)` | `GET /2/tweets/search/all` (Academic / Pro) | ⬜ |
| `stream(params?)` | `GET /2/tweets/search/stream` | ⬜ |
| `sampleStream(params?)` | `GET /2/tweets/sample/stream` | ⬜ |
| `list(id)` | — chainable | ⬜ |
| `space(id)` | — chainable | ⬜ |
| `on('request', cb)` | — event emitter (RequestEvent) | ⬜ |

---

## TweetResource

| Method | Endpoint | Status |
|--------|----------|--------|
| `get(fields?)` | `GET /2/tweets/:id` | ⬜ |
| `post(params)` | `POST /2/tweets` | ⬜ |
| `delete()` | `DELETE /2/tweets/:id` | ⬜ |
| `likes()` | `GET /2/tweets/:id/liking_users` | ⬜ |
| `retweets()` | `GET /2/tweets/:id/retweeted_by` | ⬜ |
| `quoteTweets(params?)` | `GET /2/tweets/:id/quote_tweets` | ⬜ |
| `hide()` | `PUT /2/tweets/:id/hidden` (`hidden: true`) | ⬜ |
| `unhide()` | `PUT /2/tweets/:id/hidden` (`hidden: false`) | ⬜ |

---

## UserResource

| Method | Endpoint | Status |
|--------|----------|--------|
| `get(fields?)` | `GET /2/users/:id` | ⬜ |
| `getByUsername(fields?)` | `GET /2/users/by/username/:username` | ⬜ |
| `tweets(params?)` | `GET /2/users/:id/tweets` | ⬜ |
| `mentions(params?)` | `GET /2/users/:id/mentions` | ⬜ |
| `following(params?)` | `GET /2/users/:id/following` | ⬜ |
| `followers(params?)` | `GET /2/users/:id/followers` | ⬜ |
| `follow(targetUserId)` | `POST /2/users/:id/following` | ⬜ |
| `unfollow(targetUserId)` | `DELETE /2/users/:id/following/:target_user_id` | ⬜ |
| `like(tweetId)` | `POST /2/users/:id/likes` | ⬜ |
| `unlike(tweetId)` | `DELETE /2/users/:id/likes/:tweet_id` | ⬜ |
| `likedTweets(params?)` | `GET /2/users/:id/liked_tweets` | ⬜ |
| `retweet(tweetId)` | `POST /2/users/:id/retweets` | ⬜ |
| `undoRetweet(sourceTweetId)` | `DELETE /2/users/:id/retweets/:source_tweet_id` | ⬜ |
| `block(targetUserId)` | `POST /2/users/:id/blocking` | ⬜ |
| `unblock(targetUserId)` | `DELETE /2/users/:id/blocking/:target_user_id` | ⬜ |
| `blocking(params?)` | `GET /2/users/:id/blocking` | ⬜ |
| `mute(targetUserId)` | `POST /2/users/:id/muting` | ⬜ |
| `unmute(targetUserId)` | `DELETE /2/users/:id/muting/:target_user_id` | ⬜ |
| `muting(params?)` | `GET /2/users/:id/muting` | ⬜ |
| `bookmarks(params?)` | `GET /2/users/:id/bookmarks` | ⬜ |
| `addBookmark(tweetId)` | `POST /2/users/:id/bookmarks` | ⬜ |
| `removeBookmark(tweetId)` | `DELETE /2/users/:id/bookmarks/:tweet_id` | ⬜ |
| `lists(params?)` | `GET /2/users/:id/owned_lists` | ⬜ |
| `listMemberships(params?)` | `GET /2/users/:id/list_memberships` | ⬜ |
| `pinnedLists(params?)` | `GET /2/users/:id/pinned_lists` | ⬜ |

---

## Planned: ListResource

| Method | Endpoint | Status |
|--------|----------|--------|
| `get(fields?)` | `GET /2/lists/:id` | ⬜ |
| `create(params)` | `POST /2/lists` | ⬜ |
| `update(params)` | `PUT /2/lists/:id` | ⬜ |
| `delete()` | `DELETE /2/lists/:id` | ⬜ |
| `tweets(params?)` | `GET /2/lists/:id/tweets` | ⬜ |
| `members(params?)` | `GET /2/lists/:id/members` | ⬜ |
| `addMember(userId)` | `POST /2/lists/:id/members` | ⬜ |
| `removeMember(userId)` | `DELETE /2/lists/:id/members/:user_id` | ⬜ |
| `followers(params?)` | `GET /2/lists/:id/followers` | ⬜ |
| `pin(userId)` | `POST /2/users/:id/pinned_lists` | ⬜ |
| `unpin(userId)` | `DELETE /2/users/:id/pinned_lists/:list_id` | ⬜ |

---

## Planned: SpaceResource

| Method | Endpoint | Status |
|--------|----------|--------|
| `get(fields?)` | `GET /2/spaces/:id` | ⬜ |
| `buyers(fields?)` | `GET /2/spaces/:id/buyers` | ⬜ |
| `tweets(fields?)` | `GET /2/spaces/:id/tweets` | ⬜ |
| `search(query, params?)` | `GET /2/spaces/search` | ⬜ |

---

## Planned: DirectMessageResource

Requires OAuth 2.0 with `dm.read` / `dm.write` scopes or OAuth 1.0a.

| Method | Endpoint | Status |
|--------|----------|--------|
| `createConversation(params)` | `POST /2/dm_conversations` | ⬜ |
| `sendMessage(conversationId, params)` | `POST /2/dm_conversations/:dm_conversation_id/messages` | ⬜ |
| `getEvents(conversationId, params?)` | `GET /2/dm_conversations/:dm_conversation_id/dm_events` | ⬜ |
| `getConversationWithUser(userId, params?)` | `GET /2/dm_conversations/with/:participant_id/dm_events` | ⬜ |
| `getReceivedEvents(userId, params?)` | `GET /2/users/:id/dm_events` | ⬜ |

---

## Planned: StreamRules (FilteredStream helpers)

| Method | Endpoint | Status |
|--------|----------|--------|
| `getRules(ids?)` | `GET /2/tweets/search/stream/rules` | ⬜ |
| `addRules(rules)` | `POST /2/tweets/search/stream/rules` (add) | ⬜ |
| `deleteRules(ids)` | `POST /2/tweets/search/stream/rules` (delete) | ⬜ |
