# New Agent Onboarding Process

Use this checklist when hiring a new agent to ensure complete setup.

### Phase 1: Information Gathering

1. **John creates bot in BotFather and:**
   - [ ] Sets bot to **Allow Groups: Yes**
   - [ ] Sets **Group Privacy: No** (so bot sees all messages)
   - [ ] Adds bot to **WF365 Team Group** as regular member (no admin needed)
   - [ ] Sends me the bot token

2. **I ask John for:**
   - [ ] Desired agent name
   - [ ] Job role / title
   - [ ] Who they report to
   - [ ] Brief description of responsibilities

3. **I present role summary for approval**

### Phase 2: Profile Creation
   - Show the agent's proposed role, responsibilities, boundaries, and collaboration requirements
   - Wait for John's approval before proceeding

## Phase 2: Profile Creation

3. **Create profile directory:**
   ```bash
   mkdir -p ~/.hermes/profiles/<agent-name>
   ```

4. **Create .env file:**
   ```
   TELEGRAM_BOT_TOKEN=<token-from-step-1>
   TELEGRAM_ALLOWED_USERS=6473711033
   TELEGRAM_GROUP_ALLOWED_CHATS=-5132767368
   TELEGRAM_OBSERVE_UNMENTIONED_GROUP_MESSAGES=true
   TELEGRAM_REQUIRE_MENTION=true
   TELEGRAM_EXCLUSIVE_BOT_MENTIONS=true
   ```

5. **Create config.yaml with model settings:**
   ```yaml
   model:
     default: meituan/longcat-2.0:free
     provider: custom
     base_url: https://inference-api.nousresearch.com/v1
     api_key: <current-key-from-existing-agent>
   ```
   - Copy remaining settings from existing agent config
   - Update user identity
   - Configure telegram settings:
     - require_mention: true
     - exclusive_bot_mentions: true
     - observe_unmentioned_group_messages: true
     - mention_patterns: [agent's own name, "everyone", role-specific patterns]

6. **Create SOUL.md using template:**
   - Agent identity and role
   - FIRST RULE
   - HARD RULES
   - Group chat behavior
   - Role-specific responsibilities
   - Boundaries
   - Collaboration rules
   - Shared resources
   - Obsidian vault info
   - Pulse nudge handling
   - Telegram group chat management rules (all 3)
   - NEVER post silence announcements

## Phase 3: Gateway & System Setup

7. **Create systemd service:**
   ```bash
   cat > /etc/systemd/system/hermes-gateway-<agent>.service << EOF
   # ... (standard template)
   EOF
   systemctl daemon-reload
   ```

8. **Verify service file created correctly**

## Phase 4: Activation & Testing

9. **Start gateway:**
   ```bash
   sudo systemctl start hermes-gateway-<agent>.service
   ```

10. **Verify gateway is running:**
    ```bash
    systemctl is-active hermes-gateway-<agent>.service
    ```

11. **Test in Telegram:**
    - Send a message to the agent in the group
    - Verify they respond when their name is mentioned
    - Verify they don't respond when not mentioned

## Phase 5: Documentation

12. **Create agent Obsidian folder:**
    ```bash
    mkdir -p ~/.hermes/shared/obsidian-vault/Agents/<AgentName>/
    ```

13. **Create agent profile note:**
    - Role, responsibilities, collaboration, boundaries
    - Link to relevant project notes

14. **Update shared memory with new agent info**
15. **Update cross-agent search index**

## Global Settings Sync

When changes are made to existing agents' global settings (rules, patterns, configs), ensure new agents also get these changes:

1. Before finalizing new agent setup, check current global settings:
   - Review latest SOUL.md template
   - Review latest management rules
   - Review latest pattern structure
   - Review latest telegram config options

2. Apply all current global settings to new agent

3. After new agent is online, verify:
   - Management rules work (add/remove patterns)
   - Telegram group behavior is correct
   - All global patterns are present
