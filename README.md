# SQL-Project-Web3-Gaming-Economy-Analysis-Challenges
This project contains 50 SQL challenges simulating analytics on a Web3 gaming platform. It covers querying player, guild, NFT, marketplace, and governance data to demonstrate skills like joins, aggregations, filtering, window functions, and subqueries for insightful analysis.

# SQL Project: Web3 Gaming Economy Analysis Challenges

## Project Overview
This project showcases an extensive set of 50 practical SQL challenges designed to simulate complex analytics on a hypothetical Web3 gaming platform database. The challenges are crafted to test and demonstrate a wide spectrum of SQL capabilities, ranging from foundational querying to advanced data analysis techniques. The goal is to extract actionable insights from player behavior, guild management, NFT asset ownership, marketplace activities, and governance participation.

---

## Database Schema Reference

The project uses the following tables and key columns:

| Table Name             | Description                           | Key Columns                                                     |
|------------------------|-------------------------------------|----------------------------------------------------------------|
| **Players**            | Stores player profiles and activity | `player_id` (PK), `username`, `wallet_address`, `registration_date`, `last_login_date`, `total_game_time_minutes`  |
| **Guilds**             | Details about guilds and leadership | `guild_id` (PK), `guild_name`, `creation_date`, `leader_player_id` (FK), `guild_treasury_balance`                     |
| **PlayerGuildHistory** | Tracks player memberships in guilds | `membership_id` (PK), `player_id` (FK), `guild_id` (FK), `join_date`, `leave_date`                                   |
| **NFT_Assets**         | NFT details and ownership           | `asset_id` (PK), `asset_name`, `asset_type`, `rarity`, `initial_mint_date`, `current_owner_player_id` (FK)             |
| **MarketplaceTransactions** | Records NFT sales and trades         | `transaction_id` (PK), `asset_id` (FK), `seller_player_id` (FK), `buyer_player_id` (FK), `transaction_date`, `price_usd`, `transaction_fee_usd` |
| **GovernanceVotes**    | Player votes on governance proposals | `vote_id` (PK), `proposal_id`, `player_id` (FK), `vote_date`, `vote_choice`, `vote_weight`                            |
| **Daily_Market_Prices**| Tracks token price history           | `price_date` (PK), `token_symbol` (PK), `closing_price_usd`                                                           |

---

## Challenge Categories & Examples

### 1. Basic Data Retrieval  
- Fetch player information, including IDs, usernames, and wallet addresses.  
- Select guilds created after a specific date to track recent formations.  
- Retrieve specific NFT assets by rarity and ownership details.  

### 2. Aggregations and Filtering  
- Count unique voters in governance to measure player engagement.  
- Calculate the maximum transaction price to identify high-value trades.  
- List players with total game times within defined thresholds.  

### 3. Joins and Relationships  
- Link players to their current guilds and guild leaders.  
- Associate marketplace transactions with NFT asset details.  
- Identify players both buying and selling assets on the marketplace.  

### 4. Advanced SQL Techniques  
- Use Common Table Expressions (CTEs) for transaction counts and ranking assets.  
- Calculate player retention and login activity patterns using window functions and date logic.  
- Implement relational division queries to find players who voted on all proposals.  

---

## Example Challenge

**Question:** Retrieve the username and guild name for players who are currently members of a guild.  
**Solution:**
SELECT p.username, g.guild_name
FROM Players AS p
JOIN PlayerGuildHistory AS pgh ON p.player_id = pgh.player_id
JOIN Guilds AS g ON pgh.guild_id = g.guild_id
WHERE pgh.leave_date IS NULL;


**Explanation:** This query joins three tables to link players to their active guild memberships by filtering out memberships with a non-null leave_date.

---

## Skills Demonstrated

- Mastery of SELECT, WHERE, JOIN, and GROUP BY clauses.  
- Use of aggregation functions including COUNT, SUM, AVG, MAX, and DISTINCT.  
- Applying filtering with complex logical conditions and date functions.  
- Advanced techniques like window functions (DENSE_RANK, ROW_NUMBER) and CTEs for modular queries.  
- Writing relational division queries for comprehensive dataset coverage.  

---

## Setting Up and Using this Project

1. **Create Database Schema:** Use provided DDL scripts to create the tables.  
2. **Populate Data:** Load sample or actual data consistent with the schema for realistic analysis.  
3. **Execute Queries:** Run individual SQL challenges in your preferred SQL environment (MySQL, PostgreSQL, etc.).  
4. **Extend Analysis:** Customize queries or add new challenges based on project needs.

---

## Future Work

- Integrate real-world Web3 gaming data for live analytics.  
- Develop dashboards and visualizations to complement SQL analyses.  
- Incorporate predictive modeling and machine learning for player behavior forecasting.  
- Expand governance analytics to include proposal outcomes and impact.

---

## Contact & Contribution

**Author:** [Your Name]  
**Email:** [Your Email]  
**GitHub:** [Your GitHub Profile]  

Contributions, feedback, or questions are welcome!

---

This project is a comprehensive learning tool for SQL practitioners interested in gaming and blockchain analytics, enhancing skills through practical challenges reflecting real-world data scenarios.
