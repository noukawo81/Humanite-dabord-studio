# Humanite-dabord-studio
Mini-Studio IA pour Humanité d’Abord : créer facilement des messages, images, vocaux et vidéos inspirants pour promouvoir la paix et la solidarité dans le monde.
import shutil import os

Chemin où on crée le projet

project_path = '/mnt/data/humanite-dabord-studio' os.makedirs(project_path, exist_ok=True)

Création structure de base React + Tailwind

os.makedirs(f'{project_path}/src', exist_ok=True) os.makedirs(f'{project_path}/public', exist_ok=True)

Fichier App.jsx avec code du mini-studio

app_code = '''import React, { useState } from "react";

export default function App() { const [message, setMessage] = useState(""); const [generatedContent, setGeneratedContent] = useState("");

const generateMessage = () => { setGeneratedContent(🌍 Humanité d'Abord : ${message}); };

return ( <div className="min-h-screen bg-gradient-to-b from-purple-900 to-indigo-900 text-white flex flex-col items-center justify-center p-8"> <h1 className="text-4xl font-bold mb-6">🌍 Humanité d’Abord - Mini Studio IA</h1> <textarea placeholder="Écris ton message de paix ici..." value={message} onChange={(e) => setMessage(e.target.value)} className="w-full max-w-lg p-4 rounded-2xl text-black mb-4" rows="5" /> <button
onClick={generateMessage}
className="bg-yellow-500 hover:bg-yellow-600 px-6 py-3 rounded-full font-bold"
> Générer le message </button> {generatedContent && ( <div className="mt-6 bg-white text-black p-6 rounded-2xl shadow-lg max-w-lg text-center"> <h2 className="text-2xl font-bold mb-2">✨ Message généré</h2> <p>{generatedContent}</p> </div> )} </div> ); }'''

with open(f'{project_path}/src/App.jsx', 'w') as f: f.write(app_code)

Créer package.json basique

package_json = '''{ "name": "humanite-dabord-studio", "version": "1.0.0", "private": true, "dependencies": { "react": "^18.0.0", "react-dom": "^18.0.0", "react-scripts": "5.0.1", "tailwindcss": "^3.3.3" }, "scripts": { "start": "react-scripts start", "build": "react-scripts build" } }'''

with open(f'{project_path}/package.json', 'w') as f: f.write(package_json)

Créer tailwind.config.js basique

tailwind_config = '''/** @type {import('tailwindcss').Config} / module.exports = { content: ["./src/**/.{js,jsx,ts,tsx}"], theme: { extend: {} }, plugins: [], }''' with open(f'{project_path}/tailwind.config.js', 'w') as f: f.write(tailwind_config)

Zip le projet

shutil.make_archive('/mnt/data/humanite-dabord-studio', 'zip', project_path)

'/mnt/data/humanite-dabord-studio.zip'

