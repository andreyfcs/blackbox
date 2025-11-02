1. Navegue até a pasta do seu Next.js:

cd ~/Documents/Projetos\ Github/pdv-next

2. Instale o Electron como dependência de desenvolvimento:

npm install --save-dev electron
npm install --save-dev electron-builder

3. Crie a pasta para os arquivos do Electron:

/electron

4. Dentro dela, crie um arquivo main.js:

const { app, BrowserWindow } = require('electron');
const path = require('path');

function createWindow() {
  const win = new BrowserWindow({
    width: 1200,
    height: 800,
    webPreferences: {
      nodeIntegration: true,
      contextIsolation: false
    }
  });

  // Para desenvolvimento: Next.js rodando em dev server
  win.loadURL('http://localhost:3000'); 
}

app.on('ready', createWindow);

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') app.quit();
});

app.on('activate', () => {
  if (BrowserWindow.getAllWindows().length === 0) createWindow();
});

- Observação: loadURL aponta para o Next.js em modo dev. Quando fizer build, você vai mudar para os arquivos estáticos.

- Passo 2: Ajustar package.json

"main": "electron/main.js",
"scripts": {
  "dev": "next dev",
  "build": "next build && next export",
  "start": "next start",
  "electron": "electron .",
  "dist": "electron-builder"
}

E a seção do build para empacotar:

"build": {
  "appId": "com.pdvnext.desktop",
  "productName": "PDVNext",
  "files": [
    "electron/**/*",
    ".next/**/*",
    "package.json"
  ],
  "directories": {
    "buildResources": "assets"
  },
  "win": {
    "target": "nsis"
  },
  "linux": {
    "target": "AppImage"
  },
  "mac": {
    "target": "dmg"
  }
}

- Passo 3:

Inicie o Next.js em modo dev:
npm run dev

Em outro terminal, abra o Electron:
npm run electron