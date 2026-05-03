# Weather Dashboard

A responsive weather application that displays current conditions and a 5-day forecast for any city. Built with vanilla HTML, CSS, and JavaScript using the OpenWeatherMap API.

![Weather Dashboard Screenshot](screenshot.png)

## 🌐 Live Demo

[View the live app](https://alexrivera.github.io/weather-dashboard)

## ✨ Features

- Search for any city worldwide
- Display current temperature, humidity, wind speed, and conditions
- 5-day forecast with daily high/low temperatures
- Responsive design — works on mobile and desktop
- Saves recent searches to localStorage

## 🛠️ Technologies Used

- **HTML5** — Semantic markup and accessibility
- **CSS3** — Flexbox, CSS Grid, custom properties, media queries
- **JavaScript** — Fetch API, DOM manipulation, localStorage
- **OpenWeatherMap API** — Weather data
- **Git & GitHub** — Version control

## 📋 Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- An OpenWeatherMap API key (free at [openweathermap.org](https://openweathermap.org/api))

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/alexrivera/weather-dashboard.git
cd weather-dashboard
```

### 2. Add your API key

Open `js/api.js` and replace the placeholder with your API key:

```javascript
const API_KEY = 'your_api_key_here';
```

### 3. Open in browser

Open `index.html` in your browser. No build step required.

## 📁 Project Structure

```
weather-dashboard/
├── index.html          # Main HTML file
├── css/
│   ├── style.css       # Main styles
│   └── responsive.css  # Media queries
├── js/
│   ├── app.js          # Main application logic
│   ├── api.js          # API calls
│   └── ui.js           # DOM manipulation
├── images/
│   └── icons/          # Weather condition icons
└── README.md
```

## 🔧 How It Works

1. User enters a city name in the search bar
2. App calls the OpenWeatherMap API with the city name
3. API returns current weather and forecast data
4. App renders the data to the DOM
5. Search history is saved to localStorage

## 📱 Screenshots

| Desktop | Mobile |
|---|---|
| ![Desktop view](screenshots/desktop.png) | ![Mobile view](screenshots/mobile.png) |

## 🐛 Known Issues

- City names with special characters may not search correctly
- API has a rate limit of 60 calls/minute on the free tier

## 🗺️ Roadmap

- [ ] Add geolocation support (use current location)
- [ ] Add hourly forecast view
- [ ] Add dark mode
- [ ] Add unit toggle (Celsius/Fahrenheit)

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/add-dark-mode`)
3. Commit your changes (`git commit -m 'Add dark mode toggle'`)
4. Push to the branch (`git push origin feature/add-dark-mode`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Alex Rivera**
- GitHub: [@alexrivera](https://github.com/alexrivera)
- LinkedIn: [Alex Rivera](https://linkedin.com/in/alexrivera)
- Email: alex@example.com

## 🙏 Acknowledgments

- [OpenWeatherMap](https://openweathermap.org/) for the free weather API
- [Font Awesome](https://fontawesome.com/) for the icons
- Frontend Bootcamp instructors for the guidance

---

*Built as part of the Frontend Bootcamp — Module 05: JavaScript Basics*
