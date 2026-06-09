# Test Scenarios for Need Extractor

Each test scenario provides an input and expected checks. To validate the skill, feed each input to Codex inside a thread with the need-extractor skill available, and verify the output meets the checks.

## Test 1: Obvious trigger — "something feels off"

**Input:**
> 我感觉我的项目方向不对劲，但说不出来哪里不对。我在做一个帮助设计师找灵感的应用，已经做了一半了，但现在觉得越来越没动力。我不知道自己到底想要什么。

**Expected checks:**
- [ ] Output contains all 7 facets
- [ ] Does NOT start with empathy padding
- [ ] Does NOT suggest specific tools (e.g., "try Pinterest API", "use Dribbble data")
- [ ] Does NOT design a system or feature set
- [ ] Facet 5 names a specific contradiction, not a generic statement
- [ ] Facet 7 is a single action completable in one sitting
- [ ] Ends with the invitation line

## Test 2: "Is this overkill" — proportionality doubt

**Input:**
> 我想给我的个人博客加一个 A/B 测试系统，想看看哪些标题更吸引人。但我知道就我一个人写，一个月可能就几百个访问。这是不是多此一举？

**Expected checks:**
- [ ] Output contains all 7 facets
- [ ] Facet 6 explicitly calls out the A/B testing system as a pseudo-need
- [ ] Does not list A/B testing tools
- [ ] Facet 7 is a simpler alternative to A/B testing (e.g., ask a friend)

## Test 3: Choice paralysis — tech stack

**Input:**
> 我不确定我的 side project 用什么数据库。看了 PostgreSQL、SQLite、DuckDB、MongoDB、Supabase……每看一个就觉得"这个也行"。我已经花了一个周末对比了，越想越烦。"

**Expected checks:**
- [ ] Output contains all 7 facets
- [ ] Does NOT include a database comparison table
- [ ] Facet 5 names the contradiction correctly (using research to avoid building)
- [ ] Facet 6 calls out the comparison activity itself as something that can be cut
- [ ] Facet 7 names ONE concrete action (not "use X database")

## Test 4: Long conversation dump

**Input:**
[Take a 10-20 turn conversation where a user discusses an idea with someone, going back and forth between wanting simplicity and wanting features]

**Expected checks:**
- [ ] Output references specific phrases from the conversation
- [ ] Loaded references/long_conversation.md during analysis
- [ ] Facet 5 identifies the contradiction visible across multiple turns
- [ ] Output is not a conversation summary — it is need extraction

## Test 5: Negative test — should NOT trigger

**Input:**
> 请解释一下什么是 REST API，和 GraphQL 的区别是什么。

**Expected checks:**
- [ ] Skill does NOT trigger — normal response instead
- [ ] Does NOT output the 7 facets
- [ ] Briefly explains why this is not a need-extraction scenario
