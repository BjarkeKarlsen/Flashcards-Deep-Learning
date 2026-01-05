# 🧠 Deep Learning Flashcard Study App

A comprehensive Express.js web application for studying Deep Learning and Computer Vision exam topics through interactive flashcards. Master all 8 exam topics with 120+ carefully curated flashcards covering Machine Learning fundamentals, CNNs, architectures, object detection, generative models, Vision Transformers, training techniques, and visualization methods.

## 📚 Features

- **8 Complete Topics** covering all exam material:
  1. Machine Learning Fundamentals and Neural Networks
  2. Convolutional Neural Networks (CNNs)
  3. CNN Architectures (AlexNet, VGG, ResNet, etc.)
  4. Object Detection and Segmentation
  5. Generative Models (GANs, VAEs, Autoencoders)
  6. Vision Transformers (ViTs) and Self-Attention
  7. Training and Self-Supervised Learning
  8. Visualizing and Understanding CNNs

- **120+ Professional Flashcards** with detailed Q&A pairs
- **Interactive Learning Interface**:
  - Click cards to flip between question and answer
  - Visual progress bar showing study progress
  - Mastery tracking with "I Know This" button
  - Statistics dashboard (mastered, remaining, accuracy %)
  - Smooth navigation with Previous/Next buttons
  - Color-coded feedback (blue for questions, green for answers)

- **Responsive Design** - Works on desktop, tablet, and mobile
- **Express.js Backend** - Loads flashcard data from JSON API
- **Jade Templating** - Clean, maintainable template structure
- **Real-time Statistics** - Track learning progress per topic

## 🛠 Tech Stack

- **Backend**: Node.js + Express.js
- **Frontend**: Vanilla JavaScript (ES6+)
- **Templating**: Jade/Pug
- **Styling**: CSS3 with CSS Variables
- **Data**: JSON

## 📦 Prerequisites

- Node.js (v12 or higher)
- npm or yarn

## 🚀 Installation & Setup

### 1. Clone or Create Project
```bash
mkdir flashcard-app
cd flashcard-app
```

### 2. Initialize npm
```bash
npm init -y
```

### 3. Install Dependencies
```bash
npm install express jade morgan cookie-parser http-errors
npm install --save-dev nodemon  # For development
```

### 4. Create Directory Structure
```bash
mkdir -p data public/javascripts public/stylesheets routes views bin
```

### 5. Create All Files
See file listing below and copy each file to its respective location.

### 6. Add flashcards.json Data
Copy the complete JSON data (120 flashcards across 8 topics) to `data/flashcards.json`

### 7. Run the Application
```bash
# Development mode (with auto-reload)
npm run dev

# Or production mode
npm start
```

Visit `http://localhost:3000` in your browser.

## 📁 Project Structure

```
flashcard-app/
├── app.js                          # Express app configuration
├── package.json                    # Dependencies
├── bin/
│   └── www                         # Server entry point
├── routes/
│   ├── index.js                   # Home route
│   └── users.js                   # User routes (if needed)
├── views/
│   ├── layout.jade                # Base template
│   ├── flashcards.jade            # Flashcard page
│   ├── index.jade                 # Home page
│   └── error.jade                 # Error page
├── public/
│   ├── javascripts/
│   │   └── app.js                 # Frontend JavaScript
│   ├── stylesheets/
│   │   └── style.css              # Styling
│   └── data/
│       └── flashcards.json        # Flashcard data (optional copy)
├── data/
│   └── flashcards.json            # Primary flashcard data source
└── README.md                       # This file
```

## 📄 File Descriptions

| File | Purpose |
|------|---------|
| `app.js` | Express server configuration, API endpoint for `/api/flashcards` |
| `routes/index.js` | Route handler for home page, renders flashcards template |
| `views/flashcards.jade` | Jade template for flashcard UI |
| `public/javascripts/app.js` | Frontend logic (fetch data, handle interactions) |
| `public/stylesheets/style.css` | All styling with CSS variables for theming |
| `data/flashcards.json` | Complete flashcard dataset (8 topics, 120 cards) |

## 🎯 How to Use

1. **Start Studying**: Open the app and browse any of the 8 topics
2. **Learn Cards**: Click on a flashcard to reveal the answer
3. **Mark Progress**: Click "I Know This" to mark a card as mastered
4. **Track Progress**: Watch the progress bar fill and statistics update
5. **Navigate**: Use Previous/Next buttons to browse through cards
6. **Switch Topics**: Click any topic button to switch study focus

## 🔧 API Endpoints

### Get All Flashcards
```
GET /api/flashcards
```

**Response:**
```json
{
  "topics": [
    {
      "id": "ml",
      "name": "Machine Learning Fundamentals and Neural Networks",
      "cards": [
        {
          "q": "What is linear regression?",
          "a": "A method for modeling the relationship..."
        }
      ]
    }
  ]
}
```

## 🎨 Customization

### Change Colors
Edit CSS variables in `public/stylesheets/style.css`:
```css
:root {
  --color-primary: #2186B4;        /* Main blue */
  --color-success: #4caf50;        /* Green for answers */
  --color-background: #f5f5f5;     /* Light gray bg */
  /* ... more variables ... */
}
```

### Add More Flashcards
Edit `data/flashcards.json` and add cards to any topic array:
```json
{
  "q": "Your question here?",
  "a": "Your answer here"
}
```

### Modify Card Appearance
Update styles in `style.css` - look for `.flashcard`, `.flashcard-text`, etc.

## 🐛 Troubleshooting

### API Returns 500 Error
**Problem**: `Cannot read properties of undefined (reading 'forEach')`

**Solution**: Make sure:
1. `data/flashcards.json` exists in project root
2. JSON is valid (use jsonlint.com to verify)
3. Run: `npm start` and check console logs

### Module Not Found Error
**Problem**: `Cannot find module 'express'`

**Solution**:
```bash
npm install
```

### Port Already in Use
**Problem**: `EADDRINUSE: address already in use :::3000`

**Solution**:
```bash
# Change port (edit bin/www or use environment variable)
PORT=3001 npm start
```

## 📝 Environment Variables

Create a `.env` file (optional):
```
NODE_ENV=development
PORT=3000
```

Load with `npm install dotenv` and add to `app.js`:
```javascript
require('dotenv').config();
```

## 🚀 Deployment

### Deploy to Heroku
```bash
heroku create your-app-name
git push heroku main
```

### Deploy to Vercel
Note: Express apps need serverless configuration. Use traditional hosting (Heroku, Railway) for best compatibility.

## 📊 Study Tips

1. **Master One Topic at a Time**: Focus on completing one topic before moving to the next
2. **Review Regularly**: Revisit completed topics for reinforcement
3. **Track Progress**: Use the accuracy % to identify weak areas
4. **Mix Topics**: Once confident, switch between topics for comprehensive review
5. **Understand Answers**: Don't just memorize - understand the concepts

## 🤝 Contributing

To add more flashcards or improve existing ones:

1. Edit `data/flashcards.json`
2. Maintain consistent Q&A quality
3. Test by restarting the server

## 📞 Support

- Check browser console (F12) for errors
- Verify file paths in error messages
- Ensure Node.js and npm are installed: `node -v` and `npm -v`

## 📜 License

MIT License - Feel free to use and modify for personal study.

## 🎓 About the Content

These flashcards cover comprehensive exam preparation for:
- Deep Learning for Visual Recognition course
- Topics: CNN fundamentals through advanced architectures
- Based on curriculum covering Lectures 1-13
- 120+ cards with detailed explanations and key concepts

---

**Happy Studying! 🚀📚**
