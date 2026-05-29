# Complete Backend Implementation

This directory contains the complete Node.js/Express backend for the Vehicle Finance Platform.

## Features Implemented

### Controllers
- ✅ **auth.controller.js** - User authentication & registration
- ✅ **customer.controller.js** - Customer management
- ✅ **vehicle.controller.js** - Vehicle management (two/four wheeler)
- ✅ **loan.controller.js** - Loan processing with vehicle type support
- ✅ **insurance.controller.js** - Insurance policies with vehicle type-specific plans
- ✅ **document.controller.js** - Document upload & management with OCR
- ✅ **payment.controller.js** - Payment processing
- ✅ **disbursement.controller.js** - Loan disbursement

### Services (AI/ML)
- ✅ **ai-fraud-detection.service.js** - Fraud scoring & analysis
- ✅ **ai-ocr.service.js** - Document OCR & parsing
- ✅ **ai-credit-scoring.service.js** - Credit score calculation
- ✅ **ai-underwriting.service.js** - Automated loan underwriting
- ✅ **ai-chatbot.service.js** - Customer support chatbot

### Routes
- ✅ **auth.routes.js** - Authentication endpoints
- ✅ **customer.routes.js** - Customer management endpoints
- ✅ **vehicle.routes.js** - Vehicle endpoints (with type filtering)
- ✅ **loan.routes.js** - Loan endpoints (with eligibility & comparison)
- ✅ **insurance.routes.js** - Insurance endpoints (with premium calculation)
- ✅ **document.routes.js** - Document endpoints with AI OCR
- ✅ **payment.routes.js** - Payment endpoints
- ✅ **disbursement.routes.js** - Disbursement endpoints
- ✅ **ai.routes.js** - AI service endpoints
- ✅ **dashboard.routes.js** - Dashboard analytics
- ✅ **admin.routes.js** - Admin functions

### Middleware
- ✅ **auth.middleware.js** - JWT authentication & role-based access
- ✅ **error.middleware.js** - Global error handling

### Configuration
- ✅ **app.js** - Express application setup
- ✅ **database.js** - PostgreSQL & Redis connections
- ✅ **aws.js** - AWS S3 integration
- ✅ **payment.js** - Razorpay integration

### Database
- ✅ **schema.sql** - Complete database schema
- ✅ **schema-updates.sql** - Two-wheeler support updates

## Installation

```bash
cd backend
npm install
```

## Running

### Development
```bash
npm run dev
```

### Production
```bash
npm start
```

### Testing
```bash
npm run test
```

## Environment Variables

Create `.env` file (see `.env.example`):

```
BACKEND_PORT=5000
DB_HOST=localhost
DB_PORT=5432
DB_USER=financeapp
DB_PASSWORD=financeapp123
DB_NAME=vehicle_finance
JWT_SECRET=your_secret_key
AWS_ACCESS_KEY_ID=xxx
AWS_SECRET_ACCESS_KEY=xxx
```

## API Endpoints Summary

### Vehicle Management (Type-Specific)
```
POST   /api/vehicles                      - Create (two/four wheeler)
GET    /api/vehicles/type/:vehicleType    - Filter by type
GET    /api/vehicles/stats/overview       - Statistics
```

### Loan Processing (Vehicle-Type Based)
```
POST   /api/loans                         - Create loan
GET    /api/loans?vehicleType=two_wheeler - Filter by type
GET    /api/loans/eligibility/criteria    - Criteria by type
POST   /api/loans/compare                 - Lender comparison
```

### Insurance (Vehicle-Type Specific)
```
POST   /api/insurance                     - Create policy
GET    /api/insurance/plans?vehicleType=..  - Plans by type
POST   /api/insurance/calculate-premium   - Calculate premium
```

### AI Services
```
POST   /api/ai/fraud-detection/analyze
POST   /api/ai/ocr/extract
GET    /api/ai/credit-scoring/:customerId
POST   /api/ai/underwriting/:loanId
POST   /api/ai/chatbot/message
```

## Key Implementation Details

### Two-Wheeler Loan Criteria
- Min: ₹50,000 | Max: ₹10,00,000
- Tenure: 12-60 months
- Base Rate: 10.5%
- Max LTV: 90%

### Four-Wheeler Loan Criteria
- Min: ₹2,00,000 | Max: ₹50,00,000
- Tenure: 12-84 months
- Base Rate: 9.5%
- Max LTV: 85%

### Insurance Plans

**Two-Wheeler**:
- Third Party: ₹500/year
- Comprehensive: ₹2,500/year (3%)
- Zero Depreciation: ₹3,500/year (4.5%)

**Four-Wheeler**:
- Third Party: ₹1,200/year
- Comprehensive: ₹6,000/year (4%)
- Zero Depreciation: ₹8,500/year (6%)

### AI Services

**Fraud Detection**:
- Calculates fraud score (0-100)
- Analyzes behavioral patterns
- Detects document forgery
- Identifies duplicates

**Document OCR**:
- Extracts text from images
- Parses PAN, Aadhaar, DL, bank statements, salary slips
- Validates data format
- Checks consistency

**Credit Scoring**:
- Multi-factor analysis
- Income stability: 20%
- Employment history: 15%
- Debt-to-income: 25%
- Payment history: 20%
- Credit mix: 10%
- Credit age: 10%

**Automated Underwriting**:
- Fraud risk assessment
- Credit evaluation
- Income & debt analysis
- LTV analysis
- Collateral evaluation
- Auto interest rate recommendation

**AI Chatbot**:
- Loan status
- Insurance quotes
- EMI calculation
- Document guidance
- Eligibility check

## Database Structure

### Key Tables
- `users` - User accounts
- `customers` - Customer profiles
- `vehicles` - Vehicle details (with vehicle_type, vehicle_category, displacement_cc)
- `loans` - Loan applications (with vehicle_type)
- `insurance_policies` - Insurance policies (with vehicle_type)
- `documents` - Document storage with OCR
- `payments` - Payment records
- `api_logs` - API audit logs
- `audit_logs` - System audit trail

### Key Indexes
- `idx_vehicles_type` - Fast vehicle type queries
- `idx_loans_vehicle_type` - Loan filtering by type
- `idx_insurance_vehicle_type` - Insurance filtering by type

## Security

- JWT authentication
- Role-based access control
- Encrypted passwords (bcrypt)
- Rate limiting
- CORS enabled
- Helmet security headers
- Audit logging

## Error Handling

Global error middleware catches:
- Validation errors
- Authentication errors
- Authorization errors
- Not found errors
- Server errors

## Testing

Tests can be added for:
- Auth endpoints
- Vehicle CRUD
- Loan creation & updates
- Insurance policy management
- AI services
- Payment processing

## Future Enhancements

- [ ] GraphQL API
- [ ] WebSocket real-time updates
- [ ] Batch processing jobs
- [ ] Advanced analytics
- [ ] Mobile app API
- [ ] Third-party integrations

---

**Status**: ✅ Complete Implementation Ready  
**Last Updated**: 2025-05-29
