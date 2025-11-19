# README

## StackSocial - Decentralized On-Chain Social & Tipping Platform

A smart contract built on the Stacks blockchain that enables decentralized social networking with integrated tipping functionality.

### Features

**User Profiles** - Create personalized profiles with username and bio
**Posts** - Share content (280 characters) on-chain
**Tipping** - Send STX directly to content creators
**Follow System** - Follow and unfollow other users
**Admin Controls** - Ban/unban users to maintain community standards
**On-Chain Tracking** - All interactions recorded on the blockchain

### Core Functions

| Function | Description |
|----------|-------------|
| `create-profile` | Create a user profile with username and bio |
| `create-post` | Post content (max 280 characters) |
| `tip` | Send STX to a post creator |
| `follow` | Follow another user |
| `unfollow` | Unfollow a user |
| `set-ban` | Admin function to ban/unban users |

### Read-Only Functions

- `get-profile` - Retrieve user profile information
- `get-post` - Retrieve post details
- `get-total-users` - Get total number of registered users
- `get-total-tips` - Get total STX tipped across the platform

### Smart Contract Data

**User Profile Data:**
- Username (32 characters max)
- Bio (128 characters max)
- Ban status
- Follower count
- Tips received

**Post Data:**
- Author principal
- Content (280 characters max)
- Timestamp
- Tips received on that post

### Error Codes

| Code | Description |
|------|-------------|
| `u100` | Profile/Post not found |
| `u101` | Invalid amount |
| `u102` | Profile already exists |
| `u103` | Not authorized (owner only) |
| `u104` | User is banned |

### Usage Example

```clarity
;; Create a profile
(contract-call? .stacksocial create-profile "alice" "Web3 enthusiast")

;; Create a post
(contract-call? .stacksocial create-post "Just launched my new project!")

;; Tip a creator (100 STX)
(contract-call? .stacksocial tip u1 u100000000)

;; Follow a user
(contract-call? .stacksocial follow 'SP123ABC456DEF789...)

;; Admin: Ban a user
(contract-call? .stacksocial set-ban 'SP123ABC456DEF789... true)
```

### Technology Stack

- **Blockchain:** Stacks (Layer 2 for Bitcoin)
- **Language:** Clarity Smart Contract Language
- **Network:** Testnet/Mainnet compatible


### Future Enhancements

- Hashtag support
- Comment threads
- Repost functionality
- Token-gated features
- Governance mechanisms

---

**License:** MIT  
**Version:** 1.0.0  
**Author:** StackSocial Team
