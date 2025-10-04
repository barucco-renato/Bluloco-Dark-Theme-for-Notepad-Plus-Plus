# Bluloco Dark Theme for Notepad++

A complete port of the Bluloco Dark Visual Studio Code theme to Notepad++. This theme brings the beautiful, carefully crafted Bluloco color scheme to Notepad++ with full syntax highlighting support.

![Bluloco Dark Theme Preview](https://github.com/uloco/theme-bluloco-dark/raw/master/images/theme-screenshot-dark.png)

## 🎨 About Bluloco

Bluloco is a sophisticated color scheme that combines blue-based accents with a carefully balanced palette that's easy on the eyes during long coding sessions. The dark variant provides excellent contrast while maintaining readability.

## 📋 Conversion Process

### Step 1: Analysis of Source Themes

#### VSCode Theme Structure Analysis
The original Bluloco Dark theme uses a JSON structure with:
- `colors`: Global UI colors (background, foreground, panels, etc.)
- `tokenColors`: Syntax token colors for different programming constructs
- `semanticTokenColors`: Additional semantic highlighting

#### Notepad++ Theme Structure Analysis
Notepad++ uses XML configuration with:
- `GlobalStyles`: Editor-wide settings (background, caret, selection, etc.)
- `LexerStyles`: Language-specific syntax highlighting rules
- Color format: RGB hex values without `#` prefix

### Step 2: Color Mapping Strategy

#### Core Color Palette Mapping
| VSCode Color | Notepad++ Color | Usage |
|--------------|-----------------|-------|
| `#282c34` | `282C34` | Main background |
| `#abb2bf` | `ABB2BF` | Default text |
| `#636d83` | `636D83` | Comments |
| `#10b1fe` | `10B1FE` | Keywords, storage types |
| `#3fc56b` | `3FC56B` | Functions, methods |
| `#ff6480` | `FF6480` | Classes, types |
| `#f9c859` | `F9C859` | Strings, regex |
| `#ff78f8` | `FF78F8` | Numbers, constants |
| `#7a82da` | `7A82DA` | Operators, punctuation |
| `#3691ff` | `3691FF` | Tags, HTML elements |
| `#ff936a` | `FF936A` | Attributes, parameters |
| `#ce9887` | `CE9887` | Object properties, variables |

#### UI Element Mapping
- **Editor Background**: `#282c34` → `282C34`
- **Current Line**: `#2d333d` → `2D333D`
- **Selection**: `#0084ff4b` → `0084FF` (simplified)
- **Line Numbers**: `#636d83` on `#22252a` background
- **Caret Color**: `#ffcc00` → `FFCC00`

### Step 3: Syntax Token Conversion

#### Language-Specific Mappings

**C/C++/Java Family:**
- Preprocessor: `#10b1fe` (blue)
- Instructions: `#10b1fe` (blue)
- Types: `#ff6480` (red-pink)
- Strings: `#f9c859` (yellow)
- Numbers: `#ff78f8` (pink)

**Python:**
- Keywords: `#10b1fe` (blue)
- Function definitions: `#3fc56b` (green)
- Class names: `#ff6480` (red-pink)
- Triple quotes: `#636d83` (comments color)

**JavaScript:**
- Keywords: `#10b1fe` (blue)
- Strings: `#f9c859` (yellow)
- Regex: `#f9c859` (yellow)

**HTML/XML:**
- Tags: `#3691ff` (bright blue)
- Attributes: `#ff936a` (orange)
- Values: `#ff78f8` (pink)

**CSS:**
- Selectors: `#3691ff` (blue)
- Properties: `#ce9887` (brown)
- Values: `#ff78f8` (pink)
- Classes/IDs: `#3fc56b` (green)

### Step 4: XML Structure Implementation

#### Global Styles Section
```xml
<GlobalStyles>
    <WidgetStyle name="Default Style" styleID="32" fgColor="ABB2BF" bgColor="282C34"/>
    <WidgetStyle name="Current line background colour" styleID="0" bgColor="2D333D"/>
    <WidgetStyle name="Selected text colour" styleID="0" bgColor="0084FF" fgColor="FFFFFF"/>
    <!-- ... more global styles -->
</GlobalStyles>
```

#### Lexer Styles Section
```xml
<LexerStyles>
    <LexerType name="python" desc="Python" ext="">
        <WordsStyle name="DEFAULT" styleID="0" fgColor="ABB2BF" bgColor="282C34"/>
        <WordsStyle name="COMMENTLINE" styleID="1" fgColor="636D83" bgColor="282C34"/>
        <WordsStyle name="STRING" styleID="3" fgColor="F9C859" bgColor="282C34"/>
        <!-- ... more Python styles -->
    </LexerType>
    <!-- ... more languages -->
</LexerStyles>
```

## 🛠 Installation

### Method 1: Manual Installation

1. **Download the theme file:**
   - Save `bluloco-dark.xml` to your Notepad++ themes directory

2. **Locate Notepad++ themes folder:**
   - Windows: `C:\Users\[YourUsername]\AppData\Roaming\Notepad++\themes\`
   - Or via Notepad++: `Settings` → `Style Configurator` → `Theme` (shows folder location)

3. **Apply the theme:**
   - Open Notepad++
   - Go to `Settings` → `Style Configurator`
   - Select "bluloco-dark" from the theme dropdown
   - Click "Save & Close"

### Method 2: Import via Style Configurator

1. Open Notepad++
2. Go to `Settings` → `Style Configurator`
3. Click the "Import" button
4. Navigate to and select the `bluloco-dark.xml` file
5. The theme will be automatically installed and selected

## 📁 File Structure

```
bluloco-dark-theme/
├── bluloco-dark.xml          # Main theme file
├── README.md                 # This file
└── screenshots/              # Theme preview images
    ├── python.png
    ├── javascript.png
    ├── html.png
    └── css.png
```

## 🎯 Supported Languages

The theme includes syntax highlighting for:

- **C/C++/Objective-C**
- **Java/C#**
- **Python**
- **JavaScript/TypeScript**
- **HTML/XML**
- **CSS**
- **PHP**
- **SQL**
- **JSON**
- **Batch files**
- **INI configuration**
- **And many more...**

## 🔧 Customization

### Font Recommendations
For the best experience, use these fonts with Bluloco Dark:

- **Consolas** (Windows)
- **Fira Code** (with ligatures)
- **JetBrains Mono**
- **Cascadia Code**

### Adjusting Colors
To modify colors:

1. Open `bluloco-dark.xml` in a text editor
2. Locate the color values (6-character hex codes without `#`)
3. Replace with your preferred colors
4. Save and re-import the theme

### Example: Changing Background Color
```xml
<!-- Change from: -->
<WidgetStyle name="Default Style" styleID="32" fgColor="ABB2BF" bgColor="282C34"/>

<!-- To: -->
<WidgetStyle name="Default Style" styleID="32" fgColor="ABB2BF" bgColor="1E1E1E"/>
```

## 🐛 Troubleshooting

### Theme Not Appearing
- Ensure the XML file is in the correct themes folder
- Check file permissions
- Restart Notepad++ after adding the theme

### Colors Not Applying Correctly
- Verify the XML file is well-formed
- Check for duplicate style definitions
- Ensure color values are 6-character hex without `#`

### Specific Language Not Highlighting
- The theme might not include that specific lexer
- Check if the language is enabled in Notepad++
- Consider adding the lexer style manually

## 🤝 Contributing

Contributions to improve the theme are welcome!

### Areas for Improvement
- Add support for more programming languages
- Improve specific language token mappings
- Create light variant of the theme
- Add screenshots for different languages

### Reporting Issues
When reporting issues, please include:
1. Notepad++ version
2. Operating system
3. Specific language/file type having issues
4. Screenshot of the problem

## 📄 License

This theme is based on the [Bluloco Dark theme](https://github.com/uloco/theme-bluloco-dark) by uloco, converted for Notepad++.

Original Bluloco theme is licensed under MIT License.

## 🙏 Acknowledgments

- **uloco** for creating the original Bluloco theme
- **Notepad++ team** for the excellent editor
- **Community contributors** for testing and feedback

## 📞 Support

If you encounter any issues or have questions:

1. Check this README first
2. Open an issue on GitHub
3. Contact the maintainers

---

**Enjoy coding with Bluloco Dark in Notepad++!** 🎉
