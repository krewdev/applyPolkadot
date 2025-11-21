# wyyrrddd

## 🌟 Project Overview

### Tagline
A token-powered social feed where content reach is transparently auctioned on-chain, giving creators direct control over their visibility.

### Brief Description
wyyrrddd is a decentralized, web-based social media platform that revolutionizes content discovery through a transparent, token-based engagement and reach auction system. Unlike opaque algorithms controlled by centralized platforms, wyyrrddd gives users direct control over both content visibility and engagement through native tokens (LIKE, LOVE, CARE, CREEP). Creators can boost posts to the top of the feed via reach auctions, while users interact with content by spending tokens at tiered costs (LIKE: 1, LOVE: 5, CARE: 10, CREEP: 50). The platform also introduces a groundbreaking Data Sovereignty model where users can voluntarily sell their anonymized behavioral data to the wyyrrddd DAO and earn from it. Built as a modern web application on Polkadot with AI-powered content generation, wyyrrddd puts the power of social media algorithms and data ownership back into users' hands through on-chain token economics.

### Polkadot Integration
wyyrrddd integrates deeply with Polkadot through:

1. **Native Token System on Asset Hub**: Custom token contracts (LIKE, LOVE, CARE, CREEP) deployed on Polkadot Asset Hub for engagement and reach auction mechanics
2. **Smart Contract-Based Algorithm**: On-chain smart contracts handle reach auction logic, engagement tracking, and DAO data marketplace, ensuring transparent and verifiable content ranking
3. **Polkadot.js Wallet Integration**: Seamless wallet connection for token spending, posting, interaction, and data sovereignty controls using Polkadot.js extension
4. **USDC Integration**: Stablecoin support for displaying user net worth and DAO earnings in stable value terms
5. **DAO Governance**: Decentralized autonomous organization structure for data marketplace revenue distribution (90% to users, 10% to protocol)
6. **Cross-Chain Content Discovery**: Leveraging XCM for potential cross-parachain content sharing and discovery
7. **Decentralized Storage**: IPFS integration for immutable content storage with Polkadot-based metadata anchoring

### Motivation
Current social media platforms operate with opaque algorithms that creators can't control or understand. We're building wyyrrddd to democratize content visibility by making it transparent, auction-based, and directly controllable through blockchain tokens. Polkadot's low fees, fast transactions, and robust smart contract capabilities make it the perfect foundation for a token-powered social network where micro-transactions happen constantly in the background.

## 🔍 Project Details

### Technology Stack

**Frontend (Web Application):**
- React 18+ with TypeScript
- Web-based deployment (accessible via browser, no native app required)
- TailwindCSS with custom cyberpunk design system
- Custom color palette (cyber-dark, cyber-primary, cyber-secondary, etc.)
- Custom animations (pulse-fast, scan, float-out)
- React Router for client-side routing
- Responsive mobile-first design (Progressive Web App ready)
- Browser APIs: Geolocation API, Web NFC API, Web Crypto API

**Blockchain:**
- ink! smart contracts on Polkadot Asset Hub
- Polkadot.js API for wallet integration
- Substrate-based token standard implementation

**Backend Services (Web-Based Infrastructure):**
- Google Gemini AI API for:
  - Content generation (generateFeedContent)
  - Location-based environmental analysis (analyzeSurroundings)
- IPFS (via NFT.Storage) for decentralized content storage
- Browser Geolocation API for location-based rewards
- Web NFC API (browser-native NFC support) for NFC tag detection
- Client-side state management (no traditional backend server required)

**State Management:**
- React Context API for wallet state
- Local storage for offline-first experience

### Core Components & Architecture

1. **Feed Component**: Main social feed displaying posts ranked by reach auction bids with AI-generated content
2. **Reach Auction System**: Live auction interface showing current top bid and allowing users to boost their posts to the top
3. **Token Interaction System**: Tiered engagement mechanics where users spend tokens to interact with posts (LIKE: 1, LOVE: 5, CARE: 10, CREEP: 50 tokens)
4. **Profile/Identity Component**: User dashboard displaying wallet stats, token balances, USDC net worth, and DAO earnings
5. **Data Sovereignty Module**: Users can opt-in to sell anonymized behavioral data to the wyyrrddd DAO and earn passive income (90% revenue share)
6. **Radar Feature (GEO-Spatial Discovery)**: Location-based and NFC-based reward system where users scan their surroundings to find targets and earn CARE tokens (GEO: 50 tokens, NFC: 25 tokens)
7. **Token Wallet Integration**: Seamless token spending through Polkadot.js wallet extension
8. **Post Creation**: Image upload, metadata handling, and on-chain registration
9. **AI Content Generation**: Gemini-powered feed content generation for discovery
10. **Smart Contract Layer**: On-chain auction logic, engagement tracking, and DAO data marketplace ensuring transparent ranking and revenue distribution

### Data Models

**Post Structure:**
```typescript
interface Post {
  id: string;                    // Unique identifier
  userId: string;                // Creator wallet address
  username: string;              // Display name
  userAvatar: string;            // Avatar URL
  imageUrl: string;              // IPFS hash for image
  caption: string;               // Post text content
  tokens: {                       // Token engagement metrics
    LIKE: number;
    LOVE: number;
    CARE: number;
    CREEP: number;
  };
  isSponsored: boolean;          // Whether post is boosted
  reachBid: number;              // Current reach auction bid (LIKE tokens)
  timestamp: number;             // Post creation timestamp
}
```

**Token Types & Costs:**
- **LIKE**: Primary engagement token (cost: 1 token per interaction)
- **LOVE**: Premium engagement token (cost: 5 tokens per interaction)
- **CARE**: Community-oriented engagement (cost: 10 tokens per interaction)
- **CREEP**: High-value engagement metric (cost: 50 tokens per interaction)

**User Profile Data:**
```typescript
interface UserProfile {
  walletAddress: string;          // Polkadot wallet address
  username: string;               // Display name
  avatar: string;                 // Avatar URL/IPFS hash
  tapestryLevel: number;          // User reputation/level system
  usdcBalance: number;            // USDC holdings
  daoEarnings: number;            // Cumulative earnings from data sovereignty
  tokenBalances: {                // Token holdings
    LIKE: number;
    LOVE: number;
    CARE: number;
    CREEP: number;
  };
  isSellingData: boolean;         // Opt-in status for data sovereignty
}
```

### MVP/Proof of Concept

Working MVP demonstrates:
- ✅ React-based feed UI with cyberpunk aesthetic
- ✅ Wallet connection via Polkadot.js context
- ✅ Token spending mechanism for reach boosting
- ✅ Image upload and post creation
- ✅ Live reach auction interface showing current bids
- ✅ AI-powered content generation via Gemini service
- ✅ Post card component with engagement metrics

**Current Implementation:**

**Feed Component:**
- Dynamic post loading from AI service (Gemini integration)
- File upload and base64 image encoding
- Token spending verification before reach boosting
- Live reach auction interface with current bid display
- Responsive UI with cyberpunk design system
- Loading states and error handling

**PostCard Component:**
- Token interaction buttons with tiered costs (LIKE: 1, LOVE: 5, CARE: 10, CREEP: 50)
- Real-time engagement animations on token spend
- Interactive tooltips showing token costs
- Sponsored/reach-boosted post badges
- User avatar and tapestry level display
- Gradient overlays and cyberpunk styling

**Profile/Identity Component:**
- Wallet stats display (USDC balance, DAO earnings)
- Token balance cards for all four token types
- Data sovereignty toggle for selling anonymized behavioral data
- User profile header with wallet address and connection status
- Grid layout for token assets

**Navigation Component:**
- Three main routes: Feed, Radar (GEO-spatial discovery), Identity (profile)
- Active state indicators with cyberpunk styling
- Bottom navigation bar with icons

**Radar Component (Frontend Prototype):**
- GEO-spatial scanning interface with animated radar visualization (UI complete)
- Geolocation-based target detection UI (browser location APIs integrated, mock data)
- NFC tag detection simulation UI (ready for hardware integration)
- AI-powered location analysis UI (Gemini service analyzeSurroundings integrated, returns mock analysis)
- Frontend token reward display (mock rewards: GEO targets: 50 CARE tokens, NFC targets: 25 CARE tokens)
- Visual scanning animation with rotating rings and scan lines (fully functional)
- Reward claiming UI with mock token distribution (frontend-only, no on-chain integration yet)
- **Note**: Full blockchain integration with smart contracts and actual token rewards is planned for Milestone 2

### Limitations

wyyrrddd will NOT provide:
- Email/password authentication (wallet-only)
- Centralized user data storage
- Traditional follower/following social graph (focus on algorithmic discovery)
- Direct messaging features (scope limited to feed and engagement)
- Support for non-Polkadot ecosystems in initial version

## 🧩 Ecosystem Fit

### Where It Fits in the Ecosystem

wyyrrddd positions itself as a social infrastructure layer for the Polkadot ecosystem, demonstrating how native tokens can power novel social mechanics. It complements existing DeFi and NFT projects by providing a social engagement layer where ecosystem tokens gain utility beyond trading and governance.

### Target Audience

1. **Content Creators**: Artists, writers, and creators seeking transparent and controllable content distribution
2. **Polkadot Community Members**: Users already engaged in the ecosystem looking for native social experiences
3. **Crypto-Native Users**: Early adopters comfortable with wallet-based authentication and token mechanics
4. **Algorithm Transparency Advocates**: Users frustrated with opaque social media algorithms

### Needs Met

1. **Transparent Content Discovery**: Makes algorithmic ranking transparent and controllable through on-chain auctions
2. **Creator Economic Empowerment**: Gives creators direct control over reach through token spending while enabling users to engage at multiple price points
3. **Blockchain-Native Social Experience**: Full wallet integration without email/password fallbacks
4. **Fair Attention Marketplace**: Competitive but transparent auction system for feed placement
5. **Data Sovereignty**: Users can monetize their own behavioral data instead of platforms profiting without user consent
6. **Tiered Engagement System**: Multiple engagement options at different price points (1-50 tokens) allow for nuanced expression
7. **Passive Income Opportunity**: DAO data marketplace provides ongoing revenue stream for users who opt-in

### Similar Projects in Polkadot

**Existing Social Projects:**
- **Subsocial**: Decentralized social network with IPFS storage, but lacks token-based algorithmic control
- **Plaza**: Polkadot's official social hub, focuses on community building rather than algorithmic transparency

**How wyyrrddd Differs:**
1. **Token-Powered Algorithm**: First social platform to make algorithmic ranking transparent and auction-based
2. **Tiered Engagement System**: Unique multi-token interaction model (LIKE/LOVE/CARE/CREEP) with different costs and meanings
3. **Data Sovereignty Model**: First social platform where users can opt-in to sell their own data and receive 90% of revenue share
4. **Reach Auction Innovation**: Novel mechanism for content visibility through competitive bidding
5. **AI-Powered Discovery**: Integrates AI content generation with blockchain-based ranking
6. **GEO-Spatial Reward System**: Location-based and NFC-based discovery mechanism where users can scan their surroundings to find targets and earn tokens—bridging the digital and physical worlds through blockchain rewards
7. **Micro-Transaction Focus**: Built specifically for constant token spending in background with very low fees
8. **User Reputation System**: "Tapestry Level" system for tracking user engagement and status

### Why Such a Project Might Not Exist Yet

1. **Technical Complexity**: Requires sophisticated smart contract logic for real-time auction mechanics
2. **User Education**: Token-based social mechanics need significant user education
3. **Gas Cost Concerns**: Only viable on chains with extremely low fees (Polkadot's advantage)
4. **Market Timing**: Token-powered social networks are still emerging, requiring both crypto-native users and content creators

## 👥 Team

### Team Name
wyyrrddd Labs

### Contact Name
Jay Young

### Contact Email
manidex@proton.me

### Website


### Team Members

Jay Young 

### LinkedIn Profiles

[LinkedIn URLs if available]

### Team Code Repos

github.com/krewdev/solana-zk
github.com/krewdev/sealevelstudios

### GitHub Accounts

github.com/krewdev
github.com/sealevelstudios

### Team Experience

Building sealevel studios involved deep blockchain integration and required the need for knowledge about vast amounts of tooling and code. LLM handling and deployment as well as smart contract writing and running, and the building of custom APIs and endpoints, makes this project perfect for my level of knowledge and what I will enjoy building out.

## 📊 Development Status

### Current Implementation

wyyrrddd has a working frontend MVP demonstrating core concepts.

**MVP Repository/Deployment:**
- Interactive Simulator: [applications/assets/wyyrrddd-simulator.html](./assets/wyyrrddd-simulator.html) (standalone HTML demo demonstrating core features)
- GitHub Repository: [https://github.com/krewdev/wyyrrddd](https://github.com/krewdev/wyyrrddd) (full React implementation)
- Live Demo: [https://wyyrrddd-ks8tuohoj-battlesol.vercel.app](https://wyyrrddd-ks8tuohoj-battlesol.vercel.app) (deployed version)

The MVP includes both a standalone HTML simulator (for quick demonstration) and the complete React frontend implementation with all components described below.

**Completed Features:**
- React Feed component with post display and reach auction system
- Wallet context integration (useWallet hook) with full token management
- Token spending functionality for both reach boosting and post engagement
- Tiered engagement system with four token types at different costs
- Image upload and post creation flow
- Reach auction UI showing current bids and boost functionality
- Profile/Identity page with wallet stats, token balances, and data sovereignty controls
- Navigation system with Feed, Radar, and Identity routes
- AI content generation integration (Gemini service)
- Interactive post cards with engagement animations
- Cyberpunk design system implementation with gradient overlays
- Loading states and error handling
- User level/reputation display ("Tapestry Level")
- USDC balance tracking for net worth display
- DAO earnings tracking for data sovereignty participants

**Codebase Structure:**
- `Feed.tsx`: Main feed component with auction system
- `PostCard.tsx`: Individual post display with token interactions and animations
- `Profile.tsx`: User profile/identity page with wallet stats and data sovereignty
- `Navigation.tsx`: Bottom navigation bar with route management
- `Icons.tsx`: Custom icon components (LikeIcon, HeartIcon, CareIcon, CreepIcon, etc.)
- `WalletContext.tsx`: Wallet integration, token management, and DAO functionality
- `geminiService.ts`: AI content generation service
- Token types and Post interfaces defined

**Next Steps:**
- Smart contract development for on-chain auction logic and engagement tracking
- DAO smart contract for data sovereignty marketplace and revenue distribution
- IPFS integration for decentralized content storage
- Polkadot Asset Hub token contract deployment (LIKE, LOVE, CARE, CREEP)
- USDC integration for stable value tracking
- Radar feature implementation for GEO-spatial and NFC-based content discovery with token rewards
- Backend API for feed aggregation, ranking, and DAO data processing

## 📅 Development Roadmap

### Overview

- **Estimated Duration:** 2.5 months
- **Full-Time Equivalent (FTE):** 1.5
- **Total Costs:** $7,000 USD

### Milestone 1: On-Chain Auction System & Token Contracts ($3,500, 1.25 months)

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Documentation | Comprehensive inline code documentation and tutorial explaining how to deploy token contracts, interact with reach auction, and boost posts on wyyrrddd |
| 0c. | Testing | Unit tests covering smart contract auction logic, token transfers, and reach calculation algorithms, with detailed testing guide |
| 0d. | Article | Article explaining how wyyrrddd's transparent auction system democratizes content discovery on Polkadot |
| 1. | Token Contracts on Asset Hub | Deploy custom ink! contracts for LIKE, LOVE, CARE, and CREEP tokens on Polkadot Asset Hub with: (1) Standard token transfer functionality, (2) Minting capabilities for initial distribution, (3) Balance querying interfaces, (4) Approval mechanisms for spending |
| 2. | Reach Auction Smart Contract | Implement and deploy ink! contract that will: (1) Handle reach auction bidding logic, (2) Track current top bid per post, (3) Process token spending for reach boosting, (4) Calculate feed ranking based on auction bids, (5) Enable post registration with on-chain metadata anchoring |
| 3. | DAO Data Marketplace Smart Contract | Implement and deploy ink! contract for data sovereignty that will: (1) Handle opt-in/opt-out for data selling, (2) Process anonymized behavioral data submissions, (3) Track DAO earnings per user, (4) Distribute revenue (90% to users, 10% to protocol), (5) Enable USDC payouts for DAO earnings |
| 4. | Polkadot.js Integration | Complete wallet integration that will: (1) Connect to Polkadot.js extension seamlessly, (2) Query token balances from Asset Hub, (3) Sign transactions for reach auction bids, (4) Handle transaction status updates and confirmations, (5) Support multiple wallet accounts |

### Milestone 2: Content Storage & Feed Aggregation ($3,500, 1.25 months)

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT |
| 0b. | Documentation | Updated documentation covering IPFS integration, content storage, and feed aggregation logic |
| 0c. | Testing | Extended test coverage including integration tests for complete user journey from post creation to feed display |
| 0d. | Demo Video | Comprehensive demonstration video showcasing reach auction mechanics, token spending, and feed ranking |
| 1. | IPFS Content Storage | Implement decentralized storage that will: (1) Upload images to IPFS via NFT.Storage, (2) Store post metadata with IPFS hash, (3) Anchor content hashes on-chain via smart contract, (4) Enable content retrieval by IPFS hash, (5) Handle content verification |
| 2. | Feed Aggregation Service | Develop feed ranking system that will: (1) Query all posts from smart contract, (2) Calculate ranking based on reach auction bids and engagement metrics, (3) Integrate AI content generation (Gemini) for discovery, (4) Handle pagination for large feed, (5) Cache feed state for performance optimization, (6) Aggregate user tapestry levels from engagement data |
| 3. | Radar Feature - Blockchain Integration | Complete blockchain integration for the existing Radar frontend prototype: (1) Deploy smart contract logic for CARE token rewards (GEO: 50, NFC: 25) on Polkadot Asset Hub, (2) Implement on-chain reward claiming and token distribution via Polkadot.js transactions, (3) Connect existing frontend UI to smart contract for real token rewards (replacing mock rewards), (4) Enable location-based target registration for businesses/creators with on-chain metadata storage, (5) Integrate smart contract verification for geolocation and NFC tag detections, (6) Add transaction signing and confirmation handling for reward claims. Note: Frontend UI with animations, Gemini AI integration, and browser APIs is already complete from MVP. |
| 4. | Enhanced UI/UX & Data Sovereignty | Improve user experience with: (1) Real-time auction bid updates, (2) Transaction status notifications, (3) Optimized mobile responsive design, (4) Onboarding flow for new users, (5) Post analytics dashboard showing reach metrics, (6) Data sovereignty dashboard showing DAO earnings, (7) USDC balance integration and display, (8) Enhanced engagement animations and feedback |

### 💰 Budget Breakdown

**Milestone 1 ($3,500):**
- Smart Contract Development (Tokens + Auction + Engagement): $1,500 (50 hours @ $30/hour)
- DAO Data Marketplace Smart Contract: $800 (27 hours @ $30/hour)
- Polkadot.js Integration (including USDC): $900 (30 hours @ $30/hour)
- Testing & Documentation: $300 (10 hours @ $30/hour)

**Milestone 2 ($3,500):**
- IPFS Integration: $800 (27 hours @ $30/hour)
- Feed Aggregation Service: $1,000 (33 hours @ $30/hour)
- Radar Feature - Blockchain Integration: $1,200 (40 hours @ $30/hour)
- UI/UX Enhancement (including data sovereignty): $500 (17 hours @ $30/hour)

## 🔮 Future Plans

### Post-Grant Development

1. **Multi-Token Auction Support**: Allow bidding with different token types (LOVE, CARE, CREEP) with weighted values in reach auctions
2. **Creator Monetization**: Enable direct tipping, subscriptions, and revenue sharing features using Polkadot tokens
3. **Enhanced Data Sovereignty**: Expand DAO data marketplace with more granular controls, data type selection, and privacy settings
4. **Cross-Chain Content Sharing**: Leverage XCM to share content across Polkadot parachains
5. **Advanced AI Features**: Enhanced content generation, personalized feed recommendations based on wallet activity and engagement patterns
6. **Community Governance**: DAO structure for platform evolution using Polkadot governance mechanisms, allowing token holders to vote on protocol changes
7. **Tapestry Level System**: Expand reputation system with rewards, badges, and special privileges for high-level users
8. **Analytics Dashboard**: Comprehensive analytics for creators showing reach, engagement, token earnings, and audience insights

### Additional Funding

- Apply for Polkadot Treasury funding for scaling development
- Seek partnerships with existing Polkadot NFT and DeFi projects for token integration
- Explore Web3 Foundation grants for advanced feature development
- Potential VC funding for user acquisition and marketing

### Vision for Growth

wyyrrddd aims to become the standard social layer for the Polkadot ecosystem, demonstrating how blockchain-native token mechanics can revolutionize social media. By making algorithmic transparency a core feature, we envision attracting creators frustrated with traditional platforms and crypto-native users seeking fully decentralized social experiences. Our long-term vision includes becoming the go-to platform for Polkadot community engagement, where ecosystem tokens gain utility beyond DeFi and governance.

## ℹ️ Additional Information

**Technical Innovation:**
wyyrrddd introduces several novel mechanisms:

1. **Transparent Reach Auction**: Makes content visibility transparent and controllable—a first in the social media space. Unlike traditional algorithms, users can see exactly why content appears at the top of their feed (highest bidder) and directly influence this through token spending.

2. **Tiered Token Engagement System**: Four-token interaction model (LIKE/LOVE/CARE/CREEP) with different costs (1/5/10/50 tokens) allows for nuanced expression and economic signaling in engagement.

3. **Data Sovereignty Model**: Users can voluntarily sell their anonymized behavioral data to the DAO and receive 90% of the revenue—flipping the traditional social media model where platforms profit from user data without consent or compensation.

4. **User Reputation via Tapestry Levels**: Engagement-based reputation system that rewards active users and provides visual status indicators.

5. **Micro-Transaction Social Mechanics**: Built specifically for constant token spending in the background, leveraging Polkadot's low fees to enable frequent micro-interactions.

**Ecosystem Integration:**
We plan to integrate with existing Polkadot projects:
- Partner with NFT marketplaces (e.g., KodaDot, RMRK) to enable NFT display in posts
- Integrate with DeFi protocols (Acala, Moonbeam) for token staking and yield generation on user token balances
- Connect with governance platforms for community-driven content moderation
- Integrate with identity solutions (KILT, Dock) for verified creator badges and reputation anchoring
- Partner with USDC issuers for seamless stablecoin integration
- Explore integration with cross-chain bridges for expanding token utility
- Partner with physical businesses (cafes, venues, events) to deploy NFC tags and location-based rewards through Radar feature
- Integrate with mapping services (OpenStreetMap, Google Maps) for enhanced location-based features

**Open Source Commitment:**
wyyrrddd will be open source from day one, allowing the Polkadot community to contribute to and extend the platform. We believe transparent algorithms should have transparent code.

Remember that the Fast-Grants Programme is designed as a first step for promising projects. We're looking for projects that can continue to grow beyond this initial funding.

