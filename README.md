# 📍 Geospatial Explorer Pro - Historical Political Map Tracker

An interactive historical mapping system that tracks geographical boundaries, political entities, and named locations across time periods. Built with React, Leaflet, and TailwindCSS.

## ✨ Features

- **Interactive Time Slider**: Navigate through history from 1886 to 2024
- **Dynamic Map Rendering**: View historical political boundaries
- **Location Tracking**: Search and analyze named locations (gazetteer)
- **Duplicate Detection**: Find and analyze locations with identical names
- **Point-in-Polygon Analysis**: Determine which political entity controls a location at any given year
- **Automatic Data Loading**: CSV and GeoJSON files are auto-loaded on page load
- **Fully Offline**: Works completely offline - no external APIs required
- **GitHub Pages Ready**: Deploy directly from your GitHub repository

## 🚀 Quick Start

### Option 1: Direct Use (GitHub Pages)

Simply open `index.html` in your browser. The application will automatically:
1. Load `Dov Play Gaz - Sheet1.csv` (gazetteer/locations)
2. Load `GEO.json` (geopolitical boundaries)

### Option 2: Deploy to GitHub Pages

1. **Initialize a Git repository** (if not already done):
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Geospatial Explorer Pro"
   ```

2. **Push to GitHub**:
   - Create a new repository called `<your-username>.github.io` or `geospatial-explorer`
   - Add the remote and push: 
   ```bash
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / root
   - Save

4. **Access your site**:
   - `https://<your-username>.github.io/` (for `<username>.github.io` repo)
   - `https://<your-username>.github.io/<repo-name>/` (for regular repo)

## 📊 Data Files

### Required Files
- **`Dov Play Gaz - Sheet1.csv`**: Gazetteer with location coordinates
  - Columns: `Hebrew Name`, `English Name`, `Latitude`, `Longitude`, `Alt English Names` (optional)
  
- **`GEO.json`**: GeoJSON file with political boundaries and temporal metadata
  - Required properties: `From` (or `from`, `start_year`), `To` (or `to`, `end_year`)
  - Recommended properties: `Name`, `Status`, `Area`, `Capital`, `Id`/`Holder`

### Optional
- Manual file upload via buttons if auto-load fails

## 🎯 Usage Guide

### Main Analysis Mode
1. **Search Locations**: Use the search box to find locations by Hebrew or English name
2. **View Boundaries**: Click on map regions to see all locations within that political entity
3. **Time Navigation**: Move the slider to view historical changes
4. **Entity Details**: See the political entity name, status, area, and capital for selected year

### Duplicate Detection Mode
1. Switch to "🔍 Duplicate Names" tab
2. Filter by minimum distance between duplicate locations
3. View distance metrics between each duplicate point pair
4. Click on duplicates to navigate to them on the map
5. See which political entity controls each duplicate location

## 🛠️ Technical Details

### Architecture
- **Frontend Framework**: React 18
- **Map Library**: Leaflet 1.9.4
- **Styling**: TailwindCSS
- **Data Processing**: PapaParse (CSV), Turf.js (geospatial analysis)
- **Language**: HTML5 + JSX (Babel standalone)

### Auto-Loading Mechanism
```javascript
// Files are fetched relative to index.html
const csvResponse = await fetch('./Dov Play Gaz - Sheet1.csv');
const geoResponse = await fetch('./GEO.json');
```

### Coordinate System
- Uses WGS84 (EPSG:4251) with latitude/longitude
- Map tiles via CartoDB (light style)

## 🔧 Customization

### Change Map Tiles
Edit this line in `index.html`:
```javascript
L.tileLayer('https://{s}.basemaps.cartocdn.com/light_nolabels/{z}/{x}/{y}{r}.png', {
```

### Adjust Year Range
Change these values:
```html
<input type="range" min="1886" max="2024" step="1" value={year} ... />
```

### Customize Styling
Modify TailwindCSS classes or the `<style>` section for colors and appearance

## ⚕️ Removed Features

### Chat/AI Historical Research (v2.3)
The Gemini API chat feature has been removed to ensure:
- ✓ No external API dependencies
- ✓ Complete offline functionality
- ✓ Simpler deployment to GitHub Pages
- ✓ No security concerns with API keys

To add external API functionality, implement your own fetch endpoints.

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| CSV/GeoJSON not loading | Ensure files are in the same directory as `index.html` |
| Map not displaying | Check browser console for CORS errors |
| Slow performance | Reduce GeoJSON feature count or simplify polygons |
| Markers not visible | Ensure CSV has valid `Latitude`/`Longitude` columns |
| Time slider unresponsive | Check feature date ranges in GeoJSON properties |

## 📝 Browser Support

- Chrome/Edge: ✓ Full support
- Firefox: ✓ Full support
- Safari: ✓ Full support
- IE11: ✗ Not supported

## 📄 License

Your specified license here (e.g., MIT, CC-BY-4.0, etc.)

## 👤 Author

Your name/organization

## 🙏 Credits

- **Leaflet**: Interactive mapping
- **Turf.js**: Geospatial analysis
- **CartoDB**: Map tiles
- **React**: UI framework
- **TailwindCSS**: Styling

## 📧 Support

For issues or questions, please:
1. Check the Troubleshooting section above
2. Review the browser console for error messages
3. Ensure data files are properly formatted

---

**Version**: 2.3 (GitHub Pages Ready)  
**Last Updated**: February 2026
