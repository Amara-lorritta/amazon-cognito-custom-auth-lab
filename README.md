# amazon-cognito-custom-auth-lab

This project demonstrates a serverless custom authentication flow using Amazon Cognito, AWS Lambda, and Amazon CloudWatch. It was completed as part of a hands-on AWS lab to build a secure and flexible user login authentication process.

## 🧩 Lab Objectives
- ✅ Configured an Amazon Cognito user pool.
- ✅ Created Lambda functions for custom authentication flow:
  - `DefineAuthFunction`
  - `AuthFunction`
  - `AuthChallengeResponseFunction`
- ✅ Integrated the flow with CloudWatch Logs for observability.
- ✅ Successfully tested the authentication lifecycle.

## 🛠️ Architecture
![image](https://github.com/user-attachments/assets/aedc1352-d5f6-4bb0-931b-c60cd9d99fbf)

The solution uses three Lambda functions triggered in sequence by Amazon Cognito:
1. **DefineAuthChallenge** – Initiates the custom challenge
2. **CreateAuthChallenge** – Generates and issues a verification code
3. **VerifyAuthChallengeResponse** – Verifies the user’s response
4. All Lambda function activity is logged and monitored using **Amazon CloudWatch**.


![creating user pool name](https://github.com/user-attachments/assets/2c538a3d-0a20-4746-bb35-8bb103b1eb46)


![updatedDefineAuthFunction](https://github.com/user-attachments/assets/69f36620-37ae-4c76-bbe9-17f40ba0c7c5)


![updated passwordpolicy](https://github.com/user-attachments/assets/e1129afa-576b-4290-a8c7-39a8fdd00dd7)


![Test User](https://github.com/user-attachments/assets/018ff957-bf08-465f-aa71-9eef5bff04bd)


![Testing AuthFunction](https://github.com/user-attachments/assets/897ff87e-a58b-4a26-b458-87b33c97a8ec)


![TestingDefineAuthhFunction](https://github.com/user-attachments/assets/398f1b90-5c26-4cd3-bfb0-bb571acf769b)


![Testing AuthChallengeResponseFunction](https://github.com/user-attachments/assets/bd36b278-fc6e-465e-aab4-06801b21bf15)


![LambdaTriggersCreated](https://github.com/user-attachments/assets/7af705d3-d4c8-4bba-a395-ba7926a24ca9)


## 📂 Tech Stack

- Amazon Cognito  
- AWS Lambda (Python 3.13)  
- Amazon CloudWatch  

## 🚀 How It Works

1. User initiates login through the Cognito user pool.
2. Cognito triggers the first Lambda (`DefineAuthFunction`) to start a `CUSTOM_CHALLENGE`.
3. The second Lambda (`AuthFunction`) generates a code challenge for the user.
4. The user responds with the code verified by the third Lambda (`AuthChallengeResponseFunction`).
5. All responses and outcomes are tracked in CloudWatch.

