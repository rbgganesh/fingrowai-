# Vehicle Finance & Insurance Digital Platform

A comprehensive digital platform for automobile dealers to process vehicle finance, insurance, and loan management for both **Two-Wheeler** and **Four-Wheeler** vehicles with AI-powered decision making.

## 🎯 Key Features

### Vehicle Types Supported
- **🏍️ Two-Wheelers**: Motorcycle, Scooter, Moped
- **🚗 Four-Wheelers**: Sedan, SUV, Hatchback, Coupe, Truck, Commercial

### AI/ML Features
- ✅ **Fraud Detection**: Risk scoring, behavioral analysis, document forgery detection
- ✅ **Document OCR**: Text extraction, data parsing, validation
- ✅ **Credit Scoring**: Multi-factor analysis, CIBIL comparison
- ✅ **Automated Underwriting**: Intelligent approval decisions
- ✅ **AI Chatbot**: 24/7 customer support

### Products
- **Loans**: Vehicle-specific eligibility, EMI calculation, lender comparison
- **Insurance**: Comprehensive plans with add-ons, premium calculation
- **Document Management**: Digital locker, OCR extraction, e-sign
- **Analytics**: Real-time dashboards, approval metrics, conversion tracking

## 📋 Business Workflow

```
Customer Registration → KYC Verification → CIBIL Check → Loan Pre-Approval
→ Insurance Processing → Final Loan Approval → Disbursement → Vehicle Delivery
```

## 🛠 Technology Stack

### Backend
- **Framework**: Node.js + Express.js
- **Database**: PostgreSQL
- **Cache**: Redis
- **Authentication**: JWT + OAuth2
- **Cloud Storage**: AWS S3

### Frontend (To Be Implemented)
- **Framework**: React.js + Next.js
- **Styling**: Tailwind CSS
- **State Management**: Redux

### Infrastructure
- **Containerization**: Docker
- **Orchestration**: Docker Compose
- **Cloud**: AWS Ready

## 📁 Project Structure

```
.
├── backend/                    # Node.js API
│   ├── src/
│   │   ├── controllers/       # Business logic
│   │   ├── services/          # AI & business services
│   │   ├── routes/            # API endpoints
│   │   ├── middleware/        # Auth & error handling
│   │   ├── config/            # Configuration
│   │   └── app.js             # Express app
│   ├── database/
│   │   └── schema.sql         # Database schema
│   └── Dockerfile
├── database/
│   ├── schema.sql             # Full database schema
│   └── schema-updates.sql     # Two-wheeler support
├── docker-compose.yml         # Docker orchestration
├── .env.example               # Environment template
└── README.md
```

## 🚀 Quick Start

### Using Docker (Recommended)
```bash
docker-compose up
```

### Manual Setup

**Backend**
```bash
cd backend
npm install
npm run migrate
npm run dev
```

**Database**
```bash
psql -U financeapp -d vehicle_finance < database/schema.sql
```

## 🔌 API Endpoints

### Vehicles
- `POST /api/vehicles` - Create vehicle
- `GET /api/vehicles/type/:vehicleType` - Get by type
- `GET /api/vehicles/stats/overview` - Statistics

### Loans
- `POST /api/loans` - Create loan
- `GET /api/loans` - List loans (with filters)
- `GET /api/loans/eligibility/criteria` - Eligibility by type
- `POST /api/loans/compare` - Compare lenders
- `POST /api/loans/calculate/emi-breakdown` - EMI calculation

### Insurance
- `POST /api/insurance` - Create policy
- `GET /api/insurance/plans` - Get plans by type
- `GET /api/insurance/quotes` - Get quotes
- `POST /api/insurance/calculate-premium` - Premium calculation

### AI Services
- `POST /api/ai/fraud-detection/analyze` - Fraud analysis
- `POST /api/ai/ocr/extract` - Document OCR
- `GET /api/ai/credit-scoring/:customerId` - Credit score
- `POST /api/ai/underwriting/:loanId` - Automated underwriting
- `POST /api/ai/chatbot/message` - Chat support

### Dashboard
- `GET /api/dashboard/statistics` - Dashboard stats
- `GET /api/dashboard/approval-ratio` - Approval metrics
- `GET /api/dashboard/insurance-conversion` - Conversion rate

## 📊 Two-Wheeler vs Four-Wheeler

### Loans
| Feature | Two-Wheeler | Four-Wheeler |
|---------|-------------|---------------|
| Min Loan | ₹50,000 | ₹2,00,000 |
| Max Loan | ₹10,00,000 | ₹50,00,000 |
| Max LTV | 90% | 85% |
| Max Tenure | 60 months | 84 months |
| Base Rate | 10.5% | 9.5% |

### Insurance
| Plan | Two-Wheeler | Four-Wheeler |
|------|-------------|---------------|
| Third Party | ₹500/year | ₹1,200/year |
| Comprehensive | ₹2,500/year (3%) | ₹6,000/year (4%) |
| Zero Depreciation | ₹3,500/year (4.5%) | ₹8,500/year (6%) |

## 🔐 Security
- JWT authentication
- OAuth2 ready
- Role-based access control
- SSL/TLS encryption
- Rate limiting
- Audit logging
- Data encryption

## 📈 Key Metrics
- Application count (by vehicle type)
- Approval ratio (by vehicle type)
- Insurance conversion rate
- Pending approvals
- Revenue tracking
- Fraud detection alerts

## 🤖 AI Features Explained

### Fraud Detection
- Fraud score (0-100)
- Duplicate detection
- Income verification
- Document forgery detection
- Behavioral analysis

### Document OCR
- PAN, Aadhaar, DL extraction
- Bank statement parsing
- Salary slip analysis
- Data validation

### Credit Scoring
- Income stability (20%)
- Employment history (15%)
- Debt-to-income ratio (25%)
- Payment history (20%)
- Credit mix (10%)
- Credit age (10%)

### Automated Underwriting
- Fraud risk assessment
- Credit quality evaluation
- Income & debt analysis
- LTV analysis
- Collateral evaluation
- Employment verification
- Interest rate recommendation
- Approval conditions

### AI Chatbot
- Loan status inquiry
- Insurance quotes
- EMI calculation
- Document guidance
- Eligibility check
- 24/7 support

## 📚 Environment Variables

See `.env.example` for all required variables:

```bash
# Database
DB_HOST=postgres
DB_PORT=5432
DB_USER=financeapp
DB_PASSWORD=financeapp123
DB_NAME=vehicle_finance

# JWT
JWT_SECRET=your_secret_key
JWT_EXPIRY=7d

# APIs
CIBIL_API_KEY=xxx
KYC_API_KEY=xxx
INSURANCE_API_KEY=xxx
PAYMENT_GATEWAY_KEY=xxx

# AWS
AWS_ACCESS_KEY_ID=xxx
AWS_SECRET_ACCESS_KEY=xxx
AWS_REGION=us-east-1
```

## 🧪 Testing

```bash
cd backend
npm run test
```

## 📖 Documentation

- [Implementation Guide](./IMPLEMENTATION_GUIDE.md)
- [API Documentation](./docs/API_DOCUMENTATION.md) - (To be created)
- [Database Schema](./database/schema.sql)

## 🔄 Workflow Overview

1. **Customer Onboarding**
   - Registration with OTP
   - Personal & professional details
   - Vehicle selection

2. **Document Collection**
   - Upload PAN, Aadhaar, Income Proof
   - AI OCR extraction
   - Data validation

3. **KYC Verification**
   - Aadhaar verification API
   - PAN verification API
   - Face match
   - Fraud detection

4. **Credit Analysis**
   - CIBIL API check
   - AI credit scoring
   - Risk assessment

5. **Loan Processing**
   - Eligibility check
   - EMI calculation
   - Lender routing
   - Pre-approval

6. **Insurance**
   - Premium quotation
   - Plan comparison
   - Policy issuance

7. **Final Approval**
   - Document verification
   - Hypothecation check
   - Final loan approval

8. **Disbursement**
   - Payment processing
   - Dealer settlement
   - Vehicle delivery

## 👥 User Roles

- **Super Admin**: Platform management
- **Dealer Admin**: Dealer operations
- **Sales Executive**: Customer onboarding
- **Finance Executive**: Loan processing
- **Insurance Executive**: Insurance management
- **Customer**: Vehicle buyer
- **Auditor**: Compliance & audit

## 💼 Business Model

**Revenue Streams**:
- Insurance commission (2-5%)
- Loan processing fee (1%)
- Platform subscription
- API usage fees

## 🚀 Deployment

### Development
```bash
docker-compose up
```

### Production
- AWS EC2 with Docker
- RDS for PostgreSQL
- ElastiCache for Redis
- CloudFront for CDN
- Kubernetes (optional scaling)

## 📞 Support

For questions or support, please contact: support@vehiclefinance.com

## 📄 License

Proprietary - All rights reserved © 2025

---

**Last Updated**: 2025-05-29  
**Version**: 1.0.0  
**Status**: 🟢 Active Development
