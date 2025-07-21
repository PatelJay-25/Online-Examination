# AWS S3/CloudFront Deployment Instructions

## 1. Build the React App
```sh
npm install
npm run build
```

## 2. Set API Base URL
- Create a `.env` file in the `src/` directory:
  ```
  VITE_API_BASE_URL=https://your-backend-api-url
  ```
  Replace with your actual backend URL (Elastic Beanstalk or other).

## 3. Deploy to S3
- Create an S3 bucket (enable static website hosting)
- Upload the contents of the `dist` (or `build`) folder to the bucket
- Set bucket policy for public read (if needed)

## 4. (Optional) Use CloudFront for HTTPS and CDN
- Create a CloudFront distribution pointing to your S3 bucket
- Use the CloudFront URL as your frontend domain

## 5. Update CORS on Backend
- Make sure your backend allows requests from your S3/CloudFront domain

---

## Environment Variables
- All API calls use `VITE_API_BASE_URL` from your `.env` file 