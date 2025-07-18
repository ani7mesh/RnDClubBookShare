# ISBN Scanner Web Application

## Overview
This web application allows users to scan ISBN barcodes from books using their device's camera and send the collected ISBNs via email. The application validates ISBN formats, prevents duplicates, and provides real-time feedback during scanning.

## Features

- **Camera-Based Scanning**: Uses device camera to scan ISBN barcodes
- **ISBN Validation**: Automatically validates and cleans scanned ISBNs
- **Duplicate Prevention**: Ensures only unique ISBNs are added
- **Visual Feedback**: Provides scanning confirmation with visual cues
- **Email Integration**: One-click email sending with pre-formatted content
- **Responsive Design**: Works on both mobile and desktop devices
- **ISBN Counter**: Shows current count of scanned ISBNs
- **List Management**: Clear button to reset the list

## How to Use

1. Open the application in a browser (requires camera access)
2. Enter your email address in the provided field
3. Point your camera at a book's ISBN barcode
4. The app will automatically detect valid ISBNs and add them to the list
5. Use the "Send ISBNs via Email" button to open your email client with the list
6. Use the "Clear List" button to start a new scanning session

## Technical Requirements

- Modern browser with camera access (Chrome, Firefox, Safari, Edge)
- Internet connection (for loading external libraries)
- Device with camera (mobile recommended for easier scanning)

## Implementation Details

### ISBN Handling
- ISBNs are cleaned of non-digit characters except 'X'
- Validates both ISBN-10 (10 characters) and ISBN-13 (13 characters) formats
- Stores ISBNs in uppercase standardized format

### User Interface
- Clean, responsive design with centered layout
- Visual scan confirmation (green flash)
- Status messages for errors and successes
- ISBN counter to track progress
- Clear button for resetting the list

### Scanning Technology
- Uses HTML5 QR Code Scanner library
- Optimized for EAN-13 barcode format (standard for ISBNs)
- Configurable scanning frame size

### Email Integration
- Uses `mailto:` protocol to open default email client
- Pre-fills subject and body with scanned ISBNs
- Includes ISBN count in email body

## Code Structure

```html
<!DOCTYPE html>
<html>
<head>
  <!-- Metadata, title, and CSS styles -->
</head>
<body>
  <!-- Header -->
  <h1>📚 ISBN Scanner</h1>
  
  <!-- Email input -->
  <input type="email" id="email" placeholder="yourname@example.com" required>
  
  <!-- Scanner container -->
  <div id="reader">...</div>
  
  <!-- Status messages -->
  <div id="status"></div>
  
  <!-- ISBN list -->
  <textarea id="isbns" readonly></textarea>
  
  <!-- Action buttons -->
  <button id="send">Send ISBNs via Email</button>
  <button id="clear">Clear List</button>
  
  <!-- JavaScript functionality -->
  <script>
    // ISBN validation and cleaning functions
    // Scanner initialization and handling
    // Event listeners for buttons
    // Feedback and status functions
  </script>
</body>
</html>
```

## Libraries Used
- [html5-qrcode](https://github.com/mebjas/html5-qrcode) - QR/Barcode scanning library

## Browser Compatibility
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

Note: Mobile browsers provide the best user experience for scanning.

## Future Improvements
- ISBN format verification using checksum
- Cloud storage of scanned ISBNs
- Direct integration with book databases
- Export to CSV/Excel functionality
- Multi-user support with login system
- Dark mode option

## License
This project is open-source and available under the MIT License.