# Deploy-digiflake-admin-panal-project

This project is a CRUD (Create, Read, Update, Delete) application that includes functionalities for managing categories and subcategories. The app has both a backend server and a frontend client.
---------------------------------------------------------------------------------------------------
=> Features
---------------------------------------------------------------------------------------------------
- Manage Categories and Subcategories
-  Upload Images for Categories and Subcategories
- User Authentication
---------------------------------------------------------------------------------------------------
=> For Deploy this Application 
First Create Instance 
![Screenshot 2025-02-14 195649](https://github.com/user-attachments/assets/26a4e2ca-c4f2-44c5-9e84-69f7b54f80be)
---------------------------------------------------------------------------------------------------
=> Then Add Security Group HTTP | HTTPS | SSH | MYSQL/AURORA | 5173 | 5000
![Screenshot 2025-02-14 195629](https://github.com/user-attachments/assets/7b75e661-1c0e-414c-9c6d-5cf145f95eed)
------------------------------------------------------------------------------------------------
=> Connect the Instance Using SSH Or to AWS EC2 Connect

- sudo apt update
- sudo apt install mysql-server -y
- sudo systemctl start mysql
- sudo systemctl enable mysql
- git clone
- ls
- cd digitalflake-admin-panel/
- ls
- cd DATABASE/
- ls
- sudo mysql -u root -p
       - Show Databases;
![Screenshot 2025-02-14 170730](https://github.com/user-attachments/assets/4cdd33bf-73a1-4970-9646-2245b21682e4)
- mysql -u root -p digiflake_admin < ~/digitalflake-admin-panel/DATABASE/my_crud_app.sql
-  sudo mysql -u root -p
      - REATE DATABASE digiflake_admin;
      - Show databases;
      - UES digiflake_admin;
      - Show tables;
      - Select * from User;
      - CREATE USER 'root'@'%' IDENTIFIED BY 'Admin';
      - GRANT ALL PRIVILEGES ON digiflake_admin. * TO 'root'@'%';
      - FLUSH PRIVILEGES;
      - EXIT;

![Screenshot 2025-02-14 171300](https://github.com/user-attachments/assets/07f72cea-bf59-4105-b646-f8c20f1d3752)
![Screenshot 2025-02-14 171423](https://github.com/user-attachments/assets/f7ae6213-14c9-4896-8ffd-d0e559ef778a)
![Screenshot 2025-02-14 171952](https://github.com/user-attachments/assets/f43ee099-b5fb-4715-a5c8-68d6310c0916)
------------------------------------------------------------------------------------------------
- cd ../
- cd server
- ls
- sudo install node
- sudo apt install -y nodejs npm
- node -v
- npm -v
- npm i
- ls
- nano config.js
    - import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    host: '0.0.0.0',  // Allows external access (your EC2 public IP)
    port: 5173,       // Ensures the app runs on port 5173
    strictPort: true, // Ensures the app doesn't switch ports
  }
})
- rm -rf node_modules package-lock.json
- npm cache clean --force
- npm install
- npm install bcrypt
- mysql -u root -p
    - SELECT user , host, plugin FROM mysql.user;
    - ALTER USER 'root'@'loalhost' IDFNTIFIED WITH mysql_native_password BY 'Admin';
    - FLUSH PRIVILEGES;
    - ![Screenshot 2025-02-14 171952](https://github.com/user-attachments/assets/4ae393e3-331d-49fd-a58b-53375b7eee8d)
- nano config.js
- node index.js
- mysql -u root -p
  - ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Admin';
  - FLUSH PRIVILEGES;
  - EXIT;
  - ![Screenshot 2025-02-14 180239](https://github.com/user-attachments/assets/7de0732f-9e1a-4c90-819f-5aee80b6460b)

- node index.js;
- cd ../
- npm install -g pm2
- pm2 start index.js --name digitalflake-server
- cd server/
- pm2 start index.js --name digitalflake-server
- pm2 save
- pm2 startup
- pm2 save
- pm2 list
- cd ../
- cd client/
- ls
- npm i
- npm run dev
    {run this localhost address and with replace with our Public ip address}
    ![Screenshot 2025-02-14 195425](https://github.com/user-attachments/assets/6ca9cf04-1695-48c0-b82a-560cf462121c)

- npm run build
- ls
- npm run dev
- npm start
- ls
- sudo apt install nginx
- nano vite.config.js 
- npm run dev -- --host
- cd ../
- cd server/
- cd src 
- cd ../
- npm install -g pm2
- pm2 start index.js --name digitalflake-server
- cd server/
- pm2 start index.js --name digitalflake-server
- pm2 save
- pm2 startup
- pm2 save
- pm2 list
- cd ../
- cd client/
- ls
- npm i
- npm run dev
- npm run build
- ls
- npm run dev
- npm start
- ls
- sudo apt install nginx
- nano vite.config.js 
- npm run dev -- --host
- cd ../
- cd server/
- cd src
- cd components/
- ls
- nano Login.jsx
- node index.js
- pm2 list
- pm2 restart 0
- cd ..
- cd client/
- npm run dev
- cd src
- cd components/
- ls
- nano Signup.jsx
- nano Category/
- nano Category.jsx
- cd Category/
- ls
- nano Category.jsx
- cd ..
- cd SubCategory/
- ls
- nano SubCategory.jsx
- npm run dev
- cd ..
- ls
- nano Signup.jsx
- npm run dev
![Screenshot 2025-02-14 195451](https://github.com/user-attachments/assets/e19079cd-d8bb-4224-9010-4164fbbd099c)
![Screenshot 2025-02-14 195510](https://github.com/user-attachments/assets/594b0c38-6563-47b8-9603-dc1f513c594a)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
NOTE : {Replace All the localhost address with our Public ip in Singup.jsx , Category.jsx , 
        SubCategory.jsx all this pages}
-----------------------------------------------------------------------------------------------
 - Output :
 - ![Screenshot 2025-02-14 195402](https://github.com/user-attachments/assets/8783cd57-c101-401d-a07f-c26d74e9daf0)
 - ![Screenshot 2025-02-14 194933](https://github.com/user-attachments/assets/9e8491e9-082e-409b-a3fb-500a659337fe)
 - ![Screenshot 2025-02-14 194953](https://github.com/user-attachments/assets/4111f7f2-e59c-4f6d-bb3a-dbf863c53cfc)
- ![Screenshot 2025-02-14 195007](https://github.com/user-attachments/assets/52b135bb-77fd-42dd-bdf6-00ae9d96eb93)
- ![Screenshot 2025-02-14 195152](https://github.com/user-attachments/assets/54fca996-168d-4a17-9428-1e7f0caba28e)
- ![Screenshot 2025-02-14 195239](https://github.com/user-attachments/assets/494d6046-5554-41c0-91f0-d10935538486)
- ![Screenshot 2025-02-14 195257](https://github.com/user-attachments/assets/c002fc48-54a9-4609-8e2c-85919b76d6f4)
- ![Screenshot 2025-02-14 195317](https://github.com/user-attachments/assets/46023028-d5d0-42d8-9d55-f2e90a69cca8)


	
