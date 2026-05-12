<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Word to Jekyll Blog Converter</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mammoth/1.6.0/mammoth.browser.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #2c3e50, #3498db);
            color: white;
            padding: 30px;
            text-align: center;
        }

        .header h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .header p {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .main-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 0;
            min-height: 600px;
        }

        .upload-section, .output-section {
            padding: 30px;
        }

        .upload-section {
            background: #f8f9fa;
            border-right: 1px solid #e9ecef;
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: #2c3e50;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .upload-area {
            border: 3px dashed #3498db;
            border-radius: 15px;
            padding: 40px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: white;
            margin-bottom: 20px;
        }

        .upload-area:hover {
            border-color: #2980b9;
            background: #f0f8ff;
            transform: translateY(-2px);
        }

        .upload-area.dragover {
            border-color: #27ae60;
            background: #f0fff4;
        }

        .upload-area.small {
            padding: 20px;
            margin-bottom: 15px;
        }

        .upload-icon {
            font-size: 3rem;
            margin-bottom: 15px;
            color: #3498db;
        }

        .file-input {
            display: none;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #2c3e50;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 12px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 14px;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #3498db;
        }

        .form-group small {
            color: #666;
            font-size: 0.85em;
            display: block;
            margin-top: 5px;
        }

        .btn {
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
            width: 100%;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.4);
        }

        .btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }

        .btn-secondary {
            background: linear-gradient(135deg, #95a5a6, #7f8c8d);
            margin-top: 10px;
        }

        .btn-secondary:hover {
            box-shadow: 0 5px 15px rgba(149, 165, 166, 0.4);
        }

        .output-section {
            background: #ffffff;
        }

        .output-area {
            background: #f8f9fa;
            border: 1px solid #e9ecef;
            border-radius: 10px;
            padding: 20px;
            min-height: 400px;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            line-height: 1.6;
            overflow-y: auto;
            position: relative;
        }

        .copy-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #27ae60;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 12px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .output-area:hover .copy-btn {
            opacity: 1;
        }

        .copy-btn:hover {
            background: #2ecc71;
        }

        .status {
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            font-weight: 500;
        }

        .status.success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }

        .status.error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }

        .status.info {
            background: #cce7ff;
            color: #004085;
            border: 1px solid #b6d7ff;
        }

        .loading {
            display: none;
            text-align: center;
            padding: 20px;
        }

        .spinner {
            border: 3px solid #f3f3f3;
            border-top: 3px solid #3498db;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 0 auto 10px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .image-preview-area {
            display: none;
            background: white;
            border: 2px solid #e9ecef;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
        }

        .image-preview-area.active {
            display: block;
        }

        .image-preview-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e9ecef;
        }

        .image-preview-header h4 {
            color: #2c3e50;
            font-size: 1.1rem;
        }

        .clear-images-btn {
            background: #e74c3c;
            color: white;
            border: none;
            padding: 6px 12px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.85em;
        }

        .clear-images-btn:hover {
            background: #c0392b;
        }

        .image-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 10px;
        }

        .image-item {
            position: relative;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            padding: 8px;
            background: #f8f9fa;
        }

        .image-item img {
            width: 100%;
            height: 100px;
            object-fit: cover;
            border-radius: 5px;
            margin-bottom: 5px;
        }

        .image-item .image-name {
            font-size: 0.75em;
            color: #666;
            text-align: center;
            word-break: break-all;
        }

        .image-item .remove-img {
            position: absolute;
            top: 12px;
            right: 12px;
            background: #e74c3c;
            color: white;
            border: none;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 14px;
            line-height: 1;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .image-item .remove-img:hover {
            background: #c0392b;
        }

        .checkbox-group {
            margin-bottom: 20px;
        }

        .checkbox-group label {
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            padding: 12px;
            background: white;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .checkbox-group label:hover {
            border-color: #3498db;
            background: #f0f8ff;
        }

        .checkbox-group input[type="checkbox"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .upload-section {
                border-right: none;
                border-bottom: 1px solid #e9ecef;
            }

            .header h1 {
                font-size: 2rem;
            }

            .image-grid {
                grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>📝 Word to Jekyll Converter</h1>
            <p>Transform your Word documents into Jekyll blog posts instantly</p>
        </div>

        <div class="main-content">
            <div class="upload-section">
                <h2 class="section-title">
                    📤 Upload & Configure
                </h2>

                <!-- Optional Image Upload -->
                <div class="checkbox-group">
                    <label>
                        <input type="checkbox" id="includeImagesCheck">
                        <span><strong>Include images in this post</strong></span>
                    </label>
                </div>

                <div id="imageUploadSection" style="display: none;">
                    <div class="upload-area small" id="imageUploadArea">
                        <div class="upload-icon" style="font-size: 2rem;">🖼️</div>
                        <h4>Upload Images (Optional)</h4>
                        <p style="font-size: 0.9em;">Click or drag images here</p>
                        <p style="font-size: 0.8em; color: #666; margin-top: 5px;">Supports JPG, PNG, GIF</p>
                    </div>
                    <input type="file" id="imageInput" class="file-input" accept="image/*" multiple />

                    <div class="image-preview-area" id="imagePreviewArea">
                        <div class="image-preview-header">
                            <h4>📷 Uploaded Images (<span id="imageCount">0</span>)</h4>
                            <button class="clear-images-btn" id="clearImagesBtn">Clear All</button>
                        </div>
                        <div class="image-grid" id="imageGrid"></div>
                    </div>

                    <div class="form-group">
                        <label for="imageFolder">Image Folder Path:</label>
                        <input type="text" id="imageFolder" placeholder="/assets/images/posts/" value="/assets/images/posts/">
                        <small>Where images are stored in your Jekyll site</small>
                    </div>
                </div>

                <!-- Word Document Upload -->
                <div class="upload-area" id="uploadArea">
                    <div class="upload-icon">📄</div>
                    <h3>Upload Word Document</h3>
                    <p>Drop your .docx file here or click to browse</p>
                </div>
                <input type="file" id="fileInput" class="file-input" accept=".docx" />

                <div class="form-group">
                    <label for="titleInput">Article Title:</label>
                    <input type="text" id="titleInput" placeholder="Enter your article title">
                </div>

                <div class="form-group">
                    <label for="categorySelect">Category:</label>
                    <select id="categorySelect">
                        <option value="Administrative">Administrative</option>
                        <option value="Academic">Academic</option>
                        <option value="Clinical">Clinical</option>
                        <option value="Research">Research</option>
                        <option value="Reflections & Musings">Reflections & Musings</option>
                        <option value="Yoga & Wellness">Yoga & Wellness</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="dateInput">Date:</label>
                    <input type="date" id="dateInput">
                </div>

                <button class="btn" id="convertBtn" disabled>Convert to Jekyll Format</button>

                <div class="loading" id="loading">
                    <div class="spinner"></div>
                    <p>Converting your document...</p>
                </div>

                <div id="status"></div>
            </div>

            <div class="output-section">
                <h2 class="section-title">
                    📋 Jekyll Output
                </h2>
                <div class="output-area" id="outputArea">
                    <button class="copy-btn" id="copyBtn">📋 Copy</button>
                    <div id="output">Upload a Word document to see the converted Jekyll format here...</div>
                </div>

                <div id="instructionsArea" style="margin-top: 20px; padding: 20px; background: #fff3cd; border: 2px solid #ffc107; border-radius: 10px; display: none;">
                    <h3 style="color: #856404; margin-bottom: 10px;">📝 Next Steps:</h3>
                    <ol style="color: #856404; line-height: 1.8; margin-left: 20px;">
                        <li>Copy the Jekyll content above</li>
                        <li id="imageStep" style="display: none;"><strong>Upload your images</strong> to <code id="imagePath"></code> in your Jekyll site</li>
                        <li>Create a new file in your <code>_posts</code> folder</li>
                        <li>Name it: <code id="suggestedFilename"></code></li>
                        <li>Paste the content and commit</li>
                    </ol>
                </div>
            </div>
        </div>
    </div>

    <script>
        class WordToJekyllConverter {
            constructor() {
                this.initializeElements();
                this.setupEventListeners();
                this.setDefaultDate();
                this.uploadedImages = [];
            }

            initializeElements() {
                this.uploadArea = document.getElementById('uploadArea');
                this.fileInput = document.getElementById('fileInput');
                this.imageUploadArea = document.getElementById('imageUploadArea');
                this.imageInput = document.getElementById('imageInput');
                this.imageUploadSection = document.getElementById('imageUploadSection');
                this.includeImagesCheck = document.getElementById('includeImagesCheck');
                this.imagePreviewArea = document.getElementById('imagePreviewArea');
                this.imageGrid = document.getElementById('imageGrid');
                this.imageCount = document.getElementById('imageCount');
                this.clearImagesBtn = document.getElementById('clearImagesBtn');
                this.titleInput = document.getElementById('titleInput');
                this.categorySelect = document.getElementById('categorySelect');
                this.dateInput = document.getElementById('dateInput');
                this.imageFolderInput = document.getElementById('imageFolder');
                this.convertBtn = document.getElementById('convertBtn');
                this.output = document.getElementById('output');
                this.copyBtn = document.getElementById('copyBtn');
                this.status = document.getElementById('status');
                this.loading = document.getElementById('loading');
                this.instructionsArea = document.getElementById('instructionsArea');
                this.imageStep = document.getElementById('imageStep');
                this.imagePath = document.getElementById('imagePath');
                this.suggestedFilename = document.getElementById('suggestedFilename');
            }

            setupEventListeners() {
                // Word document upload
                this.uploadArea.addEventListener('click', () => this.fileInput.click());
                this.fileInput.addEventListener('change', (e) => this.handleFileSelect(e));
                this.uploadArea.addEventListener('dragover', (e) => this.handleDragOver(e, this.uploadArea));
                this.uploadArea.addEventListener('dragleave', (e) => this.handleDragLeave(e, this.uploadArea));
                this.uploadArea.addEventListener('drop', (e) => this.handleDrop(e, 'document'));

                // Image upload
                this.includeImagesCheck.addEventListener('change', () => this.toggleImageUpload());
                this.imageUploadArea.addEventListener('click', () => this.imageInput.click());
                this.imageInput.addEventListener('change', (e) => this.handleImageSelect(e));
                this.imageUploadArea.addEventListener('dragover', (e) => this.handleDragOver(e, this.imageUploadArea));
                this.imageUploadArea.addEventListener('dragleave', (e) => this.handleDragLeave(e, this.imageUploadArea));
                this.imageUploadArea.addEventListener('drop', (e) => this.handleDrop(e, 'images'));
                this.clearImagesBtn.addEventListener('click', () => this.clearAllImages());

                // Convert button
                this.convertBtn.addEventListener('click', () => this.convertDocument());

                // Copy button
                this.copyBtn.addEventListener('click', () => this.copyToClipboard());

                // Auto-generate title
                this.fileInput.addEventListener('change', () => this.autoFillTitle());
            }

            setDefaultDate() {
                const today = new Date().toISOString().split('T')[0];
                this.dateInput.value = today;
            }

            toggleImageUpload() {
                if (this.includeImagesCheck.checked) {
                    this.imageUploadSection.style.display = 'block';
                } else {
                    this.imageUploadSection.style.display = 'none';
                    this.clearAllImages();
                }
            }

            handleDragOver(e, element) {
                e.preventDefault();
                element.classList.add('dragover');
            }

            handleDragLeave(e, element) {
                e.preventDefault();
                element.classList.remove('dragover');
            }

            handleDrop(e, type) {
                e.preventDefault();
                const element = type === 'document' ? this.uploadArea : this.imageUploadArea;
                element.classList.remove('dragover');
                
                const files = e.dataTransfer.files;
                if (files.length > 0) {
                    if (type === 'document') {
                        this.handleFile(files[0]);
                    } else {
                        this.handleImages(files);
                    }
                }
            }

            handleFileSelect(e) {
                const file = e.target.files[0];
                if (file) {
                    this.handleFile(file);
                }
            }

            handleFile(file) {
                if (!file.name.endsWith('.docx')) {
                    this.showStatus('Please select a .docx file.', 'error');
                    return;
                }

                this.selectedFile = file;
                this.updateUploadArea(file.name);
                this.convertBtn.disabled = false;
                this.showStatus(`File "${file.name}" loaded successfully!`, 'success');
            }

            updateUploadArea(filename) {
                this.uploadArea.innerHTML = `
                    <div class="upload-icon">✅</div>
                    <h3>File Selected</h3>
                    <p><strong>${filename}</strong></p>
                    <p style="font-size: 0.9em; color: #666;">Click to select a different file</p>
                `;
            }

            handleImageSelect(e) {
                this.handleImages(e.target.files);
            }

            handleImages(files) {
                Array.from(files).forEach(file => {
                    if (file.type.startsWith('image/')) {
                        const reader = new FileReader();
                        reader.onload = (e) => {
                            this.uploadedImages.push({
                                name: file.name,
                                data: e.target.result,
                                file: file
                            });
                            this.updateImagePreview();
                        };
                        reader.readAsDataURL(file);
                    }
                });
            }

            updateImagePreview() {
                if (this.uploadedImages.length > 0) {
                    this.imagePreviewArea.classList.add('active');
                    this.imageCount.textContent = this.uploadedImages.length;
                    
                    this.imageGrid.innerHTML = this.uploadedImages.map((img, index) => `
                        <div class="image-item">
                            <button class="remove-img" onclick="converter.removeImage(${index})">×</button>
                            <img src="${img.data}" alt="${img.name}">
                            <div class="image-name">${img.name}</div>
                        </div>
                    `).join('');
                } else {
                    this.imagePreviewArea.classList.remove('active');
                }
            }

            removeImage(index) {
                this.uploadedImages.splice(index, 1);
                this.updateImagePreview();
            }

            clearAllImages() {
                this.uploadedImages = [];
                this.updateImagePreview();
                this.imageInput.value = '';
            }

            autoFillTitle() {
                if (this.selectedFile && !this.titleInput.value) {
                    const filename = this.selectedFile.name.replace('.docx', '');
                    const title = filename.replace(/[_-]/g, ' ')
                                        .replace(/\b\w/g, l => l.toUpperCase());
                    this.titleInput.value = title;
                }
            }

            async convertDocument() {
                if (!this.selectedFile) return;

                this.showLoading(true);
                this.showStatus('Converting document...', 'info');

                try {
                    const arrayBuffer = await this.selectedFile.arrayBuffer();
                    const result = await mammoth.convertToHtml({ arrayBuffer: arrayBuffer });
                    
                    const jekyllContent = this.convertToJekyll(result.value);
                    this.displayOutput(jekyllContent);
                    this.showInstructions();
                    this.showStatus('Document converted successfully!', 'success');
                    
                } catch (error) {
                    console.error('Conversion error:', error);
                    this.showStatus('Error converting document. Please try again.', 'error');
                } finally {
                    this.showLoading(false);
                }
            }

            convertToJekyll(htmlContent) {
                const title = this.titleInput.value || 'Your Article Title Here';
                const date = this.dateInput.value || new Date().toISOString().split('T')[0];
                const category = this.categorySelect.value;
                const imageFolder = this.imageFolderInput.value || '/assets/images/posts/';

                // Convert tables to markdown first (before other conversions)
                htmlContent = this.convertTablesToMarkdown(htmlContent);

                // Convert HTML to markdown
                let content = htmlContent
                    .replace(/<h1[^>]*>(.*?)<\/h1>/gi, '# $1')
                    .replace(/<h2[^>]*>(.*?)<\/h2>/gi, '## $1')
                    .replace(/<h3[^>]*>(.*?)<\/h3>/gi, '### $1')
                    .replace(/<h4[^>]*>(.*?)<\/h4>/gi, '#### $1')
                    .replace(/<h5[^>]*>(.*?)<\/h5>/gi, '##### $1')
                    .replace(/<h6[^>]*>(.*?)<\/h6>/gi, '###### $1')
                    .replace(/<p[^>]*>(.*?)<\/p>/gi, '$1\n\n')
                    .replace(/<strong[^>]*>(.*?)<\/strong>/gi, '**$1**')
                    .replace(/<b[^>]*>(.*?)<\/b>/gi, '**$1**')
                    .replace(/<em[^>]*>(.*?)<\/em>/gi, '*$1*')
                    .replace(/<i[^>]*>(.*?)<\/i>/gi, '*$1*')
                    .replace(/<ul[^>]*>/gi, '')
                    .replace(/<\/ul>/gi, '\n')
                    .replace(/<ol[^>]*>/gi, '')
                    .replace(/<\/ol>/gi, '\n')
                    .replace(/<li[^>]*>(.*?)<\/li>/gi, '- $1\n')
                    .replace(/<a[^>]*href="([^"]*)"[^>]*>(.*?)<\/a>/gi, '[$2]($1)')
                    .replace(/<[^>]*>/g, '')
                    .replace(/\n\s*\n\s*\n/g, '\n\n')
                    .trim();

                // Add image references if images are uploaded
                let imageSection = '';
                if (this.uploadedImages.length > 0) {
                    this.uploadedImages.forEach((img, index) => {
                        const imgPath = `${imageFolder}${img.name}`;
                        imageSection += `![Image ${index + 1}](${imgPath})\n\n`;
                    });
                }

                const jekyllPost = `---
layout: post
title: "${title}"
date: ${date}
categories: [${category}]
author: Dr Kembhavi
---

${imageSection}${content}

---

*Share your thoughts in the comments below.*`;

                return jekyllPost;
            }

            convertTablesToMarkdown(html) {
                // Create a temporary div to parse HTML
                const tempDiv = document.createElement('div');
                tempDiv.innerHTML = html;
                
                // Find all tables
                const tables = tempDiv.querySelectorAll('table');
                
                tables.forEach(table => {
                    let markdownTable = '\n\n';
                    const rows = table.querySelectorAll('tr');
                    
                    if (rows.length === 0) return;
                    
                    // Process each row
                    rows.forEach((row, rowIndex) => {
                        const cells = row.querySelectorAll('td, th');
                        const cellContents = Array.from(cells).map(cell => 
                            cell.textContent.trim().replace(/\|/g, '\\|')
                        );
                        
                        // Add row
                        markdownTable += '| ' + cellContents.join(' | ') + ' |\n';
                        
                        // Add separator after first row (header)
                        if (rowIndex === 0) {
                            markdownTable += '| ' + cellContents.map(() => '---').join(' | ') + ' |\n';
                        }
                    });
                    
                    markdownTable += '\n';
                    
                    // Replace the table HTML with markdown
                    table.outerHTML = markdownTable;
                });
                
                return tempDiv.innerHTML;
            }

            displayOutput(content) {
                this.output.textContent = content;
                this.copyBtn.style.opacity = '1';
            }

            showInstructions() {
                this.instructionsArea.style.display = 'block';
                
                const title = this.titleInput.value || 'your-article-title';
                const date = this.dateInput.value || new Date().toISOString().split('T')[0];
                const filename = `${date}-${title.toLowerCase().replace(/[^a-z0-9]+/g, '-')}.md`;
                
                this.suggestedFilename.textContent = filename;

                if (this.uploadedImages.length > 0) {
                    this.imageStep.style.display = 'list-item';
                    this.imagePath.textContent = this.imageFolderInput.value || '/assets/images/posts/';
                } else {
                    this.imageStep.style.display = 'none';
                }
            }

            async copyToClipboard() {
                try {
                    await navigator.clipboard.writeText(this.output.textContent);
                    const originalText = this.copyBtn.textContent;
                    this.copyBtn.textContent = '✅ Copied!';
                    setTimeout(() => {
                        this.copyBtn.textContent = originalText;
                    }, 2000);
                } catch (err) {
                    console.error('Failed to copy:', err);
                    this.showStatus('Failed to copy to clipboard', 'error');
                }
            }

            showStatus(message, type) {
                this.status.innerHTML = `<div class="status ${type}">${message}</div>`;
                setTimeout(() => {
                    this.status.innerHTML = '';
                }, 5000);
            }

            showLoading(show) {
                this.loading.style.display = show ? 'block' : 'none';
                this.convertBtn.disabled = show;
            }
        }

        let converter;
        document.addEventListener('DOMContentLoaded', () => {
            converter = new WordToJekyllConverter();
        });
    </script>
</body>
</html>
