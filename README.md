# NBA Logo API

A simple, fast, and reliable static API for accessing official NBA team logos in high-quality SVG format. This repository provides direct access to all 30 NBA team logos through clean, RESTful endpoints.

## Overview

The NBA Logo API delivers scalable vector graphics (SVG) for all National Basketball Association teams. Built for developers who need quick access to NBA team logos for web applications, mobile apps, data visualizations, and sports-related projects.

## Features

- **Complete Coverage**: All 30 NBA team logos included
- **High-Quality SVG Format**: Scalable vector graphics that look crisp at any size
- **Fast Delivery**: Static file serving for optimal performance
- **Simple Integration**: Clean URLs with intuitive team abbreviations
- **Free to Use**: MIT licensed for both personal and commercial projects
- **No Rate Limits**: Direct file access without API key requirements

## Usage

### Basic Endpoint Structure

```
https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/{team-abbreviation}.svg
```

### Example Requests

```html
<!-- Atlanta Hawks Logo -->
<img src="https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/atl.svg" alt="Atlanta Hawks Logo" width="100" height="100">

<!-- Los Angeles Lakers Logo -->
<img src="https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/lal.svg" alt="Los Angeles Lakers Logo" width="100" height="100">

<!-- Golden State Warriors Logo -->
<img src="https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/gsw.svg" alt="Golden State Warriors Logo" width="100" height="100">
```

### JavaScript Integration

```javascript
// Fetch NBA team logo
const getTeamLogo = (teamAbbr) => {
  return `https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/${teamAbbr.toLowerCase()}.svg`;
};

// Usage
const lakersLogo = getTeamLogo('LAL');
const warriorsLogo = getTeamLogo('GSW');
```

### CSS Background Images

```css
.team-logo-lakers {
  background-image: url('https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/lal.svg');
  background-size: contain;
  background-repeat: no-repeat;
}
```

## Available Teams

| Team | Abbreviation | Full Name |
|------|--------------|-----------|
| `atl` | ATL | Atlanta Hawks |
| `bkn` | BKN | Brooklyn Nets |
| `bos` | BOS | Boston Celtics |
| `cha` | CHA | Charlotte Hornets |
| `chi` | CHI | Chicago Bulls |
| `cle` | CLE | Cleveland Cavaliers |
| `dal` | DAL | Dallas Mavericks |
| `den` | DEN | Denver Nuggets |
| `det` | DET | Detroit Pistons |
| `gsw` | GSW | Golden State Warriors |
| `hou` | HOU | Houston Rockets |
| `ind` | IND | Indiana Pacers |
| `lac` | LAC | Los Angeles Clippers |
| `lal` | LAL | Los Angeles Lakers |
| `mem` | MEM | Memphis Grizzlies |
| `mia` | MIA | Miami Heat |
| `mil` | MIL | Milwaukee Bucks |
| `min` | MIN | Minnesota Timberwolves |
| `nop` | NOP | New Orleans Pelicans |
| `nyk` | NYK | New York Knicks |
| `okc` | OKC | Oklahoma City Thunder |
| `orl` | ORL | Orlando Magic |
| `phi` | PHI | Philadelphia 76ers |
| `phx` | PHX | Phoenix Suns |
| `por` | POR | Portland Trail Blazers |
| `sac` | SAC | Sacramento Kings |
| `sas` | SAS | San Antonio Spurs |
| `tor` | TOR | Toronto Raptors |
| `uta` | UTA | Utah Jazz |
| `was` | WAS | Washington Wizards |

## Implementation Examples

### React Component

```jsx
import React from 'react';

const NBATeamLogo = ({ team, size = 50, className = '' }) => {
  const logoUrl = `https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/${team.toLowerCase()}.svg`;
  
  return (
    <img 
      src={logoUrl}
      alt={`${team.toUpperCase()} Logo`}
      width={size}
      height={size}
      className={className}
    />
  );
};

export default NBATeamLogo;
```

### Vue.js Component

```vue
<template>
  <img 
    :src="logoUrl" 
    :alt="`${team} Logo`"
    :width="size"
    :height="size"
    :class="className"
  />
</template>

<script>
export default {
  name: 'NBATeamLogo',
  props: {
    team: { type: String, required: true },
    size: { type: Number, default: 50 },
    className: { type: String, default: '' }
  },
  computed: {
    logoUrl() {
      return `https://raw.githubusercontent.com/gtkacz/nba-logo-api/main/icons/${this.team.toLowerCase()}.svg`;
    }
  }
};
</script>
```

## Best Practices

### Performance Optimization

- **Cache Logos Locally**: For production applications, consider caching frequently used logos to reduce external requests
- **Lazy Loading**: Implement lazy loading for logos that appear below the fold
- **Preload Critical Logos**: Use `<link rel="preload">` for logos that appear immediately on page load

### Accessibility

- Always include descriptive `alt` attributes when using logos in `<img>` tags
- Ensure sufficient color contrast when overlaying logos on backgrounds
- Consider providing alternative text formats for screen readers

### SEO Benefits

- SVG format ensures logos remain crisp across all device pixel densities
- Semantic file naming improves search engine understanding
- Fast loading times contribute to better Core Web Vitals scores

## Contributing

We welcome contributions to improve and expand the NBA Logo API. Please follow these guidelines when contributing:

### How to Contribute

1. **Fork the Repository**: Create a personal fork of the project on GitHub
2. **Create a Feature Branch**: Use a descriptive branch name (e.g., `update-team-logos`, `add-alternative-formats`)
3. **Make Your Changes**: Ensure all changes maintain consistency with existing files
4. **Test Your Changes**: Verify that all logos render correctly and maintain proper aspect ratios
5. **Submit a Pull Request**: Provide a clear description of your changes and their purpose

### Logo Quality Standards

When contributing new or updated logos, please ensure they meet these requirements:

- **File Format**: SVG format only
- **Optimization**: Files should be optimized for web delivery (unnecessary metadata removed)
- **Consistency**: Maintain consistent styling and dimensions across all logos
- **Official Sources**: Use only official team logos from verified NBA sources
- **File Size**: Keep individual files under 50KB when possible for optimal performance

### Naming Conventions

- Logo files must use lowercase team abbreviations as filenames
- Follow the existing three-letter abbreviation system
- Include proper `<title>` elements within SVG files for accessibility

### Code of Conduct

This project adheres to a code of conduct that ensures a welcoming environment for all contributors. We expect participants to:

- Use inclusive and respectful language
- Focus on constructive feedback and collaboration
- Respect differing viewpoints and experiences
- Show empathy toward other community members

### Issue Reporting

When reporting issues, please include:

- Clear description of the problem
- Steps to reproduce the issue
- Expected versus actual behavior
- Browser and device information when relevant

## Technical Specifications

### SVG Requirements

- **Viewbox**: Standardized to ensure consistent scaling
- **Color Profiles**: RGB color space for web compatibility
- **Accessibility**: Include `role="img"` and `aria-describedby` attributes
- **Optimization**: Minified for production use while maintaining readability

### Browser Compatibility

This API supports all modern browsers that handle SVG rendering:

- Chrome 4+
- Firefox 4+
- Safari 4+
- Edge (all versions)
- Internet Explorer 9+

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for complete details.

The MIT License permits both personal and commercial use, modification, distribution, and private use of this software, provided that the original copyright notice and license terms are included.

## Disclaimer

This project is not officially affiliated with the National Basketball Association (NBA) or any of its member teams. All team logos and trademarks are property of their respective owners. This API is provided for educational and development purposes under fair use guidelines.

## Support

For questions, suggestions, or support requests, please:

- Open an issue on GitHub for bug reports or feature requests
- Check existing issues before creating new ones
- Provide detailed information to help us assist you effectively

## Roadmap

Future enhancements under consideration:

- Additional logo variations (alternate logos, wordmarks)
- Historical team logos for defunct franchises
- Multiple output formats (PNG, WebP)
- CDN integration for improved global performance
- Webhook notifications for logo updates

---

**Keywords**: NBA API, basketball logos, SVG icons, sports API, team logos, NBA teams, basketball development, free API, static logo API, web development