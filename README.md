# Proxy Rules Collection

Professional rule sets for iOS proxy applications: **Loon**, **Shadowrocket**, and **Stash**.

## 🇫🇷 Optimisé pour la France

**Ces configurations sont spécifiquement développées pour un usage en France.**

### Objectifs principaux :

- **🚀 Optimisation des flux** : Routage intelligent pour minimiser la latence et maximiser les performances
- **🔒 Sécurité renforcée** : Blocage des trackers, publicités et domaines malveillants
- **⚡ Performance** : Accès direct aux sites français et européens, proxy uniquement pour les services nécessaires
- **🎯 Ciblage précis** : Règles configurées pour l'écosystème internet français

### Configuration par défaut :

- **DIRECT** : Sites français, européens et services locaux (latence minimale)
- **PROXY** : Streaming international (YouTube, Netflix), réseaux sociaux, services globaux
- **REJECT** : Trackers, publicités, domaines malveillants

---

## 🌐 Documentation Interactive

**📱 [Voir le site web complet (en français)](https://lwmmedia.github.io/proxy-rules/)**

*Guide interactif avec installation pas à pas, explications détaillées et liens de téléchargement pour toutes les configurations.*

> **Note:** Si le lien GitHub Pages ne fonctionne pas encore, utilisez ce [lien de prévisualisation](https://htmlpreview.github.io/?https://github.com/lwmmedia/Proxy-rules-public/blob/main/index.html).

---

## 🚀 Quick Start

### Loon

```ini
[Rule]
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/youtube.list,YouTube,tag=YouTube,enabled=true
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/netflix.list,Netflix,tag=Netflix,enabled=true
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/social/telegram.list,Telegram,tag=Telegram,enabled=true
```

### Shadowrocket

```ini
[Rule]
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/youtube.list,YouTube
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/netflix.list,Netflix
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/social/telegram.list,Telegram
```

### Stash

```yaml
rule-providers:
  YouTube:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/youtube.list
    interval: 86400
  Netflix:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/netflix.list
    interval: 86400

rules:
  - RULE-SET,YouTube,YouTube
  - RULE-SET,Netflix,Netflix
```

## 📁 Available Rules

### 🎬 Streaming Services

|Service    |Rule File                                     |Domains|Description                       |
|-----------|----------------------------------------------|-------|----------------------------------|
|**YouTube**|[`youtube.list`](rules/streaming/youtube.list)|15+    |YouTube, YouTube Music, YouTube TV|
|**Netflix**|[`netflix.list`](rules/streaming/netflix.list)|20+    |Netflix global streaming          |

### 💬 Social Media & Communication

|Service      |Rule File                                    |Domains|Description                   |
|-------------|---------------------------------------------|-------|------------------------------|
|**Telegram** |[`telegram.list`](rules/social/telegram.list)|25+    |Telegram messaging + IP ranges|
|**Discord**  |[`discord.list`](rules/social/discord.list)  |15+    |Discord voice/text chat       |
|**Twitter/X**|[`twitter.list`](rules/social/twitter.list)  |12+    |Twitter/X social platform     |

### 🌐 Global Tech Services

|Service      |Rule File                                      |Domains|Description                         |
|-------------|-----------------------------------------------|-------|------------------------------------|
|**Google**   |[`google.list`](rules/global/google.list)      |200+   |Google Search, Gmail, Drive, Android|
|**Apple**    |[`apple.list`](rules/global/apple.list)        |30+    |iCloud, App Store, Apple Music      |
|**Microsoft**|[`microsoft.list`](rules/global/microsoft.list)|35+    |Office 365, Azure, Teams, Xbox      |

## 🔗 Direct URLs

Copy-paste ready URLs for immediate use:

### Streaming

```
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/youtube.list
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/netflix.list
```

### Social

```
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/social/telegram.list
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/social/discord.list
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/social/twitter.list
```

### Global Services

```
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/global/google.list
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/global/apple.list
https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/global/microsoft.list
```

## 📋 Complete Configurations

### Loon Production Configuration

A complete, production-ready configuration for Loon is available here:
[`loon/complete.conf`](configs/loon/complete.conf)

### Shadowrocket Optimized Configuration

A complete, optimized configuration for Shadowrocket is available here:
[`shadowrocket/complete.conf`](configs/shadowrocket/complete.conf)

### Stash Advanced Configuration

An advanced, feature-rich configuration for Stash is available here:
[`stash/complete.yaml`](configs/stash/complete.yaml)

## 🛠️ Rule Format Standards

Rules follow proxy app standard format:

```ini
# Comments start with #
DOMAIN-SUFFIX,example.com          # Matches example.com and all subdomains
DOMAIN-KEYWORD,example             # Matches domains containing "example"  
DOMAIN,exact.example.com           # Exact domain match only
IP-CIDR,192.168.1.0/24,no-resolve  # IP range with no DNS resolution
USER-AGENT,*App*                   # User agent pattern matching
```

## 📊 Rule Statistics

|Category     |Files|Total Domains|Coverage                    |
|-------------|-----|-------------|----------------------------|
|**Streaming**|2    |35+          |YouTube, Netflix            |
|**Social**   |3    |52+          |Telegram, Discord, Twitter/X|
|**Global**   |3    |265+         |Google, Apple, Microsoft    |
|**Total**    |**8**|**352+**     |**Comprehensive**           |

## 🔄 Update Policy

- **Manual Updates**: Applied when services add new domains or change infrastructure
- **Version Control**: All changes tracked via Git commits with detailed descriptions
- **Testing**: Rules validated before deployment to prevent connectivity issues
- **Community**: Pull requests welcome for additions and improvements

## 💡 Usage Best Practices

### Performance Optimization

1. **Start Minimal**: Begin with essential services (YouTube, Google)
1. **Test Individually**: Add one rule set at a time to identify issues
1. **Monitor Latency**: Some rules may impact connection speed
1. **Regular Cleanup**: Remove unused rule sets to improve performance

### Troubleshooting

```ini
# Debug connectivity issues
RULE-SET,https://raw.githubusercontent.com/lwmmedia/Proxy-rules-public/main/rules/streaming/youtube.list,DIRECT,tag=YouTube-Debug
# Test if rules work by temporarily routing to DIRECT
```

### Enterprise Deployment

- Use dedicated proxy groups for different service categories
- Implement fallback mechanisms for critical services
- Monitor proxy server performance per rule set
- Regular rule effectiveness auditing

## 🏗️ Repository Structure

```
proxy-rules/
├── README.md                    # This documentation
├── rules/
│   ├── streaming/              # Video/audio streaming services
│   │   ├── youtube.list        # YouTube ecosystem (15+ domains)
│   │   └── netflix.list        # Netflix global (20+ domains)
│   ├── social/                 # Social media & communication
│   │   ├── telegram.list       # Telegram + IP ranges (25+ rules)
│   │   ├── discord.list        # Discord platform (15+ domains)
│   │   └── twitter.list        # Twitter/X platform (12+ domains)
│   └── global/                 # International tech services
│       ├── google.list         # Google ecosystem (200+ domains)
│       ├── apple.list          # Apple services (30+ domains)
│       └── microsoft.list      # Microsoft suite (35+ domains)
└── configs/                    # Complete configurations
    ├── loon/
    ├── shadowrocket/
    └── stash/
```

## 🤝 Contributing

### Adding New Services

1. **Fork** the repository
1. **Create** rule file in appropriate category (`/rules/streaming/`, `/rules/social/`, `/rules/global/`)
1. **Follow** naming convention: `servicename.list`
1. **Include** comprehensive domain coverage
1. **Test** rules in production environment
1. **Submit** pull request with detailed description

### Rule Quality Standards

- **Official Domains**: Use only legitimate service domains
- **Comprehensive**: Include CDN, API, and media domains
- **Tested**: Verify functionality before submission
- **Documented**: Add comments explaining domain purposes
- **Formatted**: Follow consistent syntax and spacing

### Issue Reporting

- **Service Not Working**: Report with specific app and proxy configuration
- **Missing Domains**: Provide domain names and evidence of service relationship
- **Performance Issues**: Include connection metrics and device information

## 📞 Support & Resources

- **Issues**: [GitHub Issues](https://github.com/lwmmedia/Proxy-rules-public/issues)
- **Feature Requests**: Use GitHub Issues with `enhancement` label
- **Documentation**: Check README.md for latest information
- **Community**: Star the repo and share with other users

## 📜 License & Legal

**License**: MIT License - Free for personal and commercial use

**Legal Disclaimer**:

- These rules are for educational and legitimate proxy use cases
- Users must comply with local laws and service terms of use
- Some services may prohibit proxy usage in their terms
- Repository maintainer not responsible for service disruptions
- Use at your own risk and responsibility

## 🔒 Privacy & Security

- **No Tracking**: Rules contain only routing information, no personal data
- **Open Source**: All rules publicly auditable on GitHub
- **No Analytics**: No usage statistics or user behavior tracking
- **Secure Delivery**: Rules served via HTTPS from GitHub’s CDN

-----

**Repository**: https://github.com/lwmmedia/Proxy-rules-public  
**Maintainer**: lwmmedia  
**Last Updated**: January 2025  
**Version**: 1.0.0

⭐ **Star this repo** if you find it useful!