# Reading and Translating Scanned Documents

## Introduction
This project is designed to tackle the issue of extracting text from PDF files that contain scanned documents. The text in such files is embedded within images, making it unsearchable and unselectable. The notebook resolves this by employing Optical Character Recognition (OCR) technology to extract the text. Once extracted, the text is then translated into a specified language using OpenAI's APIs, and the translated content is saved into a Word document.

## Installation
Before running the notebook, you need to install the necessary Python libraries. You can install them using pip with the following command:

```bash
pip install PyMuPDF Pillow pytesseract openai python-docx
```

## API Key
You will also need to obtain an API key from OpenAI for the translation services.

```python
import openai
openai.api_key = 'YOUR_API_KEY_HERE'
```
Replace 'YOUR_API_KEY_HERE' with your actual OpenAI API key.

## Usage
The notebook follows these steps to process the scanned PDF files:

1. **Import Libraries**: The necessary libraries are imported at the beginning of the notebook.
2. **Convert PDF Pages to Images**: Each page of the PDF is converted into an image to prepare for text extraction.
3. **Apply OCR**: OCR is performed on these images to extract the text.
4. **Translate Text**: The extracted text is then translated into the desired language using OpenAI's API.
5. **Save Translation**: Finally, the translated text is saved into a Word document.

To use the notebook, follow the steps outlined in the code and markdown cells, replacing file paths and API keys with your own data.

### Main Functions
- `convert_pdf_to_images(pdf_file_path, output_folder)`: Converts pages of a PDF file into images and saves them to the specified folder.
- Further functions for processing the images with OCR and translating the text would be detailed within the notebook.

## Additional Information
This notebook is particularly useful in scenarios where scanned documents need to be digitized and translated. It automates the process of converting non-selectable text within images into a modifiable and translatable format.

## Dependencies
The notebook requires the following libraries:

- `os`: for interacting with the operating system.
- `fitz` (PyMuPDF): for working with PDF files.
- `PIL` (from Pillow package): for image processing tasks.
- `pytesseract`: for OCR to convert images to text.
- `re`: for regular expression operations, likely used for text cleaning or matching.
- `openai`: for accessing OpenAI's API.
- `docx`: for creating and modifying Word documents.

Ensure that these libraries are installed and properly configured before running the notebook.

## NOTE
Please be advised that our translation process is conducted on a per-page basis. This method may result in inaccuracies when text flows continuously across page boundaries. To mitigate this, we recommend consolidating the entire document into a single string. This should be followed by segmenting (chunking) the text into manageable sections (chunks), which can then be translated individually to ensure greater accuracy.