# Module 3.13 assignment

The steps taken in execution of this AWS Secrets at work repo are:

1. From AWS Console, go to AWS Secrets Manager.
2. Click "Store a new secret".
3. Select "Other type of secret" at the type of secret prompt.
4. Create the following secret key-value pairs:
     i.   lcchua-key1: orange
     ii.  lcchua-key2: blue
     iii. lcchua-key3: tea
5. Next perform "unit-test" by running the following AWS CLI command:

   ```sh
   aws secretsmanager get-secret-value --secret-id prod/hello_app/secret_keys --query SecretString --output json
   ```
6. This AWS CLI command will retrieve and output the key-value pair secrets created in Step 4.
7. Next go back to AWS Console, and go to AWS Parameter Store.
8. Click "Create parameter".
9. Create the following parameters:

   | Parameter Name  | Parameter Type | Parameter Value |
   | --------------- | -------------- | --------------- |
   | /lcchua/name    | string         | John Smith      |
   | /lcchua/country | string         | Singapore       |

10. Next perform "unit-test" by running the following AWS CLI command:

    ```sh
    aws ssm get-parameter --name /lcchua/name --query Parameter.Value --output text
    ```
    ```sh
    aws ssm get-parameter --name /lcchua/country --query Parameter.Value --output text
    ```
11. This AWS CLI commands will retrieve and output the parameters created in Step 9.
12. Last, either perform `git push` to trigger or manually dispatch the `retrieve.yaml` workflow under the `.github/workflows` directory. The outputs of this workflow will look like:

![Screenshot 2024-11-11 at 9 18 52 PM](https://github.com/user-attachments/assets/f55a08bf-2cf5-403f-a525-bbbe8480ffcc)

![Screenshot 2024-11-11 at 9 19 08 PM](https://github.com/user-attachments/assets/786e6bf3-bbfb-46a9-818d-af18a62e4149)

![Screenshot 2024-11-11 at 9 19 00 PM](https://github.com/user-attachments/assets/71f40ea3-f6d2-4f7f-b5b5-be4bc6e668c5)
