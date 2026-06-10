# Product Requirements Document: Coconuts — 2-Player Web Game

## 1. Product Summary

| Field | Description |
| --- | --- |
| Product Name | Coconuts |
| Product Type | Real-time 2-player web game |
| Genre | Social wager-style guessing game / cinematic shell-game experience |
| Platform | Web app, playable on desktop and mobile browsers |
| Theme | Oriental-inspired luxury board-game arena |
| Core Mechanic | One player hides a ball under one of three half coconuts. The other player guesses where the ball is. The winner receives the round stake. |
| MVP Requirement | Human-vs-human mode and human-vs-AI opponent mode |

Coconuts is a fast, visually rich, high-tension guessing game built around a simple but psychologically compelling mechanic: hide, shuffle, guess, win. The gameplay is intentionally easy to understand, so the product must differentiate through premium visuals, animations, sound, atmosphere, tension, streaks, and polished multiplayer flow.

The game should feel less like a flat casual web game and more like a miniature cinematic casino-style duel, with dramatic round intros, animated coconut movement, particle effects, win/loss celebrations, streak indicators, and immersive sound design.

## 2. Product Vision

Coconuts should become a highly polished social competitive game where players can challenge friends, play against strangers, or play against an AI opponent in quick rounds. The game must feel premium from the first second: a cinematic camera glides across an oriental-themed game board, lanterns flicker, soft drums build tension, coconuts slide and spin, and the final reveal lands with satisfying visual impact.

The key product objective is to transform a mechanically simple guessing game into an emotionally engaging experience through:

1. Real-time multiplayer tension.
2. Premium 3D visuals.
3. Quick round-based gameplay.
4. A token economy.
5. Player streaks and status effects.
6. AI opponent mode for immediate playability.
7. Smooth payment integration for token purchases, subject to legal compliance.

## 3. Core Gameplay Loop

### 3.1 Standard Round Flow

1. Both players enter a match.
2. Each player contributes a stake of 10 tokens.
3. Total round pot becomes 20 tokens.
4. Player 1 is assigned the ball.
5. Player 1 secretly selects one of three face-down coconuts.
6. The system stores the selected coconut server-side.
7. The coconuts perform a movement/shuffle animation.
8. Player 2 selects one of the three coconuts.
9. The selected coconut is revealed.
10. If Player 2 selected the coconut hiding the ball, Player 2 wins the 20-token pot.
11. If Player 2 selected incorrectly, Player 1 wins the 20-token pot.
12. The roles switch.
13. A new round begins with a fresh 10-token stake from each player.

### 3.2 Role Rotation

After every round, the roles reverse:

- Previous guesser becomes the hider.
- Previous hider becomes the guesser.
- Each new round requires a fresh 10-token stake from both players.

This creates a fair alternating structure and prevents one player from always controlling the hidden ball.

### 3.3 Starting Balance

Each new player starts with **1,000 tokens**. This gives every user enough starting balance to experience the game before needing to purchase additional tokens.

### 3.4 Token Purchase Rule

When a player runs out of tokens, they must be able to purchase more.

Proposed token conversion: **R1 = 1 token**.

Example packs:

- R50 = 50 tokens
- R100 = 100 tokens
- R250 = 250 tokens
- R500 = 500 tokens
- R1,000 = 1,000 tokens

For legal and payment compliance, the MVP should treat tokens as closed-loop entertainment credits unless and until a regulated gambling/legal framework is obtained.

## 4. Legal and Compliance Position

### 4.1 Critical Compliance Issue

The current design includes:

- Tokens purchased with real money.
- Players staking tokens.
- A winner receiving the combined stake.
- A game outcome based primarily on chance.

This combination creates legal risk because the product may be classified as gambling, interactive gaming, prize gaming, or a regulated game of chance.

### 4.2 MVP Compliance Recommendation

For MVP, the safest product design should be:

- Tokens are entertainment credits only.
- Tokens cannot be withdrawn for cash.
- Tokens cannot be transferred outside the game.
- Tokens cannot be redeemed for money, goods, prizes, discounts, or services.
- Token purchases are final, subject to consumer protection and refund policy.
- The game is presented as entertainment, not income generation.
- Age gate may still be considered.
- Terms of service must prohibit attempts to sell or trade accounts/tokens.

### 4.3 Regulated Version

If the business wants users to win tokens with actual cash value, withdraw balances, redeem prizes, or play for anything of monetary value, the product must not launch before legal review and, where required, licensing approval.

The regulated version would require:

- Gambling-law opinion.
- Provincial and national regulatory review.
- Payment processor approval.
- KYC and age verification.
- AML controls.
- Responsible gaming tools.
- Self-exclusion features.
- Transaction monitoring.
- Audit logs.
- Fairness certification.
- RNG or game integrity testing.
- Clear terms and conditions.

## 5. Target Users

### 5.1 Primary Users

- **Casual competitive players:** Players who enjoy quick, competitive, low-friction games.
- **Friends and social challengers:** Users who want to challenge friends directly.
- **Mobile-first users:** Players who want short, visually satisfying gameplay sessions on their phones.
- **Chance-game enthusiasts:** Users who enjoy suspense, guessing, bluffing, and luck-based mechanics.

### 5.2 Secondary Users

- **Solo players:** Players who want to play instantly against AI without waiting for matchmaking.
- **Streamers and content creators:** The game’s cinematic reveals, streaks, and reactions may make it suitable for short-form content.

## 6. Game Modes

### 6.1 MVP Game Modes

#### Mode 1: Play vs AI

The user plays against an AI opponent. This mode is mandatory for the MVP because it allows the user to play immediately even when no other live players are available.

AI mode should support:

- Instant match start.
- Alternating hider/guesser roles.
- Adjustable difficulty.
- Token staking.
- Win/loss effects.
- Streak tracking.

#### Mode 2: Private 2-Player Match

A player creates a room and invites another player using a link or room code.

Required functionality:

- Create room.
- Share invite link.
- Join room.
- Ready-up screen.
- Real-time round flow.
- Role switching.
- Token settlement.

#### Mode 3: Public Matchmaking

The system pairs a player with another available player.

Required functionality:

- Find match button.
- Waiting state.
- Match found confirmation.
- Countdown into cinematic intro.
- Anti-disconnect handling.

Public matchmaking may be included in MVP if development capacity allows, but the true MVP can launch with AI mode and private rooms first.

## 7. Gameplay Rules

### 7.1 Board Setup

Each round has:

- 3 half coconuts.
- 1 hidden ball.
- 2 players.
- 10-token contribution from each player.
- 20-token round pot.

### 7.2 Hiding Phase

The hider sees the ball and selects one coconut.

Requirements:

- The guesser must not see the hider’s selection.
- Selection must be stored server-side.
- The client must not expose the answer in browser-accessible state.
- Hider receives visual confirmation after selecting.

### 7.3 Shuffle Phase

After the ball is placed:

- Coconuts animate.
- Camera moves dynamically.
- The animation should create suspense.
- The animation should not alter the true ball location unless the game intentionally supports real shuffling.
- The final position must correspond to the server-verified result.

There are two possible approaches:

- **Option A: Cosmetic Shuffle** — The hider selects a coconut, and the coconut movement is purely cinematic. The ball remains under the selected coconut. This is simpler and better for MVP.
- **Option B: True Shuffle** — The hider selects the starting coconut, then the system shuffles the coconuts according to a server-generated sequence. The guesser must track the movement. This introduces more skill and reduces pure chance, but requires better animation accuracy and fairness validation.

Recommended MVP choice: **Option A for MVP. Option B for Version 2.**

### 7.4 Guessing Phase

The guesser selects one coconut.

Requirements:

- Only one selection allowed.
- Selection is locked once made.
- Timer should apply to prevent stalling.
- If the timer expires, the guesser automatically loses the round.

Recommended timer: **15 seconds**.

### 7.5 Reveal Phase

The selected coconut lifts, flips, breaks open, glows, or slides away to reveal whether the ball is present.

Correct guess:

- Ball revealed.
- Positive visual burst.
- Player win animation.
- Token pot moves toward winner.
- Streak indicator updates.

Incorrect guess:

- Empty coconut revealed first.
- Then correct coconut reveals the hidden ball.
- Player loss animation.
- Opponent win animation.
- Token pot moves toward hider.

### 7.6 Settlement Phase

The server updates balances.

Correct guess:

- Guesser receives 20 tokens.
- Hider receives 0 tokens from the pot.

Incorrect guess:

- Hider receives 20 tokens.
- Guesser receives 0 tokens from the pot.

The next round begins only if both players have enough tokens to stake.

## 8. Token Economy

### 8.1 Starting Tokens

Each account starts with **1,000 free tokens**. These are promotional tokens.

### 8.2 Round Stake

Default stake: **10 tokens per player**.

Total pot: **20 tokens**.

### 8.3 Token Purchase

When a player has insufficient tokens:

- Show “Insufficient Tokens” modal.
- Display token packs.
- Allow PayPal purchase subject to compliance.
- Credit purchased tokens after successful payment confirmation.

### 8.4 Token Pack Design

| Pack | Price | Tokens | Bonus |
| --- | ---: | ---: | ---: |
| Starter | R50 | 50 | 0 |
| Casual | R100 | 100 | 0 |
| Popular | R250 | 260 | 10 bonus |
| Premium | R500 | 540 | 40 bonus |
| High Roller | R1,000 | 1,100 | 100 bonus |

Bonus tokens should be reviewed legally because promotional value can affect consumer disclosures and gaming classification.

### 8.5 Token Restrictions for MVP

For MVP safety:

- Tokens cannot be withdrawn.
- Tokens cannot be sold.
- Tokens cannot be transferred to another user.
- Tokens have no cash value.
- Tokens are used only for gameplay.
- Purchased tokens and free tokens may be tracked separately.
- Refund policy must be clear.

## 9. Multiplayer Requirements

### 9.1 Real-Time Communication

The game requires low-latency updates.

Recommended technology:

- WebSockets for live game events.
- Server-authoritative game state.
- Client-side animation synced to server events.

### 9.2 Match State

Each match should include:

- Match ID.
- Player 1 ID.
- Player 2 ID or AI opponent ID.
- Current round number.
- Current hider.
- Current guesser.
- Stake amount.
- Pot amount.
- Hidden coconut index.
- Guesser selection.
- Round status.
- Player balances.
- Win/loss result.
- Timeout status.
- Disconnect status.

### 9.3 Match Lifecycle

Match states:

1. Created
2. Waiting for opponent
3. Opponent joined
4. Ready check
5. Intro cinematic
6. Stake locked
7. Hiding phase
8. Shuffle phase
9. Guessing phase
10. Reveal phase
11. Settlement phase
12. Role switch
13. Next round
14. Match ended

### 9.4 Disconnect Handling

If a player disconnects:

- Pause for 20 seconds.
- Attempt automatic reconnection.
- If the player returns, continue.
- If the hider disconnects before placing the ball, cancel the round and refund stakes.
- If the guesser disconnects during guessing phase, apply timeout loss after grace period.
- If either player disconnects during settlement, server must still complete settlement.

### 9.5 Anti-Cheat Requirements

The game must be server-authoritative.

Rules:

- The hidden ball position must never be sent to the guesser before reveal.
- Clients must not determine winners.
- Clients must not update token balances directly.
- All token changes must happen server-side.
- All important events must be logged.
- WebSocket messages must be validated.
- Match replay data should be stored for disputes.

## 10. AI Opponent Requirements

### 10.1 Purpose

AI opponent mode ensures users can play immediately without waiting for another player.

### 10.2 AI Personality

The AI should feel like a real opponent, not a basic bot.

Possible AI characters:

1. Master Lao — calm, wise, subtle.
2. The Red Lotus Gambler — theatrical and confident.
3. Jade Fox — playful, mischievous.
4. Iron Panda — humorous and expressive.

### 10.3 AI Difficulty

MVP should include at least three levels:

| Difficulty | Behaviour |
| --- | --- |
| Easy | Random guesses, obvious hiding patterns |
| Normal | Random with mild behavioural weighting |
| Hard | Uses player history and pattern detection |

### 10.4 AI Guessing Logic

For MVP, the AI can guess using weighted probabilities.

Factors:

- Player’s previous coconut choices.
- Repeated patterns.
- Streak behaviour.
- Tendency to switch after loss.
- Tendency to repeat after win.

The AI should never cheat by reading the hidden answer.

### 10.5 AI Hiding Logic

AI chooses where to hide the ball using:

- Random selection.
- Anti-pattern logic.
- Occasional repeated placement.
- Difficulty-based unpredictability.

### 10.6 AI Fairness Requirement

The AI must not access information unavailable to a human player. Hard mode should feel intelligent because it tracks behaviour, not because it cheats.

## 11. Visual Direction

### 11.1 Art Style

The game should have a premium oriental-inspired visual identity.

Style keywords:

- Luxurious.
- Cinematic.
- Lantern-lit.
- Polished wood.
- Jade accents.
- Gold trim.
- Silk textures.
- Ornamental patterns.
- Mist and particle effects.
- Warm dramatic lighting.
- High-end mobile casino aesthetic, but legally positioned as entertainment unless licensed.

### 11.2 Board Design

The game board should feel like a ceremonial duelling table.

Elements:

- Dark polished wooden table.
- Gold-inlaid circular play area.
- Three coconut positions.
- Subtle engraved patterns.
- Floating embers or petals.
- Background lanterns.
- Red silk cloth details.
- Jade token counters.
- Animated shadows.
- Soft cinematic depth of field.

### 11.3 Coconut Design

The coconuts must look physically tactile and premium.

Requirements:

- Three half coconuts.
- Outer shell with realistic rough texture.
- Inner shell with creamy coconut flesh rim.
- Slight imperfections for realism.
- Subtle idle wobble.
- Shadow contact on the board.
- Lift, slide, spin, and reveal animations.

### 11.4 Ball Design

The ball should be more visually interesting than a plain ball.

Options:

- Glowing pearl.
- Jade orb.
- Golden bead.
- Small dragon-eye sphere.
- Luminous marble.

Recommended MVP design: **a glowing jade-and-gold orb**. This fits the oriental theme and gives strong visual feedback during reveal.

## 12. Animation Requirements

### 12.1 Round Intro Cinematic

Each round starts with a cinematic 3D intro.

Intro sequence:

1. Camera fades in from black.
2. Slow glide over lantern-lit board.
3. Tokens slide into the centre.
4. Three coconuts drop or rotate into position.
5. The ball glows briefly.
6. Camera settles into playable angle.
7. “Round Begins” or “Your Turn” appears.

Target duration: **3 to 5 seconds**.

The intro must be skippable after the user has seen it several times, or it should become shorter after the first round to avoid frustration.

### 12.2 Ball Placement Animation

When the hider selects a coconut:

- Ball rolls or floats under the selected coconut.
- Coconut lowers over the ball.
- Glow fades.
- Opponent sees only a suspense animation, not the actual placement.

### 12.3 Coconut Movement Animation

After placement:

- Coconuts slide across predefined paths.
- They may spin, cross over, or rotate.
- Movement must look smooth and physically plausible.
- Motion blur can be used.
- The camera may slightly track the movement.
- Sound effects should emphasize motion.

MVP recommendation: **use 3 to 5 shuffle animation patterns**.

### 12.4 Correct Guess Effect

When the guess is correct:

Visual effects:

- Coconut flips open.
- Jade orb glows intensely.
- Golden particle burst.
- Dragon-shaped light trail.
- Winner’s avatar glows.
- Tokens fly toward winner.
- “Correct!” appears.
- Streak meter pulses.

Sound effects:

- Gong hit.
- Rising chime.
- Token collection sound.
- Crowd or mystical cheer.

### 12.5 Wrong Guess Effect

When the guess is wrong:

Visual effects:

- Selected coconut opens empty.
- Dust puff or dull thud.
- Board darkens slightly.
- Correct coconut glows ominously.
- Correct coconut opens to reveal the ball.
- Tokens slide toward opponent.
- “Missed!” or “Wrong Coconut!” appears.

Sound effects:

- Low drum.
- Wooden thud.
- Soft disappointed sting.
- Opponent win sound.

### 12.6 Hot Streak Effects

Hot streaks should escalate visually.

| Streak | Indicator |
| ---: | --- |
| 2 wins | Small flame icon |
| 3 wins | “Hot Streak” banner |
| 5 wins | Board glow intensifies |
| 7 wins | Dragon aura animation |
| 10 wins | Legendary streak cinematic |

Hot streak should include:

- Player badge.
- Animated fire/energy.
- Sound cue.
- Optional chat/emote trigger.
- Match history indicator.

## 13. User Interface Requirements

### 13.1 Main Menu

Required buttons:

- Play vs AI
- Play Online
- Create Private Match
- Join Match
- Buy Tokens
- Leaderboard
- Profile
- Settings
- Help / Rules

### 13.2 Player HUD

During gameplay, show:

- Player name.
- Avatar.
- Token balance.
- Current stake.
- Current pot.
- Role: Hider or Guesser.
- Round number.
- Win streak.
- Timer.
- Connection status.

### 13.3 Game Board UI

The board must show:

- Three selectable coconuts.
- Clear hover or tap indication.
- Disabled state when it is not the player’s turn.
- Turn instruction text.
- Pot display in the centre.
- Animated token pile.

### 13.4 Token Purchase UI

When buying tokens:

- Display token packs clearly.
- Show price in Rand.
- Show token amount.
- Show payment method.
- Display terms:
  - Tokens are in-game credits.
  - Tokens have no cash value.
  - Tokens cannot be withdrawn.
  - Purchases subject to terms.
- Confirm purchase before payment.
- Show success/failure state.

### 13.5 Result Screen

After each round:

- Show winner.
- Show result.
- Show token movement.
- Show updated balances.
- Show streak update.
- Show “Next Round” countdown.

## 14. Player Account Requirements

### 14.1 Authentication

MVP options:

- Email and password.
- Google login.
- Apple login.
- Guest mode with upgrade prompt.

Recommended MVP:

- Guest play for AI mode.
- Account required for multiplayer and purchases.

### 14.2 Profile

Profile should include:

- Username.
- Avatar.
- Token balance.
- Total games played.
- Wins.
- Losses.
- Win rate.
- Best streak.
- Current streak.
- Favourite coconut position, optional and hidden from opponents.
- Match history.

### 14.3 Wallet

Wallet should show:

- Free tokens.
- Purchased tokens.
- Total balance.
- Purchase history.
- Gameplay transaction history.
- Refund status, where applicable.

## 15. Payments

### 15.1 Payment Provider

Requested provider: **PayPal**.

Payment integration must support:

- Token pack purchase.
- Payment confirmation.
- Webhook verification.
- Failed payment handling.
- Duplicate webhook protection.
- Refund handling.
- Transaction logs.

### 15.2 Payment Flow

1. User selects token pack.
2. User confirms purchase.
3. User is redirected to or presented with PayPal checkout.
4. PayPal processes payment.
5. Backend receives payment webhook.
6. Backend verifies transaction.
7. Backend credits tokens.
8. User sees updated balance.

### 15.3 Payment Security

Requirements:

- Never credit tokens based only on front-end success.
- Always verify payment server-side.
- Store PayPal transaction ID.
- Prevent duplicate token crediting.
- Log payment status.
- Implement fraud checks for abnormal purchases.

### 15.4 Important Payment Restriction

If the game is legally classified as gambling or prize gaming, ordinary payment processing may not be available. The product may require payment-provider approval, legal licensing, and jurisdictional blocking.

## 16. Backend Requirements

### 16.1 Core Services

Required backend services:

- Authentication service.
- User profile service.
- Token wallet service.
- Matchmaking service.
- Game session service.
- AI opponent service.
- Payment service.
- Transaction ledger service.
- Anti-cheat service.
- Analytics service.
- Admin dashboard.

### 16.2 Token Ledger

Every token movement must be recorded.

Ledger entries:

- User ID.
- Transaction ID.
- Transaction type.
- Amount.
- Balance before.
- Balance after.
- Match ID, if applicable.
- Payment ID, if applicable.
- Timestamp.
- Status.

Transaction types:

- Starting token grant.
- Purchase.
- Stake lock.
- Stake refund.
- Round win.
- Round loss.
- Admin adjustment.
- Bonus grant.

### 16.3 Game State Storage

Each game round must store:

- Match ID.
- Round ID.
- Hider ID.
- Guesser ID.
- Hidden coconut.
- Guess selected.
- Stake amount.
- Pot amount.
- Result.
- Started at.
- Ended at.
- Timeout status.
- Animation seed.
- Server verification hash, optional for transparency.

### 16.4 Server Authority

The backend must be the final authority on:

- Hidden coconut position.
- Valid selections.
- Timing.
- Round winner.
- Token balances.
- Match outcome.

## 17. Frontend Requirements

### 17.1 Recommended Frontend Stack

Recommended stack:

- React or Next.js.
- Three.js or React Three Fiber for 3D.
- WebSockets for real-time play.
- Zustand or Redux for local state.
- Tailwind or custom CSS for UI.
- GSAP or Framer Motion for UI animation.

### 17.2 3D Rendering Requirements

The game should use a 3D scene for the board.

Required 3D components:

- Board.
- Coconuts.
- Ball.
- Tokens.
- Lighting.
- Camera.
- Particles.
- Environment background.
- Animations.

### 17.3 Mobile Responsiveness

The game must be playable on:

- Desktop browsers.
- Mobile Safari.
- Mobile Chrome.
- Tablet browsers.

Mobile requirements:

- Tap-friendly coconuts.
- Portrait and landscape support.
- Performance optimization.
- Reduced animation quality mode.
- Stable frame rate.

### 17.4 Performance Targets

Minimum targets:

- Desktop: 60 FPS.
- Modern mobile: 30 FPS minimum, 60 FPS preferred.
- Initial load under 5 seconds on decent connection.
- First playable interaction under 8 seconds.
- WebSocket latency under 200ms where possible.

## 18. Sound and Music

### 18.1 Music Direction

The soundtrack should support the oriental theme.

Style:

- Soft drums.
- Strings.
- Flutes.
- Ambient temple textures.
- Rising tension during selection.
- Dramatic sting during reveal.

### 18.2 Sound Effects

Required sound effects:

- Coconut slide.
- Coconut spin.
- Coconut lift.
- Ball glow.
- Token stake.
- Token win.
- Correct guess.
- Wrong guess.
- Timer countdown.
- Hot streak activation.
- Match found.
- Payment success.

### 18.3 Audio Controls

Settings must include:

- Master volume.
- Music volume.
- Sound effects volume.
- Mute all.

## 19. Progression and Retention

### 19.1 Daily Bonus

Optional MVP feature:

- Daily login token bonus.
- Example: 50 free tokens per day.
- Prevent abuse with account and device checks.

### 19.2 Streak Rewards

Possible reward system:

- 3-win streak: small bonus animation.
- 5-win streak: title badge.
- 10-win streak: cosmetic unlock.

For legal safety, avoid awarding cash-value rewards.

### 19.3 Cosmetics

Cosmetics can include:

- Coconut skins.
- Board themes.
- Ball designs.
- Avatar frames.
- Win animations.
- Emotes.

Cosmetics are safer monetisation than stake-based token sales and should be considered as a major revenue path.

## 20. Leaderboards

### 20.1 MVP Leaderboards

Leaderboards may include:

- Most wins.
- Best win streak.
- Highest win rate.
- Most games played.
- AI challenge records.

### 20.2 Leaderboard Anti-Abuse

Requirements:

- Minimum games threshold for win-rate leaderboard.
- Bot detection.
- Suspicious match detection.
- Friend-match farming detection.
- Admin moderation tools.

## 21. Admin Dashboard

The admin dashboard should allow operators to view and manage:

- Users.
- Token balances.
- Payment history.
- Match history.
- Disputes.
- Suspicious activity.
- AI difficulty settings.
- Token pack prices.
- Promotions.
- Banned users.
- System health.
- Revenue analytics.

Admin actions:

- Search user.
- View wallet ledger.
- Adjust balance with reason.
- Ban or suspend user.
- Refund purchase.
- Cancel match.
- Review dispute.
- Export logs.

## 22. Analytics Requirements

Track:

- Daily active users.
- Monthly active users.
- New registrations.
- Guest-to-account conversion.
- AI games played.
- Human-vs-human games played.
- Average session length.
- Token purchase conversion.
- Average revenue per paying user.
- Round win/loss distribution.
- Drop-off points.
- Payment failures.
- Disconnections.
- Most selected coconut.
- Streak frequency.
- User retention by cohort.

Key KPIs:

- Day 1 retention.
- Day 7 retention.
- Average games per session.
- Purchase conversion rate.
- Average revenue per user.
- Multiplayer match completion rate.
- AI mode engagement.
- Cost per acquired user.
- Lifetime value.

## 23. Responsible Play Features

Even if the MVP uses closed-loop entertainment tokens, the game should include responsible play tools because of the stake-and-loss structure.

Recommended features:

- Session time reminders.
- Purchase limits.
- Daily token spending limits.
- Cool-off period.
- Self-exclusion.
- Age gate.
- “Play responsibly” notice.
- Payment confirmation friction.
- Loss history visibility.

If the game becomes regulated gambling, these features become more important and may be mandatory.

## 24. MVP Scope

### 24.1 MVP Must-Have Features

The MVP must include:

1. Account creation.
2. Starting balance of 1,000 tokens.
3. Play vs AI.
4. Private 2-player rooms.
5. Three-coconut game board.
6. Hider selection.
7. Guesser selection.
8. Role switching.
9. 10-token stake per player.
10. 20-token pot settlement.
11. Token wallet.
12. Basic purchase flow.
13. Server-authoritative game state.
14. Basic 3D board.
15. Coconut movement animation.
16. Correct guess effects.
17. Wrong guess effects.
18. Hot streak indicator.
19. Match history.
20. Basic admin dashboard.

### 24.2 MVP Should-Have Features

1. Public matchmaking.
2. Multiple AI personalities.
3. Leaderboards.
4. Daily bonus.
5. Mobile optimization.
6. Multiple board environments.
7. Cosmetic unlocks.
8. Sound settings.
9. Payment webhooks.
10. Dispute logs.

### 24.3 MVP Nice-to-Have Features

1. True shuffle tracking mode.
2. Chat/emotes.
3. Spectator mode.
4. Tournaments.
5. Seasonal events.
6. Player clans.
7. Advanced anti-cheat.
8. Animated avatars.
9. Replay system.
10. Web3 or blockchain provably fair layer, only if legally appropriate.

## 25. Version 2 Features

Version 2 may include:

- Public ranked matchmaking.
- Skill-based shuffle mode.
- Cosmetic marketplace.
- Tournament mode.
- Friend list.
- Real-time chat.
- Seasonal battle pass.
- Advanced AI opponents.
- Replay sharing.
- Creator mode.
- More board themes.
- More cinematic intros.
- Progressive visual streak states.
- Mobile app versions.
- Push notifications.
- Advanced analytics dashboard.

## 26. User Stories

### 26.1 New Player

As a new player, I want to receive 1,000 starting tokens so that I can try the game immediately.

### 26.2 AI Player

As a player, I want to play against AI so that I do not need to wait for another person.

### 26.3 Multiplayer Player

As a player, I want to invite a friend with a link so that we can play against each other.

### 26.4 Hider

As the hider, I want to choose which coconut hides the ball so that I can challenge my opponent.

### 26.5 Guesser

As the guesser, I want to select one coconut so that I can try to win the pot.

### 26.6 Winner

As a winner, I want strong visual and sound effects so that winning feels satisfying.

### 26.7 Losing Player

As a losing player, I want the result to be clear so that I understand why I lost.

### 26.8 Returning Player

As a returning player, I want to see my streaks, stats, and token balance so that I feel progression.

### 26.9 Paying Player

As a paying player, I want to buy tokens easily so that I can continue playing.

### 26.10 Admin

As an admin, I want to inspect match and wallet logs so that I can resolve disputes and detect abuse.

## 27. Acceptance Criteria

### 27.1 Round Creation

Given two players have enough tokens, when a new round starts, then 10 tokens must be locked from each player and the pot must show 20 tokens.

### 27.2 Hiding

Given it is Player 1’s hiding turn, when Player 1 selects a coconut, then the hidden position must be stored server-side and not exposed to Player 2.

### 27.3 Guessing

Given it is Player 2’s guessing turn, when Player 2 selects a coconut, then the selection must be locked and the reveal phase must begin.

### 27.4 Correct Guess

Given Player 2 chooses the coconut with the ball, then Player 2 must receive the 20-token pot and Player 1 must receive nothing from that pot.

### 27.5 Wrong Guess

Given Player 2 chooses the wrong coconut, then Player 1 must receive the 20-token pot and Player 2 must receive nothing from that pot.

### 27.6 Role Switch

Given a round has ended, then the hider and guesser roles must switch for the next round.

### 27.7 Insufficient Tokens

Given a player has fewer than 10 tokens, when the next round attempts to start, then the game must block the round and show the token purchase prompt.

### 27.8 AI Mode

Given the player selects AI mode, when the match starts, then the AI must alternate roles with the player and play according to selected difficulty.

### 27.9 Token Purchase

Given a user completes payment successfully, then the backend must verify the payment before crediting tokens.

### 27.10 Disconnection

Given a player disconnects, then the system must apply the defined grace period and resolve or refund the round according to match state.

## 28. Technical Architecture

### 28.1 Suggested Stack

Frontend:

- Next.js
- React Three Fiber
- Three.js
- Tailwind CSS
- Framer Motion or GSAP
- WebSocket client

Backend:

- Node.js with NestJS or Express
- WebSocket gateway
- PostgreSQL
- Redis for real-time match state
- Prisma ORM
- PayPal server-side integration
- Queue system for payment events and match settlement

Infrastructure:

- Vercel or Cloudflare Pages for frontend
- Render, Railway, Fly.io, AWS, or Google Cloud for backend
- Managed PostgreSQL
- Redis Cloud
- Object storage for assets
- CDN for 3D models and textures

### 28.2 Data Models

Core models:

- User
- Wallet
- WalletTransaction
- Match
- Round
- Payment
- TokenPack
- AIProfile
- UserStats
- LeaderboardEntry
- AdminActionLog

### 28.3 Security

Requirements:

- HTTPS only.
- Secure authentication.
- Rate limiting.
- WebSocket authentication.
- Server-side validation.
- Anti-replay protection.
- Payment webhook signature verification.
- SQL injection protection.
- Input sanitization.
- Audit logs.
- Role-based admin access.

## 29. Game Fairness

### 29.1 Server-Verified Results

The server must determine and store the hidden coconut.

### 29.2 Optional Provably Fair System

For future versions, the game may include a provably fair mechanism:

- Server seed.
- Client seed.
- Round nonce.
- Hash commitment before reveal.
- Seed reveal after round.
- User can verify that the outcome was not altered.

This is more important if real-money or regulated gameplay is pursued.

## 30. Risk Register

| Risk | Severity | Mitigation |
| --- | --- | --- |
| Gambling classification | Critical | Legal review, closed-loop tokens, no withdrawals |
| Payment provider rejection | High | Confirm PayPal approval before launch |
| Cheating through client inspection | High | Server-authoritative state |
| Low gameplay depth | Medium | Premium visuals, streaks, AI, cosmetics |
| Multiplayer liquidity problem | High | AI mode and private rooms |
| Token abuse | High | Wallet ledger and fraud monitoring |
| User addiction concerns | High | Responsible play features |
| Poor mobile performance | Medium | Optimized 3D assets and quality settings |
| Disputes over results | Medium | Match logs and replay data |
| Regulatory change | High | Ongoing legal monitoring |

## 31. Design Priorities

The game must prioritize:

1. Trust.
2. Visual polish.
3. Fast gameplay.
4. Smooth multiplayer.
5. Secure token accounting.
6. Legal compliance.
7. Mobile performance.
8. Replayability.
9. Emotional feedback.
10. Easy onboarding.

## 32. MVP Launch Checklist

Before launch:

- Legal opinion completed.
- Payment provider approval confirmed.
- Terms and conditions drafted.
- Privacy policy drafted.
- Token policy drafted.
- Refund policy drafted.
- Responsible play language added.
- Server-authoritative game complete.
- AI mode working.
- Private rooms working.
- Token ledger tested.
- Payment webhook tested.
- Admin dashboard working.
- Anti-cheat checks implemented.
- Mobile performance tested.
- Visual effects optimized.
- Analytics installed.
- Error logging installed.
- Security review completed.

## 33. Open Questions

1. Will tokens be withdrawable or only used inside the game?
2. Will users be allowed to transfer tokens to each other?
3. Will the game be launched in South Africa only or internationally?
4. Will the business seek gambling/game-of-chance licensing?
5. Should the MVP use cosmetic shuffle or true shuffle?
6. Should users be able to change the stake amount?
7. Should private matches count toward leaderboards?
8. Should AI games affect public stats?
9. Should the game include chat?
10. Should there be an age restriction from launch?

## 34. Recommended MVP Build Approach

### Phase 1: Prototype

Build a single-player AI prototype with:

- 3D board.
- Three coconuts.
- Ball placement.
- Guessing.
- Reveal.
- Win/loss effects.
- Basic token balance.

### Phase 2: Game Server

Add:

- Server-authoritative rounds.
- Wallet ledger.
- Match state.
- AI logic.
- Round settlement.

### Phase 3: Multiplayer

Add:

- Private rooms.
- WebSockets.
- Role switching.
- Disconnection handling.
- Match history.

### Phase 4: Visual Polish

Add:

- Cinematic intro.
- Coconut movement animations.
- Correct/wrong effects.
- Hot streak indicators.
- Sound design.
- Mobile optimization.

### Phase 5: Payments and Admin

Add:

- Token packs.
- PayPal integration.
- Payment webhooks.
- Admin dashboard.
- Transaction logs.

### Phase 6: Compliance and Launch

Complete:

- Legal review.
- Payment approval.
- Terms.
- Privacy policy.
- Token policy.
- Responsible play tools.
- Security review.

## 35. Final Product Positioning

Coconuts should be positioned as a premium cinematic guessing duel, not merely a shell game. The base mechanic is simple, but the product experience must feel dramatic, beautiful, and addictive in the non-clinical sense: fast rounds, satisfying reveals, visible streaks, and a luxurious visual identity.

The MVP should focus on:

- Instant AI play.
- Private multiplayer.
- Closed-loop tokens.
- Excellent 3D presentation.
- Secure token accounting.
- Strong legal guardrails.

The product can later evolve into a deeper competitive platform with ranked play, tournaments, cosmetics, seasonal events, and more sophisticated AI opponents.
