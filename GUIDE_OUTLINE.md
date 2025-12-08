# Complete Guide: Using Sora 2 API for 70% Cheaper Than OpenAI Direct

**Generate professional AI videos at 70% off OpenAI's pricing with the same quality and capabilities.**

This comprehensive guide will walk you through everything you need to know to start using the Sora 2 API through ViralWave Studio, from account setup to building production-ready automation systems.

## Quick Start (5 Minutes)

If you're ready to generate your first video right now:

1. **Sign up** at [viralwavestudio.com/sora-api](https://viralwavestudio.com/sora-api)
2. **Get your API key** from the dashboard (starts with `vws_`)
3. **Top up credits** ($5-10 minimum)
4. **Run this Python script**:

```python
import requests
import time
import os

API_KEY = os.getenv('VWS_API_KEY', 'vws_your_api_key_here')
BASE_URL = "https://api.viralwavestudio.com/api/v1"

# Generate video
response = requests.post(
    f"{BASE_URL}/generate-video",
    headers={
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    },
    json={
        "prompt": "A beautiful sunset over mountains",
        "aspect_ratio": "portrait",
        "duration": 10
    }
)

data = response.json()
generation_id = data["generationId"]
print(f"Generation started: {generation_id}")

# Poll for completion
while True:
    status_response = requests.post(
        f"{BASE_URL}/check-video-status",
        headers={
            "Authorization": f"Bearer {API_KEY}",
            "Content-Type": "application/json"
        },
        json={"generationId": generation_id}
    )
    
    status_data = status_response.json()
    
    if status_data["status"] == "completed":
        print(f"Video ready: {status_data['videoUrl']}")
        break
    elif status_data["status"] == "failed":
        print(f"Error: {status_data.get('error')}")
        break
    
    time.sleep(5)
```

**That's it!** You've generated your first video. Now read the full guide to learn about automation, best practices, and advanced use cases.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Why Choose ViralWave Studio Over OpenAI Direct?](#why-choose-viralwave-studio)
3. [Cost Comparison: The 70% Savings Breakdown](#cost-comparison)
4. [Getting Started](#getting-started)
5. [API Setup & Authentication](#api-setup)
6. [API Integration Guide](#api-integration)
7. [Code Examples](#code-examples)
8. [Use Cases & Applications](#use-cases)
9. [Best Practices & Tips](#best-practices)
10. [Troubleshooting & Support](#troubleshooting)
11. [FAQ](#faq)
12. [Conclusion](#conclusion)

---

## 1. Introduction

### What is Sora 2 API?

Sora 2 is OpenAI's revolutionary text-to-video generation model that represents a significant leap forward in AI-powered video creation. Launched in September 2024 and made available via API in October 2024, Sora 2 enables developers and creators to generate high-quality videos from simple text descriptions.

**Key Capabilities:**

- **Physics-Accurate Motion**: Unlike previous video generation models, Sora 2 understands real-world physics. It can generate complex scenes like Olympic gymnastics routines, paddleboard backflips, and triple axels with realistic inertia and motion.

- **Synchronized Audio**: One of Sora 2's standout features is its ability to generate dialogue, sound effects, and ambient audio in a single pass, eliminating the need for separate voice-over work or audio post-production.

- **Cameo Inserts**: Users can record themselves once and insert their likeness into any generated scene with granular authorization controls, perfect for personalized content creation.

- **Extended Duration**: Sora 2 can generate videos up to 20 seconds in length (via API, up to 12 seconds), allowing for more complex narratives and storytelling.

- **Multiple Aspect Ratios**: Support for both portrait and landscape formats, making it suitable for various platforms from TikTok to YouTube.

The API was officially released on October 6, 2024, at OpenAI's DevDay, making it accessible to developers worldwide. However, the cost of using OpenAI's API directly can be prohibitive for many developers and businesses.

### The Cost Problem

OpenAI's direct pricing for the Sora 2 API follows a per-second billing model:

- **Standard Model (sora-2)**: $0.10 per second
  - A 10-second video costs **$1.00**
  - A 15-second video costs **$1.50**

- **Pro Model (sora-2-pro)**: Up to $0.50 per second
  - A 10-second video costs **$5.00**
  - A 15-second video costs **$7.50**

**Why This Becomes Expensive:**

For developers and businesses generating videos at scale, these costs quickly add up:

- A content creator producing 50 videos per month would spend **$50-250** (depending on duration and model)
- A marketing agency creating 200 videos monthly faces costs of **$200-1,000**
- An enterprise application generating 1,000 videos per month could spend **$1,000-5,000**

These costs can make AI video generation unfeasible for startups, small businesses, and individual creators who want to leverage this powerful technology.

### The Solution: ViralWave Studio

ViralWave Studio provides access to the exact same Sora 2 API technology at a fraction of the cost. By acting as a reseller with optimized infrastructure and bulk pricing, ViralWave Studio can offer the same quality and capabilities at **70-80% lower prices**.

**Key Benefits:**

- **Same Technology**: Uses the identical OpenAI Sora 2 API, ensuring no compromise on quality
- **Massive Savings**: Flat rate of $0.30 per video (regardless of 10s or 15s duration)
- **No Watermarks**: All videos are generated watermark-free and ready for commercial use
- **Pay-As-You-Go**: No subscriptions, no monthly commitments - only pay for what you use
- **Developer-Friendly**: Simple REST API that integrates in minutes

### Who This Guide Is For

This comprehensive guide is designed for:

- **Developers** looking to integrate AI video generation into their applications
- **Content Creators** wanting to automate video production at scale
- **Marketing Teams** needing cost-effective video content for campaigns
- **Businesses** exploring AI video generation for their products or services
- **Entrepreneurs** building video-based applications or services
- **Anyone** interested in leveraging Sora 2's capabilities without the premium price tag

Whether you're a solo developer working on a side project or a team building a production application, this guide will walk you through everything you need to know to get started with cost-effective Sora 2 video generation.

---

## 2. Why Choose ViralWave Studio Over OpenAI Direct?

### Key Advantages

#### Massive Cost Savings: 70%+ Average Savings

The most compelling reason to choose ViralWave Studio is the significant cost reduction. With a flat rate of $0.30 per video (regardless of whether it's 10 or 15 seconds), you save:

- **70%** on 10-second videos ($1.00 → $0.30)
- **80%** on 15-second videos ($1.50 → $0.30)
- **94%** if you were using the Pro model ($5.00 → $0.30 for 10s)

For businesses generating videos at scale, these savings translate to thousands of dollars per month that can be reinvested in other areas of your business.

#### Same Technology: Powered by the Exact Same OpenAI Sora 2 API

There's no compromise on quality or capabilities. ViralWave Studio uses the identical OpenAI Sora 2 API, meaning:

- Same video quality and generation capabilities
- Same physics-accurate motion and synchronized audio
- Same aspect ratio and duration options
- Identical output format and file quality

You get the exact same results as using OpenAI directly, just at a fraction of the cost.

#### No Watermarks: Professional, Commercial-Ready Videos

All videos generated through ViralWave Studio are completely watermark-free and ready for immediate commercial use. Whether you're creating content for social media, marketing campaigns, or client work, your videos will have a professional, polished appearance.

#### Pay-As-You-Go: No Subscriptions or Monthly Commitments

Unlike many SaaS services that require monthly subscriptions, ViralWave Studio operates on a simple credit-based system:

- Top up credits as needed
- No monthly fees or minimum commitments
- Credits never expire (subject to terms)
- Only pay for videos you actually generate

This flexibility is perfect for businesses with variable video generation needs or those just getting started.

#### Developer-Friendly: Simple REST API with Comprehensive Documentation

The API is designed with developers in mind:

- **Simple REST API**: Standard HTTP requests, easy to integrate
- **Clear Documentation**: Comprehensive guides and code examples
- **Multiple Language Examples**: Python, JavaScript, PHP, cURL, and more
- **Straightforward Authentication**: Simple Bearer token authentication
- **Predictable Responses**: Consistent JSON response format

You can have the API integrated into your application in minutes, not hours or days.

#### Reliable Infrastructure: 99.9% Uptime SLA

ViralWave Studio maintains enterprise-grade infrastructure with:

- 99.9% uptime guarantee
- Redundant systems and failover capabilities
- Global CDN for fast video delivery
- Automatic scaling to handle traffic spikes

You can rely on the service for production applications without worrying about downtime.

#### Fast Generation: 2-5 Minute Average Generation Times

While video generation is inherently time-consuming, ViralWave Studio's optimized infrastructure ensures:

- Average generation time of 2-5 minutes
- Efficient queue management
- Priority processing for high-volume users
- Real-time status updates

#### Commercial License: Included for All Generated Videos

Every video you generate comes with a full commercial license, allowing you to:

- Use videos in client work
- Sell videos as products or services
- Include in commercial applications
- Monetize content on platforms like YouTube, TikTok, etc.

No additional licensing fees or restrictions.

#### 24/7 Support: Dedicated Support Team Available Around the Clock

When you need help, support is always available:

- 24/7 email and chat support
- Quick response times
- Technical assistance with integration
- Troubleshooting help

### When to Use ViralWave Studio vs. OpenAI Direct

**Choose ViralWave Studio when:**

- ✅ **Cost is a primary concern**: You need to generate videos at scale without breaking the budget
- ✅ **High-volume generation**: You're creating dozens or hundreds of videos monthly
- ✅ **Startup or small business**: Budget constraints make cost-effective solutions essential
- ✅ **Testing and prototyping**: You want to experiment without high costs
- ✅ **Flexible pricing needed**: You prefer pay-as-you-go over subscriptions
- ✅ **Commercial use**: You need watermark-free videos for client work
- ✅ **Multiple projects**: You're working on several projects with varying video needs

**Consider OpenAI Direct when:**

- ⚠️ **Enterprise contracts**: You need direct billing relationships with OpenAI
- ⚠️ **Specific compliance requirements**: Your organization requires direct vendor relationships
- ⚠️ **Custom model access**: You need access to experimental or custom models
- ⚠️ **Volume discounts**: You generate enough volume to negotiate better direct pricing

For 95% of use cases, ViralWave Studio provides the best balance of cost, quality, and convenience.

---

## 3. Cost Comparison: The 70% Savings Breakdown

Understanding the true cost difference between OpenAI Direct and ViralWave Studio is crucial for making an informed decision. Let's break down the pricing and see how the savings add up in real-world scenarios.

### OpenAI Direct Pricing

OpenAI uses a per-second billing model for the Sora 2 API:

**Standard Model (sora-2)**:
- **$0.10 per second**
  - 10-second video: **$1.00**
  - 15-second video: **$1.50**

**Pro Model (sora-2-pro)**:
- **Up to $0.50 per second**
  - 10-second video: **$5.00**
  - 15-second video: **$7.50**

**Important Notes:**
- Pricing is per second, so longer videos cost proportionally more
- Pro model offers higher quality but at 5x the cost
- No volume discounts for most users
- Billing is per API call, regardless of success or failure

### ViralWave Studio Pricing

ViralWave Studio uses a simple, flat-rate pricing model:

**Flat Rate**: **$0.30 per video**
- 10-second video: **$0.30** (70% savings vs. OpenAI)
- 15-second video: **$0.30** (80% savings vs. OpenAI)

**Key Advantages:**
- Same price regardless of video duration (10s or 15s)
- No per-second billing complexity
- Predictable costs for budgeting
- No hidden fees or additional charges

### Side-by-Side Comparison

| Video Duration | OpenAI Direct (Standard) | ViralWave Studio | Savings | Savings % |
|---------------|-------------------------|------------------|---------|-----------|
| 10 seconds    | $1.00                   | $0.30            | $0.70   | 70%       |
| 15 seconds    | $1.50                   | $0.30            | $1.20   | 80%       |

| Video Duration | OpenAI Direct (Pro) | ViralWave Studio | Savings | Savings % |
|---------------|---------------------|------------------|---------|-----------|
| 10 seconds    | $5.00               | $0.30            | $4.70   | 94%       |
| 15 seconds    | $7.50               | $0.30            | $7.20   | 96%       |

### Real-World Cost Scenarios

Let's examine how these pricing differences impact different types of users:

#### Scenario 1: Small Content Creator

**Monthly Usage**: 50 videos (mix of 10s and 15s videos)

**Cost Breakdown:**
- **OpenAI Direct Cost**: 
  - 25 × 10s videos: 25 × $1.00 = $25.00
  - 25 × 15s videos: 25 × $1.50 = $37.50
  - **Total: $62.50/month**

- **ViralWave Studio Cost**:
  - 50 videos × $0.30 = **$15.00/month**

- **Savings**: $47.50/month (76% reduction)
- **Annual Savings**: $570.00

**Impact**: A content creator can produce the same volume of content while saving nearly $50 per month, which can be reinvested in other tools, marketing, or equipment.

#### Scenario 2: Marketing Agency

**Monthly Usage**: 200 videos for client campaigns

**Cost Breakdown:**
- **OpenAI Direct Cost**:
  - Average of 12.5 seconds per video
  - 200 videos × $1.25 average = **$250.00/month**

- **ViralWave Studio Cost**:
  - 200 videos × $0.30 = **$60.00/month**

- **Savings**: $190.00/month (76% reduction)
- **Annual Savings**: $2,280.00

**Impact**: For a marketing agency, these savings can mean the difference between profitable and unprofitable campaigns. The $190/month saved can cover additional services or increase profit margins.

#### Scenario 3: Enterprise Application

**Monthly Usage**: 1,000 videos for a SaaS platform

**Cost Breakdown:**
- **OpenAI Direct Cost**:
  - 1,000 videos × $1.25 average = **$1,250.00/month**

- **ViralWave Studio Cost**:
  - 1,000 videos × $0.30 = **$300.00/month**

- **Savings**: $950.00/month (76% reduction)
- **Annual Savings**: $11,400.00

**Impact**: For enterprise applications, these savings are substantial. The $11,400 annual savings could fund additional development, hire a part-time developer, or significantly improve the product's unit economics.

#### Scenario 4: Startup MVP

**Monthly Usage**: 500 videos during development and testing phase

**Cost Breakdown:**
- **OpenAI Direct Cost**: 500 × $1.25 = **$625.00/month**
- **ViralWave Studio Cost**: 500 × $0.30 = **$150.00/month**
- **Savings**: $475.00/month (76% reduction)

**Impact**: For cash-strapped startups, saving $475/month during the MVP phase can extend runway significantly, allowing more time to validate the product before raising additional funding.

### Cost Calculator Formula

You can calculate your potential savings using this simple formula:

```
Monthly Savings = (Number of Videos × OpenAI Cost per Video) - (Number of Videos × $0.30)
```

**Example Calculation:**
- 100 videos/month
- Average OpenAI cost: $1.25/video
- Calculation: (100 × $1.25) - (100 × $0.30) = $125 - $30 = **$95/month savings**

### ROI Calculations for Businesses

**Return on Investment Analysis:**

For businesses, the ROI of switching to ViralWave Studio is immediate and measurable:

1. **Break-Even Point**: Immediate (no setup costs)
2. **Monthly Savings**: 70-80% reduction in video generation costs
3. **Annual Impact**: Savings scale linearly with usage
4. **Opportunity Cost**: Money saved can be reinvested in:
   - Product development
   - Marketing and advertising
   - Hiring additional team members
   - Infrastructure improvements

**Example Business Case:**

A SaaS company generating 2,000 videos/month:
- **Current Cost (OpenAI)**: $2,500/month = $30,000/year
- **New Cost (ViralWave)**: $600/month = $7,200/year
- **Annual Savings**: $22,800
- **ROI**: Infinite (no additional investment required)
- **Time to Value**: Immediate

### Understanding the True Cost

When evaluating costs, consider:

1. **Per-Video Cost**: ViralWave Studio's flat rate makes budgeting easier
2. **Failed Generations**: Both services charge for failed attempts, but ViralWave's lower cost means less financial impact
3. **Testing Costs**: Lower costs enable more experimentation and iteration
4. **Scaling Costs**: As you scale, savings compound significantly

### Making the Switch

The cost savings alone make ViralWave Studio an attractive option, but when combined with identical quality, no watermarks, and flexible pricing, it becomes the clear choice for most developers and businesses.

---

## 4. Getting Started

Getting started with ViralWave Studio's Sora 2 API is straightforward. This section will walk you through the entire setup process from account creation to generating your first video.

### Prerequisites

Before you begin, make sure you have:

1. **Basic Understanding of REST APIs**: Familiarity with HTTP requests (GET, POST), JSON, and API authentication
2. **Programming Language Knowledge**: Experience with at least one programming language (Python, JavaScript, PHP, Node.js, etc.)
3. **Development Environment**: A code editor and the ability to run code locally or on a server
4. **Internet Connection**: Stable connection for API calls
5. **Payment Method**: Credit card or other accepted payment method for topping up credits

**No Prior Experience Required**: If you're new to APIs, don't worry! This guide includes step-by-step instructions and code examples that you can copy and modify.

### Step 1: Sign Up for API Access

#### Navigate to ViralWave Studio

1. Visit the ViralWave Studio website: [https://viralwavestudio.com/sora-api](https://viralwavestudio.com/sora-api)
2. Click the **"Get API Access"** or **"Login"** button (usually in the top-right corner)
3. You'll be redirected to the API portal/login page

#### Account Creation Process

1. **Choose Sign Up**: If you don't have an account, click "Sign Up" or "Create Account"
2. **Enter Your Information**:
   - Email address (use a professional email for business accounts)
   - Password (choose a strong password)
   - Confirm password
3. **Accept Terms**: Read and accept the terms of service and privacy policy
4. **Verify Email**: Check your email inbox for a verification link
5. **Click Verification Link**: This confirms your email address and activates your account

**Pro Tip**: Use a password manager to generate and store a strong, unique password.

#### Email Verification

- Check your spam folder if you don't see the verification email
- The verification link typically expires after 24 hours
- If the link expires, you can request a new verification email from the login page

### Step 2: Get Your API Key

Once your account is verified and you're logged in:

#### Finding Your API Key

1. **Navigate to API Settings**: Look for "API Keys", "Settings", or "Developer" in the dashboard menu
2. **Locate Your API Key**: Your API key will be displayed (it starts with `vws_`)
3. **Copy the Key**: Click the copy button or manually select and copy the entire key

**Important**: Your API key is like a password - keep it secure and never share it publicly!

#### API Key Format

ViralWave Studio API keys follow this format:
```
vws_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

The key is approximately 40-50 characters long and starts with `vws_`.

#### Security Best Practices

**DO:**
- ✅ Store API keys in environment variables, not in code
- ✅ Use different keys for development and production
- ✅ Rotate keys periodically (every 90 days is recommended)
- ✅ Restrict key access to only necessary team members
- ✅ Monitor API key usage for suspicious activity

**DON'T:**
- ❌ Commit API keys to version control (Git, GitHub, etc.)
- ❌ Share API keys in public forums, chat rooms, or social media
- ❌ Hard-code keys in client-side code (JavaScript in browsers)
- ❌ Use the same key across multiple projects without good reason

#### Regenerating API Keys

If your API key is compromised or you need to rotate it:

1. Go to API Settings in your dashboard
2. Find the "Regenerate Key" or "Rotate Key" option
3. Confirm the regeneration (this will invalidate the old key immediately)
4. Update all applications using the old key with the new key

**Warning**: Regenerating a key will immediately invalidate the old key. Make sure you update all applications before regenerating, or you'll experience API errors.

### Step 3: Top Up Credits

ViralWave Studio uses a pay-as-you-go credit system. You purchase credits in advance and they're deducted as you generate videos.

#### Understanding the Credit System

- **1 Credit = 1 Video**: Each video generation costs 1 credit, regardless of duration (10s or 15s)
- **Credits Never Expire**: Unlike some services, your credits don't have an expiration date
- **No Monthly Minimums**: You're not required to purchase a minimum amount each month
- **Flexible Top-Ups**: Add credits whenever you need them

#### Minimum Top-Up Amounts

Check the current minimum purchase amount on the ViralWave Studio dashboard. Typically, minimum purchases range from $5-$10 to cover payment processing fees.

#### Payment Methods Accepted

ViralWave Studio typically accepts:
- Credit cards (Visa, Mastercard, American Express)
- Debit cards
- PayPal (if available)
- Bank transfers (for larger amounts, contact support)

#### How to Top Up Credits

1. **Navigate to Billing/Credits**: Find "Billing", "Credits", or "Top Up" in your dashboard
2. **Select Amount**: Choose how many credits you want to purchase
   - You can often see the cost per credit (typically $0.30 per credit)
   - Some services offer bulk discounts for larger purchases
3. **Enter Payment Information**: Provide your payment details securely
4. **Confirm Purchase**: Review your order and confirm
5. **Credits Added**: Credits are typically added to your account immediately

#### Credit Balance Management

- **Check Balance**: Your current credit balance is usually displayed in the dashboard
- **Usage History**: View a history of video generations and credit usage
- **Low Balance Alerts**: Set up email notifications when your balance gets low
- **Auto-Top-Up**: Some accounts offer automatic credit replenishment when balance falls below a threshold

**Pro Tip**: Start with a small top-up ($10-20) to test the service, then add more credits as needed once you're comfortable with the workflow.

### Step 4: Access Documentation

#### API Documentation Location

The official API documentation is available at:
- **Website**: [https://viralwavestudio.com/sora-api](https://viralwavestudio.com/sora-api)
- **API Docs**: Usually linked from the main page or in your dashboard

#### What's Available in the Documentation

- **API Endpoints**: Complete list of available endpoints
- **Request/Response Examples**: Sample requests and responses for each endpoint
- **Authentication Guide**: How to authenticate your requests
- **Rate Limits**: Information about API rate limits and quotas
- **Error Codes**: Complete list of error codes and their meanings
- **Code Examples**: Ready-to-use code snippets in multiple languages

#### Code Examples Library

The documentation typically includes examples in:
- Python
- JavaScript/Node.js
- PHP
- cURL (command line)
- And sometimes Ruby, Go, Java, and other languages

#### Support Resources

If you need help:

1. **Documentation**: Start with the official docs
2. **Support Email**: Contact support through your dashboard
3. **Live Chat**: If available, use the chat feature in your dashboard
4. **Community Forums**: Check if there's a community forum or Discord server
5. **GitHub Issues**: If the service has open-source components, check GitHub

### Quick Start Checklist

Before generating your first video, make sure you have:

- [ ] Created and verified your ViralWave Studio account
- [ ] Copied your API key (starts with `vws_`)
- [ ] Topped up at least $5-10 in credits
- [ ] Reviewed the API documentation
- [ ] Set up your development environment
- [ ] Chosen a programming language for integration

### Next Steps

Once you've completed these steps, you're ready to:
1. Set up API authentication (Section 5)
2. Make your first API call (Section 6)
3. Generate your first video (Section 7)

Let's move on to the technical setup!

---

## 5. API Setup & Authentication

This section covers the technical details of connecting to the ViralWave Studio API, including authentication, request formatting, and understanding responses.

### API Endpoint

All API requests are made to the following base URL:

```
Base URL: https://api.viralwavestudio.com/api/v1
```

**Important Notes:**
- Always use `https://` (secure connection required)
- The API version is included in the path (`/v1`)
- All endpoints are relative to this base URL

### Authentication Method

ViralWave Studio uses **Bearer token authentication**, which is a standard and secure method for API authentication.

#### How It Works

1. **API Key Format**: Your API key starts with `vws_` followed by a long string of characters
   ```
   Example: vws_abc123xyz789def456ghi012jkl345mno678pqr901stu234
   ```

2. **Include in Every Request**: You must include your API key in the `Authorization` header of every API request

3. **Bearer Token Format**: The key is prefixed with the word "Bearer" and a space

#### Authentication Header

Every API request must include this header:

```http
Authorization: Bearer vws_your_api_key_here
```

**Example in cURL:**
```bash
curl -X POST https://api.viralwavestudio.com/api/v1/generate-video \
  -H "Authorization: Bearer vws_your_api_key_here" \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Your video description"}'
```

### Request Headers

All API requests should include these headers:

```json
{
  "Authorization": "Bearer vws_your_api_key_here",
  "Content-Type": "application/json"
}
```

**Header Breakdown:**

1. **Authorization**: Required for all requests
   - Format: `Bearer {your_api_key}`
   - Must include the word "Bearer" followed by a space, then your API key

2. **Content-Type**: Required for POST requests with a body
   - Value: `application/json`
   - Tells the server you're sending JSON data

### Response Format

The API uses a consistent JSON response format for all endpoints.

#### Success Response Structure

All successful responses include a `success: true` field:

```json
{
  "success": true,
  "generationId": "task_abc123xyz",
  "status": "pending",
  "message": "Video generation started."
}
```

**Common Success Fields:**
- `success`: Always `true` for successful requests
- `generationId`: Unique identifier for the video generation job
- `status`: Current status of the generation (`pending`, `in_progress`, `completed`, `failed`)
- `videoUrl`: URL to the generated video (only present when `status` is `completed`)
- `message`: Human-readable message about the operation

#### Error Response Structure

Error responses include `success: false` and an `error` field:

```json
{
  "success": false,
  "error": "Prompt is required"
}
```

**Common Error Fields:**
- `success`: Always `false` for errors
- `error`: Descriptive error message explaining what went wrong
- Additional fields may be present depending on the error type (e.g., `creditsRemaining`, `rateLimitInfo`)

### HTTP Status Codes

The API uses standard HTTP status codes to indicate request results:

| Status Code | Meaning | Description |
|------------|---------|-------------|
| 200 | OK | Request successful |
| 400 | Bad Request | Invalid request parameters or missing required fields |
| 401 | Unauthorized | Missing or invalid API key |
| 402 | Payment Required | Insufficient credits in account |
| 413 | Payload Too Large | Request body exceeds 10KB limit |
| 429 | Too Many Requests | Rate limit exceeded |
| 500 | Internal Server Error | Server-side error (rare) |

### Rate Limits

To ensure fair usage and system stability, ViralWave Studio implements rate limits on API requests.

#### Per API Key Limits

- **60 requests per minute** (1 request per second average)
- **3,600 requests per hour**

These limits are generous enough for most applications while preventing abuse.

#### Per IP Address Limits

- **100 requests per minute per IP address**
- **5,000 requests per hour per IP address**

This provides an additional layer of protection against abuse from single IP addresses.

#### Rate Limit Headers

Every API response includes rate limit information in headers:

- `X-RateLimit-Limit`: Maximum requests allowed in the current window
- `X-RateLimit-Remaining`: Number of requests remaining in the current window
- `X-RateLimit-Reset`: Unix timestamp when the rate limit resets
- `Retry-After`: Seconds to wait before retrying (only present on 429 responses)

**Example Headers:**
```http
X-RateLimit-Limit: 60
X-RateLimit-Remaining: 45
X-RateLimit-Reset: 1703123456
```

#### Handling Rate Limits

When you receive a `429 Too Many Requests` response:

1. Check the `Retry-After` header for the recommended wait time
2. Implement exponential backoff in your retry logic
3. Consider implementing request queuing for high-volume applications

**Example Rate Limit Handling:**
```python
import time
import requests

def make_request_with_retry(url, headers, data, max_retries=3):
    for attempt in range(max_retries):
        response = requests.post(url, headers=headers, json=data)
        
        if response.status_code == 429:
            retry_after = int(response.headers.get('Retry-After', 60))
            print(f"Rate limited. Waiting {retry_after} seconds...")
            time.sleep(retry_after)
            continue
        
        return response
    
    raise Exception("Max retries exceeded")
```

### Request Size Limits

The API enforces limits on request size to ensure optimal performance.

#### Prompt Length Limit

- **Maximum: 1,000 characters**
- The `prompt` parameter must not exceed 1,000 characters
- This limit ensures optimal video generation quality

**Tip**: If your prompt is longer than 1,000 characters, consider:
- Summarizing the key points
- Breaking it into multiple videos
- Removing unnecessary words

#### Request Body Size Limit

- **Maximum: 10KB**
- The entire JSON request body must not exceed 10KB
- This includes all fields, not just the prompt

**Note**: For most use cases, this limit is more than sufficient. A typical request is only a few hundred bytes.

### Security Best Practices

#### Protecting Your API Key

1. **Never Commit to Version Control**
   - Add `.env` to your `.gitignore` file
   - Use environment variables or secure secret management

2. **Use Environment Variables**
   ```python
   import os
   API_KEY = os.getenv('VWS_API_KEY')
   ```

3. **Rotate Keys Regularly**
   - Regenerate your API key every 90 days
   - Update all applications before invalidating the old key

4. **Monitor Usage**
   - Regularly check your API usage in the dashboard
   - Set up alerts for unusual activity

5. **Use Different Keys for Different Environments**
   - Separate keys for development, staging, and production
   - This allows you to revoke access to one environment without affecting others

### Testing Your Setup

Before integrating into your application, test your API connection:

**Simple Test Script:**
```python
import requests
import os

API_KEY = os.getenv('VWS_API_KEY', 'vws_your_api_key_here')
BASE_URL = "https://api.viralwavestudio.com/api/v1"

# Test authentication
headers = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json"
}

# Make a simple request to verify authentication
response = requests.post(
    f"{BASE_URL}/generate-video",
    headers=headers,
    json={"prompt": "Test video"}
)

if response.status_code == 200:
    print("✅ Authentication successful!")
    print(response.json())
elif response.status_code == 401:
    print("❌ Authentication failed. Check your API key.")
else:
    print(f"⚠️ Unexpected response: {response.status_code}")
    print(response.json())
```

Once your authentication is working, you're ready to start generating videos!

---

## 6. API Integration Guide

### Core Endpoints

#### Generate Video
- **Endpoint**: `POST /v1/generate-video`
- **Purpose**: Create a new video generation request
- **Request Body**:
  ```json
  {
    "prompt": "A beautiful sunset over the ocean with waves crashing",
    "aspect_ratio": "portrait",
    "duration": 10
  }
  ```
- **Parameters**:
  - `prompt` (required): Text description of the video (max 1,000 characters)
  - `aspect_ratio` (optional): "portrait" or "landscape" (default: "portrait")
  - `duration` (optional): 10 or 15 seconds (default: 10)
- **Success Response (200)**:
  ```json
  {
    "success": true,
    "generationId": "task_abc123xyz",
    "status": "pending",
    "message": "Video generation started. Use the check-status endpoint to poll for completion."
  }
  ```
- **Error Responses**:
  - `400`: Bad Request (missing prompt, invalid parameters)
  - `401`: Unauthorized (missing or invalid API key)
  - `402`: Payment Required (insufficient credits)
  - `413`: Payload Too Large (request body > 10KB)
  - `429`: Too Many Requests (rate limit exceeded)

#### Check Video Status
- **Endpoint**: `POST /v1/check-video-status`
- **Purpose**: Check the status of a video generation job
- **Request Body**:
  ```json
  {
    "generationId": "task_abc123xyz"
  }
  ```
- **Status Values**:
  - `pending`: Video generation is queued
  - `in_progress`: Video is currently being generated
  - `completed`: Video generation finished successfully (includes `videoUrl`)
  - `failed`: Video generation failed (includes `error` message)
- **Success Response Examples**:
  - **Pending/In Progress**:
    ```json
    {
      "success": true,
      "status": "pending",
      "videoUrl": null
    }
    ```
  - **Completed**:
    ```json
    {
      "success": true,
      "status": "completed",
      "videoUrl": "https://cdn.example.com/video.mp4",
      "isCompleted": true
    }
    ```
  - **Failed**:
    ```json
    {
      "success": true,
      "status": "failed",
      "videoUrl": null,
      "error": "Generation failed: Invalid prompt content"
    }
    ```

### Polling Strategy

Video generation is an asynchronous process. After initiating a generation request, you need to poll the status endpoint until the video is ready.

#### Recommended Polling Approach

1. **Initial Request**: Submit video generation request, receive `generationId`
2. **Poll Interval**: Check status every 5 seconds
3. **Timeout**: Set a maximum wait time (e.g., 10 minutes) to prevent infinite loops
4. **Status Handling**:
   - `pending` or `in_progress`: Continue polling
   - `completed`: Return the `videoUrl`
   - `failed`: Raise an error with the failure message

#### Best Practices

- **Don't Poll Too Frequently**: 5-second intervals are optimal. Polling more frequently wastes API calls and may hit rate limits.
- **Implement Timeouts**: Always set a maximum wait time to prevent hanging processes.
- **Handle Rate Limits**: If you receive a 429 response while polling, respect the `Retry-After` header.
- **Log Progress**: Log status updates for debugging and monitoring.

#### Example Polling Implementation

```python
import time
from datetime import datetime, timedelta

def poll_video_status(generation_id, max_wait_minutes=10, poll_interval=5):
    """
    Poll video generation status until complete or timeout.
    
    Args:
        generation_id: The generation ID from the initial request
        max_wait_minutes: Maximum time to wait (default: 10 minutes)
        poll_interval: Seconds between status checks (default: 5)
    
    Returns:
        video_url: URL of the completed video
    
    Raises:
        TimeoutError: If video doesn't complete within max_wait_minutes
        Exception: If video generation fails
    """
    start_time = datetime.now()
    timeout = timedelta(minutes=max_wait_minutes)
    
    print(f"Polling for video generation: {generation_id}")
    
    while True:
        # Check for timeout
        if datetime.now() - start_time > timeout:
            raise TimeoutError(f"Video generation timed out after {max_wait_minutes} minutes")
        
        # Check status
        status_data = check_status(generation_id)
        current_status = status_data.get("status")
        
        print(f"Status: {current_status} (elapsed: {datetime.now() - start_time})")
        
        if current_status == "completed":
            video_url = status_data.get("videoUrl")
            print(f"✅ Video ready: {video_url}")
            return video_url
        
        elif current_status == "failed":
            error = status_data.get("error", "Video generation failed")
            raise Exception(f"Video generation failed: {error}")
        
        # Wait before next poll
        time.sleep(poll_interval)
```

### Error Handling

Always implement proper error handling for production applications:

```python
def generate_video_safely(prompt, aspect_ratio="portrait", duration=10):
    """Generate video with comprehensive error handling"""
    try:
        generation_id = generate_video(prompt, aspect_ratio, duration)
        video_url = poll_video_status(generation_id)
        return {"success": True, "video_url": video_url}
    
    except requests.exceptions.HTTPError as e:
        if e.response.status_code == 401:
            return {"success": False, "error": "Authentication failed. Check your API key."}
        elif e.response.status_code == 402:
            return {"success": False, "error": "Insufficient credits. Please top up your account."}
        elif e.response.status_code == 429:
            return {"success": False, "error": "Rate limit exceeded. Please slow down."}
        else:
            return {"success": False, "error": f"HTTP error: {e.response.status_code}"}
    
    except TimeoutError as e:
        return {"success": False, "error": str(e)}
    
    except Exception as e:
        return {"success": False, "error": f"Unexpected error: {str(e)}"}
```

---

## 7. Code Examples

### Python Example
```python
import requests
import time

API_KEY = "vws_your_api_key_here"
BASE_URL = "https://api.viralwavestudio.com/api/v1"

def generate_video(prompt, aspect_ratio="portrait", duration=10):
    """Generate a video using Sora 2 API"""
    url = f"{BASE_URL}/generate-video"
    headers = {
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    }
    data = {
        "prompt": prompt,
        "aspect_ratio": aspect_ratio,
        "duration": duration
    }
    
    response = requests.post(url, json=data, headers=headers)
    response.raise_for_status()
    
    result = response.json()
    if not result.get("success"):
        raise Exception(result.get("error", "Video generation failed"))
    
    return result["generationId"]

def check_status(generation_id):
    """Check the status of a video generation"""
    url = f"{BASE_URL}/check-video-status"
    headers = {
        "Authorization": f"Bearer {API_KEY}",
        "Content-Type": "application/json"
    }
    data = {"generationId": generation_id}
    
    response = requests.post(url, json=data, headers=headers)
    response.raise_for_status()
    
    return response.json()

def wait_for_video(generation_id, max_wait_time=600):
    """Poll video generation status until complete"""
    start_time = time.time()
    
    while True:
        if time.time() - start_time > max_wait_time:
            raise Exception("Video generation timeout")
        
        status_data = check_status(generation_id)
        
        if status_data["status"] == "completed":
            return status_data["videoUrl"]
        elif status_data["status"] == "failed":
            error = status_data.get("error", "Video generation failed")
            raise Exception(f"Video generation failed: {error}")
        
        time.sleep(5)  # Wait 5 seconds before checking again

# Usage
if __name__ == "__main__":
    try:
        generation_id = generate_video(
            "A beautiful sunset over mountains with birds flying",
            aspect_ratio="portrait",
            duration=10
        )
        print(f"Generation started: {generation_id}")
        
        video_url = wait_for_video(generation_id)
        print(f"Video ready at: {video_url}")
    except Exception as e:
        print(f"Error: {e}")
```

### JavaScript/Node.js Example
```javascript
const API_KEY = 'vws_your_api_key_here';
const BASE_URL = 'https://api.viralwavestudio.com/api/v1';

async function generateVideo(prompt, aspectRatio = 'portrait', duration = 10) {
  const response = await fetch(`${BASE_URL}/generate-video`, {
    method: 'POST',
    headers: {
      'Authorization': `Bearer ${API_KEY}`,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      prompt: prompt,
      aspect_ratio: aspectRatio,
      duration: duration
    })
  });

  if (!response.ok) {
    const error = await response.json();
    throw new Error(error.error || `API error: ${response.statusText}`);
  }

  const data = await response.json();
  if (!data.success) {
    throw new Error(data.error || 'Video generation failed');
  }

  return data.generationId;
}

async function checkStatus(generationId) {
  const response = await fetch(`${BASE_URL}/check-video-status`, {
    method: 'POST',
    headers: {
      'Authorization': `Bearer ${API_KEY}`,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({ generationId })
  });

  if (!response.ok) {
    throw new Error(`API error: ${response.statusText}`);
  }

  return await response.json();
}

async function waitForVideo(generationId, maxWaitTime = 600000) {
  const startTime = Date.now();

  while (true) {
    if (Date.now() - startTime > maxWaitTime) {
      throw new Error('Video generation timeout');
    }

    const statusData = await checkStatus(generationId);

    if (statusData.status === 'completed') {
      return statusData.videoUrl;
    } else if (statusData.status === 'failed') {
      throw new Error(statusData.error || 'Video generation failed');
    }

    // Wait 5 seconds before checking again
    await new Promise(resolve => setTimeout(resolve, 5000));
  }
}

// Usage with error handling
async function main() {
  try {
    const generationId = await generateVideo(
      'A beautiful sunset over mountains with birds flying',
      'portrait',
      10
    );
    console.log(`Generation started: ${generationId}`);

    const videoUrl = await waitForVideo(generationId);
    console.log(`Video ready at: ${videoUrl}`);
  } catch (error) {
    console.error('Error:', error.message);
  }
}

main();
```

### PHP Example
```php
<?php

$apiKey = 'YOUR_API_KEY';
$baseUrl = 'https://api.viralwavestudio.com/api/v1';

function generateVideo($prompt, $duration = 10) {
    global $apiKey, $baseUrl;
    
    $ch = curl_init($baseUrl . '/generate-video');
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_POST, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Authorization: Bearer ' . $apiKey,
        'Content-Type: application/json'
    ]);
    curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode([
        'prompt' => $prompt,
        'duration' => $duration
    ]));
    
    $response = curl_exec($ch);
    $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
    curl_close($ch);
    
    if ($httpCode !== 200) {
        throw new Exception('API error: ' . $response);
    }
    
    $jobData = json_decode($response, true);
    return pollVideoStatus($jobData['jobId']);
}

function pollVideoStatus($jobId) {
    global $apiKey, $baseUrl;
    
    while (true) {
        $ch = curl_init($baseUrl . '/video-status/' . $jobId);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        curl_setopt($ch, CURLOPT_HTTPHEADER, [
            'Authorization: Bearer ' . $apiKey
        ]);
        
        $response = curl_exec($ch);
        $httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
        curl_close($ch);
        
        $statusData = json_decode($response, true);
        
        if ($statusData['status'] === 'completed') {
            return $statusData['videoUrl'];
        } else if ($statusData['status'] === 'failed') {
            throw new Exception('Video generation failed: ' . $statusData['error']);
        }
        
        sleep(5);
    }
}

// Usage
try {
    $videoUrl = generateVideo('A beautiful sunset over mountains with birds flying', 10);
    echo "Video ready at: " . $videoUrl . "\n";
} catch (Exception $e) {
    echo "Error: " . $e->getMessage() . "\n";
}
?>
```

### cURL Example
```bash
#!/bin/bash

API_KEY="YOUR_API_KEY"
BASE_URL="https://api.viralwavestudio.com/api/v1"

# Generate video
RESPONSE=$(curl -X POST "$BASE_URL/generate-video" \
  -H "Authorization: Bearer $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "prompt": "A beautiful sunset over mountains with birds flying",
    "duration": 10
  }')

JOB_ID=$(echo $RESPONSE | jq -r '.jobId')

# Poll for status
while true; do
  STATUS_RESPONSE=$(curl -s "$BASE_URL/video-status/$JOB_ID" \
    -H "Authorization: Bearer $API_KEY")
  
  STATUS=$(echo $STATUS_RESPONSE | jq -r '.status')
  
  if [ "$STATUS" == "completed" ]; then
    VIDEO_URL=$(echo $STATUS_RESPONSE | jq -r '.videoUrl')
    echo "Video ready at: $VIDEO_URL"
    break
  elif [ "$STATUS" == "failed" ]; then
    ERROR=$(echo $STATUS_RESPONSE | jq -r '.error')
    echo "Error: $ERROR"
    exit 1
  fi
  
  sleep 5
done
```

---

## 8. Use Cases & Applications

### Marketing & Advertising
- Social media campaign videos
- Product demonstration videos
- Brand storytelling content
- Ad creatives at scale

### Content Creation
- YouTube intros and outros
- TikTok content generation
- Instagram story highlights
- Video thumbnails and previews

### E-Learning & Training
- Educational course content
- Training material videos
- Explainer videos
- Interactive learning content

### Business Applications
- Internal communications
- Product showcases
- Customer testimonials
- Event promotions

### Development & Prototyping
- MVP video features
- Concept validation
- A/B testing video content
- Rapid iteration

---

## 8.5. Text-to-Video Automation Use Cases

### Social Media Automation

#### Instagram/TikTok Content Automation
**Use Case**: Automatically generate daily video content from text posts
**Integration Points**:
- Instagram API / TikTok API
- Content management systems (CMS)
- Social media scheduling tools (Buffer, Hootsuite)

**Setup Example**:
```python
# Automated Instagram video generator
import requests
from instagrapi import Client

def generate_instagram_video(text_post):
    """Convert text post to video and upload to Instagram"""
    # Generate video from text
    generation_id = generate_video(
        prompt=text_post,
        aspect_ratio="portrait",  # Instagram/TikTok format
        duration=15
    )
    video_url = wait_for_video(generation_id)
    
    # Download video
    video_file = download_video(video_url)
    
    # Upload to Instagram
    ig = Client()
    ig.login(username, password)
    ig.clip_upload(video_file, caption=text_post)
    
    return video_url
```

#### YouTube Shorts Automation
**Use Case**: Convert blog posts or articles into YouTube Shorts
**Integration Points**:
- YouTube Data API v3
- WordPress/RSS feeds
- Content extraction tools

**Setup Example**:
```python
# Blog to YouTube Shorts converter
import feedparser
from googleapiclient.discovery import build

def convert_blog_to_shorts():
    """Monitor RSS feed and create YouTube Shorts from new posts"""
    feed = feedparser.parse("https://yourblog.com/feed")
    
    for entry in feed.entries:
        # Extract key points from blog post
        summary = extract_summary(entry.content[0].value)
        
        # Generate video
        prompt = f"Animated explainer video about: {summary}"
        generation_id = generate_video(
            prompt=prompt,
            aspect_ratio="portrait",
            duration=15
        )
        video_url = wait_for_video(generation_id)
        
        # Upload to YouTube
        youtube = build('youtube', 'v3', credentials=credentials)
        upload_video_to_youtube(youtube, video_url, entry.title)
```

### E-Commerce Automation

#### Product Video Generation
**Use Case**: Automatically create product showcase videos from product descriptions
**Integration Points**:
- Shopify API
- WooCommerce
- Amazon Seller Central
- E-commerce platforms

**Setup Example**:
```python
# Shopify product video generator
import shopify

def generate_product_videos():
    """Generate videos for all products without videos"""
    products = shopify.Product.find()
    
    for product in products:
        if not has_video(product):
            # Create video from product description
            prompt = f"Product showcase video: {product.title}. {product.body_html}"
            generation_id = generate_video(
                prompt=prompt,
                aspect_ratio="landscape",
                duration=15
            )
            video_url = wait_for_video(generation_id)
            
            # Add video to product
            add_video_to_product(product.id, video_url)
```

#### Email Marketing Automation
**Use Case**: Generate video content for email campaigns
**Integration Points**:
- Mailchimp API
- SendGrid
- Klaviyo
- Email marketing platforms

**Setup Example**:
```python
# Email campaign video generator
import mailchimp_marketing as MailchimpMarketing

def create_email_video_campaign(campaign_text):
    """Generate video for email campaign"""
    generation_id = generate_video(
        prompt=campaign_text,
        aspect_ratio="landscape",
        duration=10
    )
    video_url = wait_for_video(generation_id)
    
    # Add to Mailchimp campaign
    client = MailchimpMarketing.Client()
    client.campaigns.set_content(campaign_id, {
        'html': f'<video src="{video_url}" controls></video>'
    })
```

### Content Management Automation

#### CMS Integration (WordPress, Drupal, etc.)
**Use Case**: Auto-generate featured videos for blog posts
**Integration Points**:
- WordPress REST API
- Drupal API
- Headless CMS (Contentful, Strapi)

**Setup Example**:
```python
# WordPress auto-video generator
import requests

def wordpress_auto_video():
    """Generate featured video when new post is published"""
    wp_url = "https://yoursite.com/wp-json/wp/v2"
    headers = {
        'Authorization': 'Bearer YOUR_WP_TOKEN'
    }
    
    # Get new posts
    posts = requests.get(f"{wp_url}/posts?status=publish", headers=headers).json()
    
    for post in posts:
        if not has_featured_video(post['id']):
            # Generate video from post excerpt
            prompt = post['excerpt']['rendered']
            generation_id = generate_video(
                prompt=prompt[:1000],  # Max 1000 chars
                aspect_ratio="landscape",
                duration=15
            )
            video_url = wait_for_video(generation_id)
            
            # Set as featured video
            update_post_featured_video(post['id'], video_url)
```

### Notification & Alert Automation

#### Slack/Discord Bot Integration
**Use Case**: Generate videos from text commands in chat
**Integration Points**:
- Slack API
- Discord Bot API
- Microsoft Teams

**Setup Example**:
```python
# Slack bot for video generation
from slack_bolt import App

app = App(token=os.environ["SLACK_BOT_TOKEN"])

@app.command("/generate-video")
def generate_video_command(ack, respond, command):
    ack()
    prompt = command['text']
    
    try:
        generation_id = generate_video(
            prompt=prompt,
            aspect_ratio="portrait",
            duration=10
        )
        respond(f"Video generation started! ID: {generation_id}")
        
        # Poll in background
        video_url = wait_for_video(generation_id)
        respond(f"Video ready! {video_url}")
    except Exception as e:
        respond(f"Error: {str(e)}")
```

### API Integration Patterns

#### Webhook-Based Automation
**Use Case**: Trigger video generation from external events
**Integration Points**:
- Zapier
- Make (Integromat)
- n8n
- Custom webhooks

**Setup Example**:
```python
# Flask webhook endpoint
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/webhook/generate-video', methods=['POST'])
def webhook_generate():
    data = request.json
    prompt = data.get('prompt')
    aspect_ratio = data.get('aspect_ratio', 'portrait')
    duration = data.get('duration', 10)
    
    try:
        generation_id = generate_video(prompt, aspect_ratio, duration)
        return jsonify({
            'success': True,
            'generationId': generation_id
        })
    except Exception as e:
        return jsonify({
            'success': False,
            'error': str(e)
        }), 400
```

#### Scheduled Automation (Cron Jobs)
**Use Case**: Generate videos on a schedule
**Setup Example**:
```python
# Scheduled video generation
import schedule
import time

def daily_video_generation():
    """Generate daily video content"""
    prompts = [
        "Morning motivation video",
        "Daily news summary",
        "Product of the day showcase"
    ]
    
    for prompt in prompts:
        generation_id = generate_video(prompt, "portrait", 15)
        # Store generation_id for later retrieval
        save_generation_id(generation_id)

# Schedule daily at 9 AM
schedule.every().day.at("09:00").do(daily_video_generation)

while True:
    schedule.run_pending()
    time.sleep(60)
```

### Batch Processing Automation

#### Bulk Video Generation
**Use Case**: Generate multiple videos from a list of prompts
**Setup Example**:
```python
# Batch video generator with rate limit handling
import asyncio
from concurrent.futures import ThreadPoolExecutor

def batch_generate_videos(prompts, max_workers=5):
    """Generate multiple videos with rate limit management"""
    results = []
    
    def process_prompt(prompt):
        try:
            generation_id = generate_video(prompt, "portrait", 10)
            video_url = wait_for_video(generation_id)
            return {'prompt': prompt, 'video_url': video_url, 'status': 'success'}
        except Exception as e:
            return {'prompt': prompt, 'error': str(e), 'status': 'failed'}
    
    with ThreadPoolExecutor(max_workers=max_workers) as executor:
        results = list(executor.map(process_prompt, prompts))
    
    return results

# Usage
prompts = [
    "Video 1 description",
    "Video 2 description",
    "Video 3 description"
]
results = batch_generate_videos(prompts)
```

### Database-Driven Automation

#### Content Queue System
**Use Case**: Process video generation requests from a database queue
**Setup Example**:
```python
# Database queue processor
import sqlite3
import time

def process_video_queue():
    """Process pending video generation requests from database"""
    conn = sqlite3.connect('video_queue.db')
    cursor = conn.cursor()
    
    while True:
        # Get pending requests
        cursor.execute("""
            SELECT id, prompt, aspect_ratio, duration 
            FROM video_queue 
            WHERE status = 'pending' 
            LIMIT 1
        """)
        row = cursor.fetchone()
        
        if not row:
            time.sleep(10)  # Wait if no pending requests
            continue
        
        queue_id, prompt, aspect_ratio, duration = row
        
        try:
            # Update status to processing
            cursor.execute(
                "UPDATE video_queue SET status = 'processing' WHERE id = ?",
                (queue_id,)
            )
            conn.commit()
            
            # Generate video
            generation_id = generate_video(prompt, aspect_ratio, duration)
            video_url = wait_for_video(generation_id)
            
            # Update with result
            cursor.execute("""
                UPDATE video_queue 
                SET status = 'completed', 
                    video_url = ?, 
                    generation_id = ?
                WHERE id = ?
            """, (video_url, generation_id, queue_id))
            conn.commit()
            
        except Exception as e:
            cursor.execute(
                "UPDATE video_queue SET status = 'failed', error = ? WHERE id = ?",
                (str(e), queue_id)
            )
            conn.commit()
    
    conn.close()
```

---

## 9. Setting Up Text-to-Video Automations

### Overview
This section provides step-by-step guides for setting up automated text-to-video workflows that integrate the ViralWave Studio API into your existing systems.

### Prerequisites
- API key from ViralWave Studio
- Basic programming knowledge (Python, JavaScript, or similar)
- Access to the platform you want to integrate with (API keys, webhooks, etc.)

### Automation Architecture Patterns

#### Pattern 1: Event-Driven Automation
Trigger video generation based on events (new post, new product, scheduled time)

**Components**:
- Event listener/webhook receiver
- Video generation service
- Status polling service
- Result handler (upload, store, notify)

**Flow**:
```
Event → Trigger → Generate Video → Poll Status → Handle Result
```

#### Pattern 2: Queue-Based Automation
Process video generation requests from a queue (database, message queue, etc.)

**Components**:
- Queue system (database, Redis, RabbitMQ)
- Worker processes
- Rate limiter
- Result storage

**Flow**:
```
Queue → Worker → Generate Video → Poll Status → Store Result → Notify
```

#### Pattern 3: Scheduled Automation
Generate videos on a fixed schedule (daily, weekly, etc.)

**Components**:
- Scheduler (cron, task scheduler)
- Content source (RSS, database, API)
- Video generator
- Distribution system

**Flow**:
```
Schedule → Fetch Content → Generate Video → Distribute
```

### Step-by-Step Setup Guides

#### Setup 1: WordPress Auto-Video Plugin

**Goal**: Automatically generate featured videos for new blog posts

**Step 1: Install Dependencies**
```bash
pip install requests wordpress-api
```

**Step 2: Create WordPress Plugin**
```php
<?php
// wp-content/plugins/auto-video-generator/auto-video-generator.php
/*
Plugin Name: Auto Video Generator
Description: Automatically generates videos for new posts using ViralWave Studio API
Version: 1.0
*/

add_action('save_post', 'generate_post_video', 10, 3);

function generate_post_video($post_id, $post, $update) {
    // Skip if already has video
    if (get_post_meta($post_id, 'generated_video_url', true)) {
        return;
    }
    
    // Call external service to generate video
    $api_endpoint = 'https://your-server.com/api/generate-video';
    $response = wp_remote_post($api_endpoint, [
        'body' => json_encode([
            'post_id' => $post_id,
            'excerpt' => get_the_excerpt($post_id),
            'title' => get_the_title($post_id)
        ]),
        'headers' => ['Content-Type' => 'application/json']
    ]);
}
```

**Step 3: Create Python Service**
```python
# video_generator_service.py
from flask import Flask, request, jsonify
import requests
import time

app = Flask(__name__)
API_KEY = "vws_your_api_key_here"
BASE_URL = "https://api.viralwavestudio.com/api/v1"

def generate_video(prompt):
    # Implementation from earlier examples
    pass

@app.route('/api/generate-video', methods=['POST'])
def handle_wordpress_request():
    data = request.json
    post_id = data['post_id']
    excerpt = data['excerpt']
    
    # Generate video
    generation_id = generate_video(excerpt[:1000])
    video_url = wait_for_video(generation_id)
    
    # Update WordPress post
    update_wordpress_post(post_id, video_url)
    
    return jsonify({'success': True, 'video_url': video_url})

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

#### Setup 2: Shopify Product Video Automation

**Goal**: Auto-generate videos for new products

**Step 1: Create Shopify App**
```javascript
// shopify-app/server.js
const express = require('express');
const { shopifyApi } = require('@shopify/shopify-api');

const app = express();

app.post('/webhooks/products/create', async (req, res) => {
    const product = req.body;
    
    // Generate video from product description
    const generationId = await generateVideo(
        `Product showcase: ${product.title}. ${product.body_html}`,
        'landscape',
        15
    );
    
    // Poll for completion and update product
    const videoUrl = await waitForVideo(generationId);
    await updateProductVideo(product.id, videoUrl);
    
    res.status(200).send('OK');
});
```

**Step 2: Set Up Webhook in Shopify**
- Go to Shopify Admin → Settings → Notifications
- Add webhook: `https://your-app.com/webhooks/products/create`
- Event: `Product creation`

#### Setup 3: Social Media Scheduler Integration

**Goal**: Auto-generate videos for scheduled social media posts

**Step 1: Buffer/Hootsuite Integration**
```python
# social_media_automation.py
import requests
from buffer_api import BufferAPI

buffer = BufferAPI(access_token='your_token')

def process_scheduled_posts():
    """Check for posts needing videos and generate them"""
    scheduled_posts = buffer.get_scheduled_posts()
    
    for post in scheduled_posts:
        if post['text'] and not post.get('video_url'):
            # Generate video from post text
            generation_id = generate_video(
                prompt=post['text'],
                aspect_ratio="portrait",
                duration=15
            )
            video_url = wait_for_video(generation_id)
            
            # Update post with video
            buffer.update_post(post['id'], media_url=video_url)
```

#### Setup 4: Zapier/Make Integration

**Goal**: No-code automation using Zapier or Make

**Zapier Setup**:
1. Create new Zap
2. Trigger: Choose your trigger (new blog post, new email, etc.)
3. Action: Webhook by Zapier
4. Configure webhook:
   - URL: `https://your-server.com/api/generate-video`
   - Method: POST
   - Data: `{"prompt": "{{trigger_field}}"}`
5. Add delay action (wait 5 minutes for video generation)
6. Add second webhook to check status
7. Final action: Upload video to destination

**Make (Integromat) Setup**:
1. Create new scenario
2. Add trigger module (RSS, Database, etc.)
3. Add HTTP module (POST to generate video)
4. Add delay module (5 minutes)
5. Add HTTP module (POST to check status) - loop until complete
6. Add final module (upload to destination)

#### Setup 5: Discord/Slack Bot

**Goal**: Generate videos from chat commands

**Discord Bot Setup**:
```python
# discord_bot.py
import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True
bot = commands.Bot(command_prefix='!', intents=intents)

@bot.command(name='video')
async def generate_video_command(ctx, *, prompt):
    """Generate a video from text prompt"""
    await ctx.send(f"🎬 Generating video: {prompt[:50]}...")
    
    try:
        generation_id = generate_video(prompt, "portrait", 10)
        await ctx.send(f"⏳ Video generation started! ID: `{generation_id}`")
        
        # Poll in background
        video_url = wait_for_video(generation_id)
        await ctx.send(f"✅ Video ready! {video_url}")
    except Exception as e:
        await ctx.send(f"❌ Error: {str(e)}")

bot.run('YOUR_DISCORD_TOKEN')
```

### Environment Setup

#### Python Environment
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install requests flask python-dotenv schedule
```

#### Node.js Environment
```bash
# Initialize project
npm init -y

# Install dependencies
npm install axios express node-cron dotenv
```

#### Environment Variables
Create `.env` file:
```env
VWS_API_KEY=vws_your_api_key_here
VWS_BASE_URL=https://api.viralwavestudio.com/api/v1
WEBHOOK_SECRET=your_webhook_secret
DATABASE_URL=your_database_url
```

### Error Handling & Retry Logic

#### Robust Video Generation Function
```python
import time
import random

def generate_video_with_retry(prompt, max_retries=3, backoff_factor=2):
    """Generate video with automatic retry on failure"""
    for attempt in range(max_retries):
        try:
            generation_id = generate_video(prompt)
            return wait_for_video(generation_id)
        except requests.exceptions.HTTPError as e:
            if e.response.status_code == 429:
                # Rate limited - use Retry-After header
                retry_after = int(e.response.headers.get('Retry-After', 60))
                wait_time = retry_after + random.uniform(0, 10)
                print(f"Rate limited. Waiting {wait_time} seconds...")
                time.sleep(wait_time)
                continue
            elif e.response.status_code == 402:
                # Insufficient credits
                raise Exception("Insufficient credits. Please top up your account.")
            elif attempt < max_retries - 1:
                wait_time = backoff_factor ** attempt
                print(f"Retry {attempt + 1}/{max_retries} after {wait_time} seconds...")
                time.sleep(wait_time)
                continue
            else:
                raise
        except Exception as e:
            if attempt < max_retries - 1:
                wait_time = backoff_factor ** attempt
                print(f"Retry {attempt + 1}/{max_retries} after {wait_time} seconds...")
                time.sleep(wait_time)
                continue
            else:
                raise
```

### Monitoring & Logging

#### Setup Logging
```python
import logging
from datetime import datetime

logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('video_generation.log'),
        logging.StreamHandler()
    ]
)

logger = logging.getLogger(__name__)

def generate_video_with_logging(prompt):
    logger.info(f"Starting video generation for prompt: {prompt[:50]}...")
    try:
        generation_id = generate_video(prompt)
        logger.info(f"Generation started: {generation_id}")
        video_url = wait_for_video(generation_id)
        logger.info(f"Video completed: {video_url}")
        return video_url
    except Exception as e:
        logger.error(f"Video generation failed: {str(e)}")
        raise
```

### Cost Monitoring

#### Track API Usage
```python
import sqlite3
from datetime import datetime

def track_video_generation(prompt, video_url, cost=0.30):
    """Track video generation for cost monitoring"""
    conn = sqlite3.connect('usage.db')
    cursor = conn.cursor()
    
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS video_generations (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            prompt TEXT,
            video_url TEXT,
            cost REAL,
            created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
        )
    """)
    
    cursor.execute("""
        INSERT INTO video_generations (prompt, video_url, cost)
        VALUES (?, ?, ?)
    """, (prompt, video_url, cost))
    
    conn.commit()
    conn.close()

def get_monthly_cost():
    """Calculate monthly video generation costs"""
    conn = sqlite3.connect('usage.db')
    cursor = conn.cursor()
    
    cursor.execute("""
        SELECT SUM(cost) as total_cost, COUNT(*) as video_count
        FROM video_generations
        WHERE created_at >= datetime('now', '-30 days')
    """)
    
    result = cursor.fetchone()
    conn.close()
    
    return {
        'total_cost': result[0] or 0,
        'video_count': result[1] or 0
    }
```

---

## 9. Best Practices & Tips

### Prompt Engineering
- Writing effective video prompts
- Including specific details for better results
- Avoiding ambiguous descriptions
- Examples of good vs. bad prompts

### Cost Optimization
- Choosing the right duration (10s vs 15s)
- Batch processing strategies
- Caching and reusing content
- Monitoring usage and costs

### Performance Optimization
- Async processing patterns
- Webhook integration for better UX
- Error handling and retries
- Rate limiting considerations

### Security Best Practices
- Protecting API keys
- Using environment variables
- Implementing proper authentication
- Secure video storage

### Quality Tips
- Iterating on prompts for better results
- Understanding generation times
- Handling failed generations
- Video post-processing considerations

---

## 10. Troubleshooting & Support

### Common Issues

#### Authentication Errors
- Invalid API key
- Expired credentials
- Missing headers

#### Generation Failures
- Invalid prompts
- Rate limiting
- Service outages
- Timeout handling

#### Video Quality Issues
- Understanding generation limitations
- Prompt refinement strategies
- When to regenerate

### Getting Help
- 24/7 support availability
- Support channels (email, chat, etc.)
- Documentation resources
- Community forums (if available)

### Error Codes Reference
- Complete list of error codes
- What each error means
- How to resolve common errors

---

## 11. FAQ

### Pricing & Billing
- **Q: How does the pay-as-you-go system work?**
  - A: Top up credits as needed, no monthly fees. Each video costs $0.30 regardless of duration (10s or 15s).

- **Q: Is there a minimum purchase requirement?**
  - A: [Answer based on site information]

- **Q: Can I get a refund for unused credits?**
  - A: [Answer based on site information]

### Technical Questions
- **Q: Is this the same Sora 2 API from OpenAI?**
  - A: Yes, ViralWave Studio uses the exact same OpenAI Sora 2 API technology, ensuring identical quality and capabilities.

- **Q: How long does it take to generate a video?**
  - A: Average generation time is 2-5 minutes, though this can vary based on complexity and current load.

- **Q: What's the difference between 10-second and 15-second videos?**
  - A: Both cost the same ($0.30), so choose based on your content needs. Longer videos allow for more complex narratives.

- **Q: What programming languages are supported?**
  - A: Any language that can make HTTP requests. We provide examples in Python, JavaScript, PHP, and cURL.

### Usage & Licensing
- **Q: Can I use the generated videos commercially?**
  - A: Yes, all videos come with a commercial license included. Use them for any commercial purpose without restrictions.

- **Q: Are there watermarks on the videos?**
  - A: No, all videos are generated watermark-free and ready for professional use.

- **Q: What are the usage limits?**
  - A: [Answer based on site information]

### Integration
- **Q: How easy is it to integrate?**
  - A: Very easy! Simple REST API that can be integrated in minutes with comprehensive documentation and code examples.

- **Q: Do you offer webhooks?**
  - A: [Answer based on site information - appears to be available based on features section]

- **Q: Is there an SDK available?**
  - A: [Answer based on site information]

---

## 12. Conclusion

Congratulations! You've now learned everything you need to start using the Sora 2 API at 70% off OpenAI's direct pricing. Let's recap what we've covered and outline your next steps.

### Summary of Benefits

By choosing ViralWave Studio over OpenAI Direct, you gain:

1. **70%+ Cost Savings**: Generate videos at $0.30 each instead of $1.00-$1.50, saving hundreds or thousands of dollars monthly
2. **Same Technology and Quality**: Identical OpenAI Sora 2 API ensures no compromise on video quality or capabilities
3. **Flexible, Pay-As-You-Go Pricing**: No subscriptions, no monthly commitments - only pay for videos you generate
4. **Professional, Commercial-Ready Videos**: Watermark-free videos with full commercial license included
5. **Excellent Developer Experience**: Simple REST API, comprehensive documentation, and code examples in multiple languages
6. **Reliable Infrastructure**: 99.9% uptime SLA with 24/7 support
7. **Fast Integration**: Get up and running in minutes, not days

### What You've Learned

Throughout this guide, we've covered:

- ✅ **Cost Analysis**: Understanding the true savings (70-80% reduction)
- ✅ **Account Setup**: Creating an account, getting API keys, and managing credits
- ✅ **API Integration**: Authentication, endpoints, and request/response handling
- ✅ **Code Examples**: Production-ready code in Python, JavaScript, PHP, and cURL
- ✅ **Automation Patterns**: Event-driven, queue-based, and scheduled automation
- ✅ **Use Cases**: Social media, e-commerce, content management, and more
- ✅ **Best Practices**: Security, error handling, rate limiting, and optimization
- ✅ **Troubleshooting**: Common issues and how to resolve them

### Next Steps

Now that you understand how the system works, here's your action plan:

#### 1. Sign Up and Get Started
- [ ] Create your ViralWave Studio account
- [ ] Verify your email address
- [ ] Get your API key from the dashboard
- [ ] Top up at least $5-10 in credits to get started

#### 2. Generate Your First Video
- [ ] Test the API with the Quick Start script
- [ ] Verify you can successfully generate and retrieve a video
- [ ] Experiment with different prompts and aspect ratios

#### 3. Integrate Into Your Application
- [ ] Choose your integration approach (direct API, webhook, automation tool)
- [ ] Implement error handling and retry logic
- [ ] Set up monitoring and logging
- [ ] Test thoroughly in a development environment

#### 4. Build Automation (Optional)
- [ ] Identify your automation needs (social media, e-commerce, content management)
- [ ] Set up your chosen automation pattern
- [ ] Test with a small volume before scaling
- [ ] Monitor costs and optimize as needed

#### 5. Scale and Optimize
- [ ] Monitor your usage and costs
- [ ] Optimize prompts for better results
- [ ] Implement caching where appropriate
- [ ] Set up alerts for low credits or errors

### Resources

**Official Documentation:**
- [ViralWave Studio API Documentation](https://viralwavestudio.com/sora-api)
- [Get API Access](https://viralwavestudio.com/api-login)
- [Pricing Information](https://viralwavestudio.com/sora-api#pricing)

**Support:**
- Check your dashboard for support contact information
- 24/7 email and chat support available
- Community forums (if available)

**Code Examples:**
- All code examples from this guide are ready to use
- Modify them to fit your specific needs
- Share improvements with the community

### Final Thoughts

#### Why This Approach Makes Sense

For 95% of developers and businesses, ViralWave Studio offers the optimal balance of:

- **Cost Efficiency**: Significant savings without quality compromise
- **Simplicity**: Easy integration and straightforward pricing
- **Flexibility**: Pay-as-you-go model adapts to your needs
- **Reliability**: Enterprise-grade infrastructure you can depend on

Whether you're a solo developer building a side project, a startup creating an MVP, or an enterprise scaling video generation, the 70% cost savings can make the difference between a viable product and an unaffordable one.

#### The Future of Cost-Effective AI Video Generation

As AI video generation technology continues to evolve, cost-effective access becomes increasingly important. By using services like ViralWave Studio:

- **More developers** can experiment with AI video generation
- **More businesses** can afford to integrate video into their products
- **More creators** can produce content at scale
- **More innovation** happens when barriers to entry are lowered

The democratization of AI video generation benefits everyone - from individual creators to large enterprises.

#### Community and Ecosystem Growth

As more developers adopt cost-effective solutions:

- **Open Source Tools**: Community-built libraries and SDKs
- **Best Practices**: Shared knowledge and optimization techniques
- **Use Cases**: Creative applications we haven't even imagined yet
- **Innovation**: Lower costs enable more experimentation

Consider contributing to the community:
- Share your automation setups
- Open source useful tools or libraries
- Write tutorials or blog posts
- Help others in forums and communities

### You're Ready!

You now have everything you need to start generating professional AI videos at 70% off OpenAI's pricing. The technology is powerful, the integration is straightforward, and the savings are substantial.

**Start small, experiment, and scale as you grow.** The best way to learn is by doing, so don't hesitate to start generating videos and building your applications.

Good luck, and happy video generating! 🎬

---

**Questions or Need Help?**

- Review the troubleshooting section (Section 10)
- Check the FAQ (Section 11)
- Contact ViralWave Studio support
- Refer back to the relevant sections of this guide

Remember: Every expert was once a beginner. Start with simple implementations and gradually build more complex systems as you gain experience.

---

## Appendix

### A. Complete API Reference
- Full endpoint documentation
- Request/response schemas
- Authentication details
- Rate limits

### B. Advanced Examples
- Batch processing
- Webhook integration
- Error handling patterns
- Production-ready implementations

### C. Migration Guide
- Moving from OpenAI direct to ViralWave Studio
- Code migration examples
- Cost comparison calculator

### D. Additional Resources
- Prompt library
- Video generation tips
- Community examples
- Related tools and services

---

---

**Last Updated**: December 2024
**Version**: 1.0
**Guide Author**: Community Guide
**Maintained By**: cheap-sora2-api repository

---

## Quick Reference Card

### API Endpoints
- **Generate Video**: `POST /v1/generate-video`
- **Check Status**: `POST /v1/check-video-status`

### Pricing
- **ViralWave Studio**: $0.30 per video (10s or 15s)
- **OpenAI Direct**: $1.00 (10s) or $1.50 (15s)
- **Savings**: 70-80%

### Rate Limits
- **Per API Key**: 60 requests/minute
- **Per IP**: 100 requests/minute

### Request Limits
- **Prompt**: Max 1,000 characters
- **Body**: Max 10KB

### Authentication
```http
Authorization: Bearer vws_your_api_key_here
```

### Status Values
- `pending` → `in_progress` → `completed` or `failed`

### Support
- 24/7 support available
- Check dashboard for contact information
