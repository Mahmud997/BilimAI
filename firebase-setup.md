# Firebase setup for BilimAI Pro MAX

## 1. Firebase project

Создайте проект в Firebase Console и зарегистрируйте Web App.

Включите:
- Authentication → Google
- Firestore Database

## 2. Authorized domain

Добавьте домен GitHub Pages вашего проекта в Authentication → Settings → Authorized domains.

## 3. index.html

Найдите:

const firebaseConfig={
  apiKey:"YOUR_FIREBASE_API_KEY",
  authDomain:"YOUR_PROJECT.firebaseapp.com",
  projectId:"YOUR_PROJECT",
  storageBucket:"YOUR_PROJECT.appspot.com",
  messagingSenderId:"YOUR_SENDER_ID",
  appId:"YOUR_APP_ID"
};

Замените значения на конфигурацию Web App из Firebase.

## 4. Firestore

Используйте `firestore.rules` из этого проекта как стартовую основу. Перед production проверьте правила под ваши роли и структуру организации.

## 5. AI

Для реального production не вызывайте OpenAI/DeepSeek/Gemini с секретным ключом напрямую из публичного GitHub Pages. Создайте HTTPS endpoint через Firebase Cloud Functions или другой серверный backend и перенесите секрет туда.
