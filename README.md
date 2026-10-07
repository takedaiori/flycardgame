# 🃏 飞卡 FlyCard，一款九零后孩童时代游戏的数字版本

试玩地址：https://takedaiori.github.io/flycardgame/

> **把童年摔在地上的那口气，捡回来。**

小时候，你有没有蹲在地上，用一张卡去砸另一张卡，砸翻面了，那张卡就归你了？放学路上、教室门口、跳远沙坑，随便找一块平地就是战场。小卖部两毛钱一包干脆面，里面那张卡片，就是全部的“本钱”。

**《飞卡》就是那个游戏的电脑版。** 但做了一些“适合电脑游戏直觉”的改动：不用蹲在地上，不用使劲甩胳膊怕把牌甩飞，不用因为地不平而吃亏。取而代之的是**拖拽 → 松手**，卡牌贴着牌桌直线滑出去，然后……等它停稳，看它盖住了对方多少。

---

## 🎯 核心玩法

你和 AI 各控制一张扑克牌，在**同一张牌桌**上轮流把牌滑出去。

> **让你的牌最终覆盖对方的牌。覆盖率达到 67%，赢下本局。**

不是“打翻面”，而是“盖上去”——这是从童年地面游戏到电脑游戏最直觉的一次改动。地面上卡牌翻不翻面，一半靠力度，一半靠地砖缝和运气。俯视牌桌上没有地砖缝，卡牌只会沿着直线滑行、减速、停下。**结果变得可控，手感变成了真正的技术。**

三局两胜制。如果某一投盖到了 **99.01% 以上**，卡牌会自动吸附到 100%，触发 **完美覆盖**，直接赢下整场比赛，不管当前比分是多少。

---

## 🕹️ 怎么玩

1. **部署**：开局牌桌是空的。你先把牌拖进左半边部署区，松手滑入。部署阶段有一条中线挡板，你不能越过它。
2. **投掷**：按住你的牌，**向你想推出的反方向拖拽**，拖得越远力度越大，松手就滑出去。
3. **滑行**：卡牌贴着桌面直线减速，撞到木质挡边会大幅减速反弹，最多有效反弹一次。
4. **判定**：滑行过程中不判胜负。**等牌停稳之后，才计算覆盖率。**
5. **额外投掷**：如果你盖到了对方一部分（但不到 67%），而且你的牌在上面，你会获得一次额外投掷——但**不能继续盖**，必须先把牌推离对方的覆盖区域，重新拉开距离。

最后一条规则看起来有点绕，但它是整个游戏最有意思的地方。它阻止了“贴上去反复微调直到蹭到 67%”这种无脑打法，逼你真正考虑**角度和力度的取舍**。

---

## ⚙️ 物理特性

虽然灵感来自童年打卡，但《飞卡》的物理不是“甩出去听天由命”。

| 特性 | 表现 |
|---|---|
| **无重力** | 俯视视角，卡牌贴着桌面水平滑行，不会下坠 |
| **库仑摩擦** | 恒定减速度减速，轨迹是一条**直线**，滑行距离与初速平方成正比 |
| **挡边阻尼** | 撞边后法向速度只剩 34%，切向保留 78%，反弹是补救手段不是主力 |
| **克制旋转** | 推出去时带一点小幅旋转，快速衰减，纯视觉，不影响落点 |
| **纸片接触** | 两张牌可以叠压接触，但**绝不弹开**，最大滑动不超过牌尺寸的 0.5% |

直线轨迹带来的手感很纯粹：**你推多重，它滑多远，偏了多少，一目了然。** 没有弹球一样的乱蹦，没有台球一样的对撞。就是纸，在桌布上滑。

---

## 🤖 AI 是个“明显更弱的对手”

这一点很重要。

AI 的存在不是为了让你觉得“我在和一个高手对弈”。**AI 的存在是为了让你有犯错空间。**

- AI 超过一半的投掷会**完全打空**，覆盖率 0%
- AI 命中率（≥67%）大约 **11%～14%**，而玩家熟练后能到 **49%**
- AI 平均覆盖率只有 20% 出头，玩家可以到 51%

AI 会方向大偏、力度不足、力度过大、选一条明显更差的路线。它偶尔（大约 7%）会扔出一记漂亮的覆盖，但大多数时候，**你失手了，AI 也抓不住。**

这才是休闲桌面玩具该有的宽容度。

---

## 🧱 技术栈

- **HTML5 Canvas + 原生 JavaScript + CSS**
- **单个 HTML 文件即可运行**
- 无需服务器、无需数据库、无需账号、无需第三方游戏引擎

打开浏览器就能玩，关掉浏览器就结束。

---

## 🚧 当前状态

MVP 开发中。第一版优先验证的事情只有一件：

> **“把扑克牌推过去盖住另一张扑克牌”到底好不好玩。**

如果你小时候也在水泥地上蹲过，如果你也记得那种“差一点就翻过来了”的不甘心——试试看，这次不用蹲着了。🂡 → 🂱


# 🃏 FlyCard

> **Pick up the grudge you left on the playground.**

If you grew up in the '90s, you probably remember this: squatting on the concrete after school, slamming one card down onto another, hoping to flip it over. If it flipped, that card was yours. A cheap pack of instant noodles from the corner store came with one card inside — and that card was your entire bankroll.

**FlyCard is that game, rebuilt for the computer.** With a few changes that make sense for a digital game: no squatting, no wild arm swings that send your card flying, no bad luck from uneven ground. Instead, it's just **drag → release.** Your card glides in a straight line across a tabletop, then... you wait for it to stop and see how much of your opponent's card it covers.

---

## 🎯 Core Rules

You and the AI each control one playing card on the **same tabletop**, taking turns sliding your card.

> **Cover your opponent's card. Reach 67% coverage and win the round.**

Not "flip it over" but "cover it" — the most intuitive translation from the playground to a computer game. On concrete, whether a card flipped depended half on force and half on cracks and luck. On a top-down table, there are no cracks. Cards glide in straight lines, slow down, and stop. **The outcome becomes controllable, and touch becomes real skill.**

Best of three. If a shot covers **99.01% or more**, the card snaps to 100%, triggering **Perfect Coverage** and instantly winning the entire match, no matter the current score.

---

## 🕹️ How to Play

1. **Deployment** — The table starts empty. Drag your card into the left-half deployment zone and release to slide it in. A center barrier exists during deployment; you cannot cross it.
2. **Throw** — Press and hold your card, then **drag in the opposite direction** of where you want it to go. Longer drag = more force. Release.
3. **Slide** — The card glides along the table, decelerating in a straight line. Hitting the wooden rail causes a big speed loss and a bounce; at most one effective bounce.
4. **Judge** — No win/loss is calculated during sliding. **Only after the card stops is coverage measured.**
5. **Extra Throw** — If you partially cover the opponent's card but stay under 67%, and your card is on top, you get an extra throw. But **you cannot keep covering.** You must push your card away from the opponent's coverage area and reset the distance.

That last rule sounds fiddly, but it's the most interesting part of the game. It prevents "stick to the opponent and micro-adjust until 67%," forcing you to think about **trade-offs between angle and force.**

---

## ⚙️ Physics

Although inspired by playground card-slapping, FlyCard's physics isn't "flick and pray."

| Feature | Behavior |
|---|---|
| **No Gravity** | Top-down view; cards slide horizontally on the table and never fall. |
| **Coulomb Friction** | Constant deceleration; trajectory is a **straight line**; stopping distance is proportional to the square of initial speed. |
| **Rail Damping** | After hitting a rail, normal velocity drops to 34%, tangential velocity keeps 78%. Bounces are a recovery tool, not a main strategy. |
| **Restrained Spin** | A slight spin on release, quickly damped, purely visual, and does not affect the landing point. |
| **Paper Contact** | Cards can overlap and touch but **never bounce apart**; max slide is 0.5% of card size. |

A straight-line trajectory feels pure: **how hard you push, how far it goes, how much you miss — all clear.** No pinball chaos, no billiard collisions. Just paper sliding on cloth.

---

## 🤖 The AI Is Meant to Be Weaker

This part matters.

The AI is not there to make you feel like you're playing a grandmaster. **The AI is there to give you room to make mistakes.**

- Over half of AI throws **completely miss** — 0% coverage.
- AI hit rate (≥67%) is around **11%–14%**; a skilled player can reach **49%**.
- AI average coverage is just over 20%; a player can reach 51%.

The AI will misjudge direction, underpower, overpower, and choose a clearly worse line. Occasionally — about 7% of the time — it lands a beautiful cover. But most of the time, **when you miss, the AI misses too.**

That's the forgiveness a casual tabletop toy should have.

---

## 🧱 Tech Stack

- **HTML5 Canvas + vanilla JavaScript + CSS**
- **Runs as a single HTML file**
- No server, no database, no account, no third-party game engine

Open it in a browser and play. Close it and you're done.

---

## 🚧 Current Status

MVP in development. The first version only needs to answer one question:

> **Is "slide a playing card across a table to cover another playing card" actually fun?**

If you ever squatted on concrete as a kid, if you still remember that sting of "so close to flipping it" — give it a try. This time, you don't have to squat. 🂡 → 🂱
