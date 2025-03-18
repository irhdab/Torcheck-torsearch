# TorCheck & TorSearch 🌐

![Tor](https://img.shields.io/badge/Tor-7D4698?logo=torproject&logoColor=white)

Web utility verifying Tor network connectivity and enabling anonymous search through multiple engines.

**Live Demo**: [check-tor-n-search-53rh9.kinsta.page](https://check-tor-n-search-53rh9.kinsta.page/)

## Features
- **Tor Verification**: Instant check using official Tor Project exit node servers
- **Multi-Engine Search**:  
  | Engine | Tor Network | Clearnet |
  |--------|-------------|----------|
  | Ahmia  | ✅          | ❌       |
  | Google | ❌          | ✅       |
  | DuckDuckGo | ❌    | ✅       |
- **Anonymized Requests**: No search query logging
- **Client-Side Execution**: Runs entirely in browser

## Usage
1. **Connection Check**  
   Automatically detects Tor status on page load

2. **Search Interface**  
   ```
   // Example search implementation
   function search(query, engine) {
     const endpoint = engine === 'ahmia' 
       ? 'http://juhanurmihxlp77nkq76byazcldy2hlmovfu2epvl5ankdibsot4csyd.onion/search' 
       : `https://${engine}.com/search?q=${encodeURIComponent(query)}`;
     window.open(endpoint, '_blank');
   }
   ```

## Security Considerations
- **IP Masking**: Relies on existing Tor browser configuration
- **Limitations**:  
  - Google/DuckDuckGo searches reveal IP without Tor
  - Browser fingerprinting risks still exist

## Project Structure
```
Torcheck-torsearch/
├── index.html          # Main interface
├── style.css           # Presentation layer
├── script.js           # Logic implementation
└── README.md           # Documentation
```

## Local Deployment
1. Clone repository:
   ```
   git clone https://github.com/irhdab/Torcheck-torsearch.git
   ```
2. Host files on web server
3. Access via `localhost:port`

## Recommended Stack
- Tor Browser Bundle for secure access
- Node.js/http-server for local testing
- Let's Encrypt SSL for production
