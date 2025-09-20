# Gblii-Fresh-Guava-
In today's fast-paced world, maintaining a healthy lifestyle shouldn't be a luxury – it should be effortless. Gblii Fresh Guava brings premium, farm-fresh guava directly to your doorstep, making your daily dose of natural goodness as convenient as a few clicks.  
# 🥑 Gblii Fresh Guava - Fresh Fruit Delivery System

> **Fresh • Natural • Delivered Daily**

A complete web-based delivery system for fresh guava fruit, designed for busy professionals and health-conscious families who value convenience and quality.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Architecture](#system-architecture)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Usage Guide](#usage-guide)
- [Configuration](#configuration)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## 🎯 Overview

Gblii Fresh Guava is a dual-interface delivery management system consisting of:

1. **Customer Frontend** - User-friendly ordering interface for customers
2. **Admin Dashboard** - Comprehensive order management system for business owners

The system enables same-day fresh fruit delivery with real-time order tracking, WhatsApp integration, and comprehensive business analytics.

### Target Audience
- **Busy Professionals** seeking convenient healthy snacking
- **Young Parents** wanting fresh, natural options for their families  
- **Health Enthusiasts** maintaining daily fresh fruit consumption

## ✨ Features

### Customer Frontend
- 🛒 **Intuitive Order Interface** - Easy quantity selection with +/- buttons
- 🎯 **Special Siti Combo** - Exclusive pricing for customers named "Siti"
- 💳 **Multiple Payment Options** - COD and QR payment methods
- 📱 **Mobile Responsive** - Optimized for all device sizes
- 🎉 **Personalized Thank You** - Custom confirmation messages in Bahasa Malaysia
- ⚡ **Real-time Calculations** - Instant total updates

### Admin Dashboard
- 📊 **Live Statistics** - Daily orders, revenue, and performance metrics
- 🔍 **Advanced Filtering** - Filter by date, status, payment method, customer name
- 📞 **WhatsApp Integration** - Direct customer communication from dashboard
- 📈 **Order Management** - Status tracking (pending/completed)
- 📄 **CSV Export** - Order data export for record keeping
- 🔄 **Auto-refresh** - Real-time data updates every 30 seconds

## 🏗️ System Architecture

```
gblii-fresh-guava/
├── customer/                 # Customer-facing frontend
│   ├── index.html           # Main order interface
│   ├── assets/              # Styles, scripts, images
│   └── components/          # Reusable UI components
│
├── admin/                   # Admin dashboard
│   ├── dashboard.html       # Order management interface
│   ├── assets/              # Admin-specific assets
│   └── modules/             # Dashboard modules
│
├── shared/                  # Shared resources
│   ├── config.js           # System configuration
│   ├── utils.js            # Common utilities
│   └── api/                # API endpoints (future)
│
└── docs/                   # Documentation
    ├── README.md           # This file
    ├── SETUP.md            # Detailed setup guide
    └── API.md              # API documentation
```

## 🚀 Quick Start

### Prerequisites
- Web browser (Chrome, Firefox, Safari, Edge)
- Web server (Apache, Nginx) or static hosting service
- (Optional) Text editor for customization

### 1-Minute Setup
1. **Download** or clone the repository
2. **Upload** the files to your web server
3. **Access** the customer interface at `yourdomain.com/customer/`
4. **Access** the admin dashboard at `yourdomain.com/admin/dashboard.html`

That's it! The system uses localStorage for data persistence, so no database setup is required initially.

## 📥 Installation

### Option 1: Static Web Hosting
```bash
# Upload entire folder to your hosting service
# Access via your domain
```

### Option 2: GitHub Pages
```bash
# 1. Fork or clone this repository
git clone https://github.com/yourusername/gblii-fresh-guava.git

# 2. Enable GitHub Pages in repository settings
# 3. Access via: https://yourusername.github.io/gblii-fresh-guava/customer/
```

### Option 3: Local Development
```bash
# Clone the repository
git clone https://github.com/yourusername/gblii-fresh-guava.git

# Navigate to project directory  
cd gblii-fresh-guava

# Serve using Python (or any local server)
python -m http.server 8000

# Access at http://localhost:8000/customer/
```

### Option 4: Cloud Deployment (Netlify/Vercel)
1. Connect your GitHub repository
2. Set build command: `# No build required`
3. Set publish directory: `/`
4. Deploy automatically

## 📖 Usage Guide

### For Customers

#### Placing an Order
1. **Visit** the customer interface
2. **Fill in** personal details (Name, Phone, Address)
3. **Select quantities** using +/- buttons:
   - Guava Slice (RM 2.00/set)
   - Guava Drinks (RM 3.00/set)  
   - Special Siti Combo (RM 17.00) - *ID verification required*
   - Other Combo (RM 19.00)
4. **Choose** payment method (COD or QR)
5. **Review** delivery notes and timing
6. **Click** "Buat Pesanan Sekarang"
7. **Receive** personalized thank you confirmation

#### Special Siti Combo
- **Eligibility**: Customers named "Siti" only
- **Contents**: 4x Guava Slices + 2x Guava Drinks + 1x Corn Cup
- **Price**: RM 17.00 (Special rate)
- **Requirement**: Must present ID during payment

#### Delivery Information
- **Order Deadline**: 11:00 AM for same-day delivery
- **Delivery Window**: 1:00 PM - 5:00 PM
- **Coverage**: [Your delivery areas]
- **Contact**: WhatsApp notifications for delivery updates

### For Admin/Founder

#### Accessing the Dashboard
1. **Navigate** to `/admin/dashboard.html`
2. **Enter admin password** (if configured)
3. **View** today's orders and statistics

#### Managing Orders
1. **Filter orders** by date, status, payment method, or customer name
2. **Click phone numbers** to contact customers via WhatsApp
3. **Update order status** (Pending → Completed)
4. **Export data** to CSV for record keeping
5. **Monitor statistics** for business insights

#### Daily Workflow
1. **Morning (9-11 AM)**: Review new orders, plan delivery routes
2. **Midday (11 AM-1 PM)**: Prepare orders, confirm delivery times
3. **Afternoon (1-5 PM)**: Execute deliveries, update order status
4. **Evening**: Review daily performance, export data if needed

## ⚙️ Configuration

### Basic Settings
Edit `shared/config.js` to customize:

```javascript
const CONFIG = {
    // Business Information
    BUSINESS_NAME: 'Gblii Fresh Guava',
    CONTACT_WHATSAPP: '60123456789',
    DELIVERY_AREAS: ['Kuala Lumpur', 'Selangor'],
    
    // Pricing (in RM)
    PRICES: {
        slice: 2.00,
        drink: 3.00,
        sitiCombo: 17.00,
        otherCombo: 19.00
    },
    
    // Delivery Settings
    ORDER_DEADLINE: '11:00',
    DELIVERY_START: '13:00',
    DELIVERY_END: '17:00',
    
    // Admin Security
    ADMIN_PASSWORD: 'your-secure-password'
};
```

### Theme Customization
Primary brand colors in CSS:
```css
:root {
    --primary-green: #4a7c59;
    --secondary-orange: #ff8c42;
    --light-green: #a8d5a8;
    --background: #f8fff8;
}
```

### Menu Customization
Update menu items in `customer/assets/js/script.js`:
```javascript
const menuItems = [
    {
        id: 'slice',
        name: 'Guava Slice',
        price: 2.00,
        emoji: '🍐🥑'
    },
    // Add more items as needed
];
```

## 🔌 API Documentation

### Current Implementation
The system currently uses **localStorage** for data persistence. Orders are stored locally in the browser.

### Future API Endpoints
Planned endpoints for backend integration:

```
POST /api/orders          # Create new order
GET  /api/orders          # Get all orders  
GET  /api/orders/:id      # Get specific order
PUT  /api/orders/:id      # Update order status
DELETE /api/orders/:id    # Delete order

GET  /api/stats           # Get business statistics
GET  /api/stats/daily     # Get daily stats
GET  /api/stats/monthly   # Get monthly stats
```

### Data Schema
```javascript
{
    orderId: 'GB25092001',
    timestamp: '2024-09-20T14:30:00',
    customerName: 'Siti Aminah',
    contactNumber: '012-345-6789',
    fullAddress: 'Complete delivery address',
    menuOrder: 'COMBO KHAS SITI x1',
    paymentMethod: 'COD',
    totalPrice: 'RM 17.00',
    status: 'pending',
    additionalNote: 'Special requirements'
}
```

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Development Setup
```bash
# Fork the repository
# Clone your fork
git clone https://github.com/yourusername/gblii-fresh-guava.git

# Create a feature branch
git checkout -b feature/your-feature-name

# Make your changes
# Test thoroughly

# Commit and push
git commit -m "Add: your feature description"
git push origin feature/your-feature-name

# Create a Pull Request
```

### Contribution Guidelines
- **Test** all changes on multiple browsers and devices
- **Follow** existing code style and structure
- **Update** documentation for new features
- **Include** screenshots for UI changes
- **Write** clear commit messages

### Areas for Contribution
- [ ] Backend API development
- [ ] Payment gateway integration
- [ ] Mobile app development
- [ ] Advanced analytics features
- [ ] Multi-language support
- [ ] Inventory management system

## 🐛 Troubleshooting

### Common Issues

**Orders not appearing in admin dashboard:**
- Ensure both customer and admin use the same domain/localhost
- Check browser localStorage is enabled
- Try different browsers to isolate the issue

**Mobile display problems:**
- Clear browser cache
- Check viewport meta tag is present
- Test on different devices/screen sizes

**WhatsApp links not working:**
- Verify phone number format (60123456789)
- Test links manually in browser
- Check WhatsApp is installed on mobile devices

**CSV export not working:**
- Try different browsers (Chrome recommended)
- Check popup blockers are disabled
- Ensure orders exist to export

### Browser Compatibility
- ✅ Chrome 70+
- ✅ Firefox 65+  
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Mobile browsers (iOS/Android)

### Performance Optimization
For high-volume usage:
- Implement backend database
- Add server-side caching
- Optimize images and assets
- Consider CDN for static files

## 🔒 Security Considerations

### Admin Access
- Change default admin password
- Use HTTPS in production
- Consider IP whitelisting for admin access
- Implement session timeouts

### Data Protection
- Orders stored locally (localStorage)
- No sensitive payment data stored
- Consider GDPR compliance for customer data
- Implement data backup strategies

### Production Checklist
- [ ] Change all default passwords
- [ ] Enable HTTPS/SSL
- [ ] Configure proper headers
- [ ] Set up monitoring and backups
- [ ] Test all functionality thoroughly

## 📊 Analytics & Monitoring

### Built-in Metrics
- Daily order count and revenue
- Popular menu items
- Payment method preferences  
- Order status tracking
- Customer information database

### External Integration Options
- Google Analytics for web traffic
- WhatsApp Business API for messaging
- Payment gateway analytics
- Customer feedback systems

## 🚀 Roadmap

### Phase 1 (Current)
- ✅ Customer ordering interface
- ✅ Admin dashboard  
- ✅ WhatsApp integration
- ✅ Order management

### Phase 2 (Planned)
- [ ] Backend API development
- [ ] Database integration (MySQL/PostgreSQL)
- [ ] User authentication system
- [ ] Email notifications

### Phase 3 (Future)
- [ ] Payment gateway integration
- [ ] Mobile app (iOS/Android)
- [ ] Advanced analytics dashboard
- [ ] Inventory management
- [ ] Multi-vendor support

## 📞 Support & Contact

### Technical Support
- **Issues**: [GitHub Issues](https://github.com/yourusername/gblii-fresh-guava/issues)
- **Documentation**: [Wiki](https://github.com/yourusername/gblii-fresh-guava/wiki)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/gblii-fresh-guava/discussions)

### Business Inquiries
- **WhatsApp**: +60 123 456 789
- **Email**: info@gbliifresh.com
- **Website**: www.gbliifresh.com

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### Commercial Use
This system is open-source and free for commercial use. We encourage:
- Attribution to original creators
- Sharing improvements with the community
- Contributing back bug fixes and enhancements

---

## 🙏 Acknowledgments

- Built with modern web technologies (HTML5, CSS3, JavaScript)
- Responsive design inspired by modern e-commerce platforms
- WhatsApp integration for seamless customer communication
- Designed for Malaysian market preferences and business practices

---

**Made with ❤️ for fresh fruit lovers and busy professionals**

*Gblii Fresh Guava - Fresh • Natural • Delivered Daily* 🥑🍐
