# Skill Swappr -- Migration & Completion Plan

## The Challenge

Your full codebase (100+ files across 27 feature directories, 28 migration files, edge functions) lives on the `main-2` branch of `Hexoro/blank-canvas` on GitHub. This Lovable project is currently blank. I cannot copy hundreds of files individually from GitHub.

## Step 0: Get Your Code Into This Project

**You need to connect this Lovable project to your GitHub repo.** This is the only practical way to bring in the full codebase:

1. Go to **Settings** (click project name top-left) > **GitHub** > **Connect project**
2. Select the `Hexoro/blank-canvas` repository
3. Once connected, the code from GitHub will sync into this project

If the `main-2` branch has what you need, you may need to merge `main-2` into `main` on GitHub first (since Lovable syncs the default branch). You can do this on GitHub: open a Pull Request from `main-2` into `main` and merge it.

**Once the code is synced in, tell me and I will proceed with the next steps.**

## Step 1: Database Migration

Run all 28 migration SQL files against this project's Lovable Cloud database. This creates:

- `profiles` (40+ columns), `user_roles`, `activity_log`
- Forums: `forum_categories`, `forum_threads`, `forum_comments`, `forum_votes`
- Badges: `badges`, `user_badges`, `guild_badges`
- Guilds: `guilds`, `guild_members`, `guild_projects`, `guild_treasury_log`, `guild_loans`, `guild_wars`, `guild_achievements`
- Marketplace: `listings` (with 16 new columns from Phase 1), `reviews`
- Workspace: `workspaces`, `workspace_members`, `workspace_messages`, `workspace_stages`, `workspace_files`, `workspace_deliverables`, `workspace_voice_messages`
- Economy: `sp_transactions`, `escrow_contracts`
- Court: `disputes`, `case_evidence`, `case_comments`, `jury_assignments`, `jury_votes`
- Events: `events`, `event_registrations`, `tournaments`, `tournament_participants`
- Telemetry: `page_sessions`, `click_heatmap`, `error_log`, `search_analytics`, `funnel_events`, `platform_metrics`, `quarterly_reports`
- Enterprise: 5 enterprise tables
- Blog: `blog_posts`, `blog_comments`, `blog_likes`
- Help: `help_reports`, `help_articles`, `bug_bounty_reports`
- `notifications`, `newsletter_subscriptions`, `transactions`, `leaderboard_achievements`, `ranking_history`
- DB functions: `has_role()`, `handle_new_user()` trigger
- Storage bucket: `workspace-files`
- RLS policies on all tables

## Step 2: Seed Test & Admin Data

Insert realistic seed data:

- **Admin user**: Create auth user + profile + admin role
- **Test users**: 5-10 users with varied ELO, skills, tiers
- **Listings**: 15-20 gigs across all 9 formats (Direct, Auction, Co-Creation, Skill Fusion, SP Only, Flash Market, Requests, Projects, Contest)
- **Guilds**: 2-3 guilds with members
- **Forum content**: Categories + sample threads
- **Events**: 3-4 events
- **Badges**: Seed system badges
- **Blog posts**: 3-5 posts
- **SP transactions**: Sample transaction history

---

## What I Need From You

**Connect GitHub first.** Once the code is synced, come back and say "code is synced" and I will:

1. Run all DB migrations
2. Seed the test/admin data
  &nbsp;

This is a very large project (85 requirements). Each implementation message will tackle 1-2 items to keep changes manageable.