# Legrand AV to Q360 Data Mapper

## Overview
This web application converts Legrand AV pricing Excel files into the Q360 Load Sheet format. It's designed to run entirely in the browser using JavaScript and the XLSX.js library.

## Features
- Drag & drop or click to upload Excel files
- Automatic column detection and mapping
- Filters out items with $0.00 pricing
- Exports to Q360 Load Sheet format
- No server required - runs entirely in the browser

## Column Mappings
The application maps Legrand AV pricing columns to Q360 columns as follows:

| Legrand AV Column | Q360 Column(s) |
|------------------|----------------|
| Brand | MANUFACTURER |
| Part Number | MASTERNO, PARTNO |
| Description | DESCRIPTION |
| Your Price | STANDARDCOST |
| MSRP | MSRP |

## Additional Processing Rules
- Rows with $0.00 in "Your Price" are automatically excluded
- TAXABLE and USETAXFLAG are set to 'Y' for all items
- All other Q360 columns are left blank for manual configuration

## Hosting on GitHub Pages

### Step 1: Create a GitHub Repository
1. Go to GitHub and create a new repository
2. Name it something like `legrand-av-mapper`
3. Make it public
4. Initialize with a README (optional)

### Step 2: Upload the HTML File
1. Upload the `legrand_av_mapper_app.html` file to your repository
2. Optionally rename it to `index.html` for cleaner URLs

### Step 3: Enable GitHub Pages
1. Go to Settings → Pages in your repository
2. Under "Source", select "Deploy from a branch"
3. Choose "main" branch and "/ (root)" folder
4. Click Save

### Step 4: Access Your App
After a few minutes, your app will be available at:
- `https://[your-username].github.io/[repository-name]/`
- Or if you renamed to index.html: `https://[your-username].github.io/[repository-name]/`

## Usage Instructions
1. Open the web application in your browser
2. Click the upload area or drag and drop a Legrand AV pricing Excel file
3. Click "Process File"
4. Download the converted Q360 Load Sheet

## File Format Requirements
- Input file must be .xlsx format
- Must contain columns: Brand, Part Number, Description, Your Price, MSRP
- Column headers can contain extra spaces or non-breaking spaces (they will be cleaned automatically)

## Browser Compatibility
- Works in all modern browsers (Chrome, Firefox, Safari, Edge)
- Requires JavaScript to be enabled

## Technical Details
- Built with vanilla JavaScript (no frameworks required)
- Uses XLSX.js library (loaded from CDN)
- All processing happens client-side
- No data is sent to any server

## Troubleshooting
- **Error: Could not find header row**: Make sure your Excel file has the required column headers
- **Error: No valid data rows found**: Check that your file has data rows with non-zero prices
- **File not downloading**: Check browser popup blocker settings

## License
This tool is provided as-is for use with Legrand AV pricing files and Q360 systems.

## Support
For issues or questions, please create an issue in the GitHub repository.