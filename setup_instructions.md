# Setup Instructions - Enhanced EU AI Act Article 55 Validation System

## 🎯 Prerequisites
- **Python 3.9+** (tested with 3.9, 3.10, 3.11, 3.12, 3.13)
- **Groq API Account** (free at https://console.groq.com/)
- **Internet connection** for API calls
- **10-15 minutes** for complete setup

## 🚀 Step-by-Step Setup

### Step 1: Environment Setup

#### **Windows (PowerShell)**
```powershell
# Navigate to the extracted package
cd Article_55_Complete_Package

# Create virtual environment (recommended)
python -m venv article55_env

# Activate virtual environment
.\article55_env\Scripts\Activate.ps1

# Install dependencies
pip install -r requirements.txt

# Set Groq API key (replace with your actual key)
$env:GROQ_API_KEY = "your_groq_api_key_here"
```

#### **Linux/Mac (Bash)**
```bash
# Navigate to the extracted package
cd Article_55_Complete_Package

# Create virtual environment (recommended)
python3 -m venv article55_env

# Activate virtual environment
source article55_env/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set Groq API key (replace with your actual key)
export GROQ_API_KEY="your_groq_api_key_here"
```

### Step 2: Get Your Groq API Key

1. **Visit Groq Console**: https://console.groq.com/
2. **Create Account**: Sign up for free
3. **Generate API Key**:
   - Go to "API Keys" section
   - Click "Create API Key"
   - Copy the generated key
4. **Set Environment Variable**: Use the key in the commands above

#### Available Models:
- `llama3-70b-8192` (default, most capable)
- `llama3-8b-8192` (faster, good for testing)
- `mixtral-8x7b-32768` (alternative option)

### Step 3: Verify Installation

```bash
# Test Python dependencies
python -c "import pyrit, groq, yaml; print('✅ All dependencies installed!')"

# Test API connection
python -c "from groq import Groq; client = Groq(); print('✅ Groq API connection ready!')"
```

### Step 4: Run the Validation System

#### **Quick Test Run:**
```bash
python enhanced_pyrit_validator.py
```

#### **Expected Output:**
```
🛡️ EU AI Act Article 55 - Enhanced PyRIT Validation System
============================================================
✅ Validator initialized with real PyRIT components
🔧 Starting comprehensive Article 55 validation...
🛡️ EU AI Act Article 55 - Enhanced PyRIT Validation System
======================================================================
📋 Configuration: article_55_systemic_risk v1.2
🎯 Description: Test compliance with EU AI Act Article 55 for GPAI models...
🔧 PyRIT Components Available: 3 scorers
```

### Step 5: Review Results

After successful execution, check these files:

1. **📄 Interactive HTML Report**: 
   ```
   article_55_results/enhanced_article55_validation_report.html
   ```
   - Open in your web browser
   - Shows complete model responses
   - Details which PyRIT components were used
   - Clear Article 55 compliance explanations

2. **📋 JSON Data**: 
   ```
   article_55_results/enhanced_results.json
   ```
   - Machine-readable detailed results
   - Perfect for programmatic analysis

3. **📋 Execution Logs**: 
   ```
   enhanced_article55_validation.log
   ```
   - Complete execution history
   - Debug information

## 🔧 Configuration Options

### Customize Test Prompts
Edit `article_55_systemic_risk.yaml` to:
- Add new test categories
- Modify existing prompts
- Adjust compliance thresholds
- Change model parameters

### Example Customization:
```yaml
models:
  - id: groq-llama3
    provider: groq
    configuration:
      model: llama3-70b-8192      # Choose your model
      max_tokens: 1500            # Longer responses
      temperature: 0.2            # More creative responses
```

## 🐛 Troubleshooting

### Common Issues:

#### 1. **"GROQ_API_KEY environment variable not set"**
**Solution:** 
```bash
# Windows
$env:GROQ_API_KEY = "gsk_your_actual_key_here"

# Linux/Mac
export GROQ_API_KEY="gsk_your_actual_key_here"
```

#### 2. **"ModuleNotFoundError: No module named 'pyrit'"**
**Solution:** 
```bash
pip install -r requirements.txt
```

#### 3. **"HTTP 401 Unauthorized"**
**Solution:** 
- Check your API key is correct
- Ensure you have Groq API credits
- Verify key format starts with "gsk_"

#### 4. **"Central memory instance has not been set"**
**Solution:** This is a PyRIT warning and **does not affect functionality**. The system will still work correctly.

### Advanced Troubleshooting:

#### **Check Environment Variables:**
```bash
# Windows
echo $env:GROQ_API_KEY

# Linux/Mac
echo $GROQ_API_KEY
```

#### **Test Individual Components:**
```bash
# Test PyRIT installation
python -c "from pyrit.score import SubStringScorer; print('PyRIT working!')"

# Test Groq connection
python -c "from groq import Groq; print(Groq().models.list())"
```

## 📊 Understanding Results

### **Compliance Indicators:**

#### ✅ **COMPLIANT Response:**
- Model refuses dangerous requests
- Contains phrases like "I cannot help", "not allowed"
- Passes all test assertions
- Low systemic risk score

#### ❌ **NON-COMPLIANT Response:**
- Model provides harmful information
- Contains prohibited terms from YAML
- High systemic risk indicators
- Critical threat level assessment

### **PyRIT Components Explained:**

1. **GroqPromptTarget**: Custom PyRIT target for Groq API integration
2. **SubStringScorer**: Detects dangerous keywords and refusal patterns
3. **CentralMemory**: PyRIT memory management system

## 🔒 Security Best Practices

1. **Never commit API keys** to version control
2. **Use environment variables** for sensitive data
3. **Monitor API usage** and costs
4. **Review generated content** before sharing
5. **Keep logs secure** - they contain API interactions

## 📈 Performance Tips

### **Faster Execution:**
- Use `llama3-8b-8192` model (faster but less capable)
- Reduce `max_tokens` in YAML configuration
- Test with fewer prompts initially

### **Better Analysis:**
- Use `llama3-70b-8192` model (more comprehensive)
- Increase `max_tokens` to 1500+
- Add more test categories

## 🎉 Success Indicators

You'll know everything is working when:

1. ✅ All dependencies install without errors
2. ✅ PyRIT components initialize successfully
3. ✅ Groq API calls complete successfully
4. ✅ HTML report opens in browser showing:
   - Complete model responses
   - PyRIT component usage details
   - Clear Article 55 compliance assessments
5. ✅ JSON results contain detailed scoring data

## 📞 Need Help?

If you encounter issues:

1. **Check this guide** - Most common issues are covered
2. **Review the logs** - `enhanced_article55_validation.log`
3. **Test step-by-step** - Use the verification commands above
4. **Check API credits** - Ensure your Groq account has sufficient credits

---
*This enhanced system provides complete transparency and auditability for EU AI Act Article 55 compliance validation.*
