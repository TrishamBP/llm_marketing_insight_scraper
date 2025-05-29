# Website Marketing Analysis Tool

A Python-based tool that automatically scrapes websites and uses AI to extract comprehensive marketing insights including SEO keywords, marketing strategies, user engagement tactics, and more.

## Features

- **Automated Web Scraping**: Uses Selenium WebDriver to extract content from any website
- **AI-Powered Analysis**: Leverages OpenAI's GPT-4o-mini to analyze website content across 9 key marketing aspects
- **Excel Export**: Saves results to a formatted Excel file with proper styling and column widths
- **Batch Processing**: Analyze multiple websites in a single run
- **Headless Browser**: Runs Chrome in headless mode for efficient scraping

## Analysis Categories

The tool analyzes websites across these key aspects:

1. **Marketing Strategies** - Core marketing approaches and tactics
2. **SEO Keywords** - Most relevant keywords for search optimization
3. **User Engagement Tactics** - Interactive features and user incentives
4. **Call-to-Action Phrases** - Primary CTA elements and messaging
5. **Branding Elements** - Brand tone, style, and positioning
6. **Competitor Comparison** - Differentiation strategies
7. **Product Descriptions** - Key features and benefits
8. **Customer Reviews Sentiment** - Overall review sentiment analysis
9. **Social Media Strategy** - Social media integration and tactics

## Prerequisites

- Python 3.7+
- Chrome browser installed
- ChromeDriver installed and configured
- OpenAI API key

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/website-analyzer.git
cd website-analyzer
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Install ChromeDriver:
   - **macOS (Homebrew)**: `brew install chromedriver`
   - **Linux**: Download from [ChromeDriver website](https://chromedriver.chromium.org/)
   - **Windows**: Download and add to PATH

4. Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

## Dependencies

Create a `requirements.txt` file with:

```
selenium==4.15.2
pandas==2.1.3
python-dotenv==1.0.0
openai==1.3.7
openpyxl==3.1.2
```

## Usage

### Basic Usage

1. Edit the `websites` list in the script to include your target URLs:
```python
websites = [
    "https://www.example1.com/",
    "https://www.example2.com/",
    # Add more URLs here
]
```

2. Run the script:
```bash
python website_analyzer.py
```

3. Check the generated `website_analysis.xlsx` file for results.

### Customizing Analysis

You can modify the `aspect_prompts` dictionary to customize what aspects are analyzed:

```python
aspect_prompts = {
    "Custom Aspect": "Your custom prompt here...",
    # Add or modify aspects as needed
}
```

### Output

The tool generates an Excel file with:
- Each website as a row
- Analysis results for each marketing aspect
- Properly formatted columns with auto-adjusted widths
- Bold headers and wrapped text for readability

## Configuration

### ChromeDriver Path
Update the ChromeDriver path in the `Website` class if needed:
```python
service = Service(executable_path="/path/to/your/chromedriver")
```

### Chrome Options
The script runs Chrome in headless mode by default. Modify `chrome_options` to change browser behavior:
```python
chrome_options.add_argument("--headless")  # Remove for visible browser
```

### AI Model
Change the OpenAI model by modifying the model parameter:
```python
model="gpt-4o-mini"  # or "gpt-4", "gpt-3.5-turbo", etc.
```

## Error Handling

The tool includes comprehensive error handling for:
- Failed website connections
- Missing API keys
- OpenAI API errors
- Content extraction failures

Errors are logged in the output Excel file for troubleshooting.

## Limitations

- Requires active internet connection
- Dependent on website structure and JavaScript rendering
- Subject to OpenAI API rate limits
- Some websites may block automated scraping

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This tool is for educational and research purposes. Please ensure you comply with website terms of service and robots.txt files when scraping content. Be respectful of server resources and implement appropriate delays between requests when processing large numbers of websites.

## Support

If you encounter issues or have questions:
1. Check the error messages in the Excel output
2. Verify your ChromeDriver installation and path
3. Ensure your OpenAI API key is valid and has sufficient credits
4. Open an issue on GitHub with detailed error information

---

**Note**: Remember to keep your OpenAI API key secure and never commit it to version control.
