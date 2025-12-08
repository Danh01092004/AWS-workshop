---
title: "Blog 4"
date: 2025-01-01
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

# AWS for Games: Jackbox Games Opens New Opportunities with Amazon GameLift Streams

**By David Holladay  March 6, 2025**

*Tags: Amazon CloudFront, Amazon GameLift, Amazon SQS, Amazon S3, Customer Solutions, Game Development, Games, Messaging, Networking & Content Delivery, Storage, Industries*

## Introduction

Jackbox Games is a Chicago-based game studio renowned for party games like Quiplash, Fibbage, Drawful, Trivia Murder Party, and many others. With over 50 games in its catalog, Jackbox pursues a mission of "accessible gaming"  enabling players to participate from any device they have. The company's entire server infrastructure is built on Amazon Web Services.

Previously, players typically used a TV to display the game and a phone as a controller  a simple but widely popular play style. Recently, Jackbox decided to partner with Amazon GameLift Streams to deliver installation-free, instant-access gaming experiences to players.

Amazon GameLift Streams is a feature within GameLift that enables games to be streamed with low latency, high frame rates, and global scale  helping studios like Jackbox expand their reach without depending on consoles or powerful devices.

## 1. Cost Control While Scaling

Bringing a game to a streaming platform can be expensive if done in isolation. Jackbox has a very large catalog, so they needed a way to optimize costs.

#### 1.1 Creating a Stream Group for All Games

AWS partnered with Jackbox to consolidate all 50 games into a single Stream Group within Amazon GameLift Streams. This allows them to scale their entire catalog together rather than managing each game individually.

#### 1.2 Multi-tenancy & Reduced Resource Costs
Because Jackbox games don't require powerful GPUs, a single server instance can run multiple games simultaneously  implementing a multi-tenancy model to save on costs.

#### 1.3 Using Data Channels to Insert Ads

Amazon GameLift Streams provides a Data Channel feature that allows ads to be inserted at appropriate moments between game rounds  helping Jackbox sustain a free-to-play model or support revenue through advertising.

## 2. Improved Update and Release Processes

#### 2.1 Traditional Party Pack Model & Limitations

Previously, Jackbox released games in Party Packs  each bundle containing 5 games. Updating a single game required updating the entire pack across all platforms, creating complexity in management and deployment.

#### 2.2 Streaming Enables Flexible, Individual Updates

With GameLift Streams, Jackbox can update a single game on the server without affecting others, regardless of platform differences. This also allows players to seamlessly transition between games without closing and reopening bundles.

#### 2.3 Increased Game Discoverability

When all games are accessible through the streaming service, players have more opportunities to try new games immediately  rather than being limited to bundles they've previously purchased.

## 3. Support & Deep Integration with AWS

##### 3.1 Technical Support Integrated into Slack

During deployment, AWS supported Jackbox directly through their Slack  enabling the development team to communicate easily and resolve issues quickly. Jackbox's CTO noted that this experience made AWS feel like part of their team.

#### 3.2 Using Multiple AWS Services

Beyond GameLift Streams, Jackbox uses several AWS services to operate their system:

- **Amazon EC2** for backend processing and session management
- **Amazon S3** for storing game assets and data
- **Amazon SQS** for queue management
- **Amazon CloudFront** for fast and reliable content distribution

All these services fit seamlessly within the AWS ecosystem Jackbox was already using.

## 4. Future Direction & Vision

Jackbox is excited about reaching new players through popular devices like Smart TVs without requiring a console. They envision an experience similar to opening a streaming app (like Netflix) to play games instantly.

Streaming also enables Jackbox to explore partnerships with other studios, bringing games from different engines into their service  expanding their catalog faster. Jackbox's CTO emphasizes that streaming opens a "new business model" impossible with traditional Party Pack structures  subscription, advertising, and direct access models  and GameLift Streams provides the flexibility to continue innovating.

## Conclusion

Through Amazon GameLift Streams, Jackbox Games has achieved numerous benefits:

- Expanded global reach to players worldwide
- Reduced operational costs through multi-tenancy and centralized management
- Simplified game update processes
- Enabled flexible revenue models (advertising, subscription)
- Enhanced player experience and content discoverability

The partnership between Jackbox and AWS demonstrates that game streaming is not just a trend, but a platform for innovation in the gaming industry.

## About the Author

**David Holladay**
<img src="/images/blog1.jpeg" width="300" style="float:left; margin:0;" />

David Holladay is a Principal Solutions Architect with the AWS Game Tech team, specializing in consulting and supporting game studios in building large-scale infrastructure on AWS. With over 15 years of experience in software development and game systems design, he has worked with many leading studios worldwide. When not working, David enjoys streaming newly released indie games and participating in game jam events to share programming expertise with the game development community.
