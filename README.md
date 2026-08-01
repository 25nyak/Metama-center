# ⚡ Metamob Arena & Login Token Faucet

A Solana-powered gaming platform with an integrated token distribution faucet system. Combines game hosting capabilities with hourly login reward mechanics.

## Features

- **Phantom Wallet Integration**: Connect your Solana wallet directly to the platform
- **Hourly Token Faucet**: Claim 27,624 tokens every hour via the login reward system
- **Universal Game Connector**: Register and launch multiple games from a single hub
  - Support for HTML/JS applications
  - Support for PPSSPP emulator instances
- **Admin Panel**: Configure token distribution and manage game entries
- **Real-time Token Balance**: Track your SPL token holdings directly in the wallet status
- **Local Storage Persistence**: Game configurations and settings are saved locally

## Quick Start

1. **Open the Application**
   - Open `index.html` in a modern web browser
   - Ensure you have the [Phantom Wallet](https://phantom.app/) browser extension installed

2. **Connect Your Wallet**
   - Click "Connect Wallet" button in the top-right
   - Approve the connection request in Phantom

3. **Configure Blockchain Settings**
   - Click "Admin Panel"
   - Enter your SPL token mint address (from pump.fun or other sources)
   - Enter your treasury wallet address (holding the token reserves)
   - Save settings

4. **Claim Login Rewards**
   - Click "Claim Hourly Drop" to claim your tokens
   - One claim per hour per wallet

5. **Register Games**
   - In Admin Panel, add game configurations
   - Specify game title, type (HTML or PPSSPP), and source URL
   - Games appear in the arena selector bar

## Configuration

### Token Mint Address
Your SPL token's mint address. Find this on:
- Pump.fun token page
- Solscan blockchain explorer
- Your token's official documentation

### Treasury Wallet Address
The wallet holding your token reserves for distribution. This address:
- Must have sufficient token balance
- Will be used to authorize token transfers to claimers

### Game Configuration
- **Game Title**: Display name for the game
- **Source Type**: 
  - `HTML / JS App (Embed)`: Web-based games
  - `PPSSPP Emulator Fork`: PSP game emulator instances
- **Source URL / Path**: Direct link or local path to the game

## Technical Stack

- **Frontend**: Vanilla HTML5, CSS3, JavaScript
- **Blockchain**: Solana Web3.js, SPL Token
- **Wallet**: Phantom Wallet
- **Storage**: Browser localStorage

## API & Blockchain Interaction

### Solana Connection
- RPC Endpoint: `https://api.mainnet-beta.solana.com`
- Network: Mainnet Beta (production)

### Token Operations
- Reads token balances via SPL Token program
- Tracks claim timestamps with hourly cooldown
- Frontend-only (no backend private key exposure)

## Security Notes

⚠️ **Important**: This is a frontend-only application. For automated token distribution:
- Consider using a backend API with secure private key management
- Implement a dispenser worker for programmatic transfers
- Never expose private keys in frontend code

## File Structure

```
Metama-center/
├── index.html        # Main application file
├── README.md         # This file
└── [Game assets]     # Optional: game files, emulator data
```

## Development

To extend or modify this application:

1. Edit `index.html` directly for quick changes
2. Modify CSS variables in the `<style>` section for theming
3. Add new game connectors in the `UniversalGameConnector` class
4. Extend wallet functionality in the `toggleWalletConnection()` function

## Browser Compatibility

- Modern browsers with ES6+ support
- Requires Phantom Wallet extension for Solana interaction
- LocalStorage support required

## License

MIT License - Feel free to fork, modify, and redistribute.

## Support

For issues or questions:
- Check the browser console (F12) for error logs
- Ensure Phantom Wallet is installed and unlocked
- Verify Solana RPC endpoint is accessible
- Confirm token mint and treasury addresses are valid

---

Built with ❤️ for the Solana gaming community
