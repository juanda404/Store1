# JD Store

A modern and responsive e-commerce web application built with Vanilla JavaScript that consumes the Platzi Fake Store API. This project demonstrates clean API integration, dynamic content rendering, and modern web development practices.

## Description

JD Store is a functional online store that showcases products from various categories including electronics, clothing, and home goods. The application fetches real-time data from the Platzi Fake Store API and presents it in an elegant, user-friendly interface with product cards, pricing, and detailed information.

## Features

- **Dynamic Product Catalog**: Real-time product loading from REST API
- **Responsive Design**: Fully responsive layout that works on desktop, tablet, and mobile devices
- **Product Categories**: Browse products by different categories
- **Product Cards**: Clean and modern product display with images, names, and prices
- **Loading States**: Visual feedback during data fetching
- **Error Handling**: Graceful error management with user-friendly messages
- **Modern UI**: Clean interface with smooth transitions and hover effects

## Technologies

- **HTML5**: Semantic markup structure
- **CSS3**: Modern styling with Flexbox/Grid
- **JavaScript (Vanilla)**: No frameworks, pure JavaScript
- **Fetch API**: For HTTP requests
- **Platzi Fake Store API**: External data source

## Live Demo

![JD Store Preview](https://i.imgur.com/your-screenshot.png)

### Preview
The store features a clean, modern interface with:
- Product grid layout with high-quality images
- Professional product cards with hover effects
- Responsive navigation header
- Footer with links and shopping cart integration
- Price display and product information

## Requirements

- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- Code editor (VS Code recommended)
- Internet connection (to fetch API data)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/juanda404/Store1
```

2. Navigate to the project directory:
```bash
cd Store1
```

3. Open with a local server (choose one option):

**Option 1: Using Python**
```bash
python -m http.server 8000
```

**Option 2: Using Node.js (http-server)**
```bash
npx http-server
```

**Option 3: Using VS Code Live Server**
- Install Live Server extension
- Right-click on `index.html`
- Select "Open with Live Server"

4. Open your browser and navigate to:
```
http://localhost:8000
```

## Project Structure

```
Store1/
│
├── src/
│   ├── assets/              # Static assets
│   └── partials/            # HTML partial components
│       ├── footer.html      # Footer component
│       ├── header.html      # Header component
│       └── index.html       # Main content
│
├── index.html               # Entry point
├── index.js                 # Main JavaScript logic
├── styles.css               # Global styles
├── .gitignore              # Git ignore rules
├── .posthtmlrc             # PostHTML configuration
├── package-lock.json       # NPM dependencies lock
├── package.json            # Project metadata and scripts
└── README.md               # Project documentation
```

## Usage

1. **Browse Products**: Open the application to view the product catalog
2. **View Details**: Hover over product cards to see additional information
3. **Filter by Category**: Use the navigation menu to filter products by category
4. **Responsive View**: Resize your browser to see the responsive design in action

### Code Example

```javascript
// Example of API consumption
const API_URL = 'https://api.escuelajs.co/api/v1';

async function fetchProducts() {
  try {
    const response = await fetch(`${API_URL}/products`);
    
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    
    const products = await response.json();
    renderProducts(products);
    
  } catch (error) {
    console.error('Error fetching products:', error);
    displayError('Failed to load products. Please try again later.');
  }
}

function renderProducts(products) {
  const container = document.getElementById('products-container');
  container.innerHTML = products.map(product => `
    <div class="product-card">
      <img src="${product.images[0]}" alt="${product.title}">
      <h3>${product.title}</h3>
      <p class="price">$${product.price}</p>
    </div>
  `).join('');
}
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/products` | Get all products |
| GET    | `/products/:id` | Get single product by ID |
| GET    | `/products/?categoryId=:id` | Get products by category |
| GET    | `/categories` | Get all categories |
| GET    | `/categories/:id` | Get single category |

**Base URL**: `https://api.escuelajs.co/api/v1`

## Key Functionalities

### Product Display
- Grid layout with responsive columns
- Product images with fallback handling
- Price formatting with currency symbol
- Smooth hover animations

### Category Filtering
- Dynamic category loading from API
- Filter products by selected category
- Visual feedback for active category

### Error Management
- Network error handling
- 404 response management
- API timeout handling
- User-friendly error messages

## Browser Support

| Browser | Version |
|---------|---------|
| Chrome  | 90+     |
| Firefox | 88+     |
| Safari  | 14+     |
| Edge    | 90+     |

## Contributing

Contributions are welcome! To contribute:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Roadmap

- [ ] Add shopping cart functionality
- [ ] Implement product search feature
- [ ] Add pagination for large product lists
- [ ] Implement product detail view
- [ ] Add dark mode support
- [ ] Include product rating and reviews
- [ ] Add checkout simulation
- [ ] Implement local storage for cart persistence

## Known Issues

- Some product images may fail to load due to API limitations
- Limited to GET requests (Platzi API free tier)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

**Juan David** - [@juanda404](https://github.com/juanda404)

## Acknowledgments

- [Platzi Fake Store API](https://fakeapi.platzi.com/) - API provider
- Inspiration from modern e-commerce platforms
- Web development community for best practices

## Resources

- [API Documentation](https://fakeapi.platzi.com/en/rest/introduction)
- [Fetch API Guide](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [JavaScript Best Practices](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

⭐️ If you found this project helpful, please consider giving it a star on GitHub!

**Built with ❤️ using Vanilla JavaScript**