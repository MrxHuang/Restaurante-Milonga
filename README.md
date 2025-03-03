## 🍽️ Que se dice? - Gestión de Pedidos e Inventario

Bienvenido a **Que se dice?**, un sistema de gestión de pedidos e inventario para restaurantes. Este proyecto facilita la administración de órdenes, seguimiento de inventario y optimización de procesos dentro de un restaurante.

---

### 🚀 Tecnologías Utilizadas

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" alt="HTML5" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" alt="CSS3" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="JavaScript" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="40" alt="Python" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flask/flask-original.svg" height="40" alt="Flask" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-plain.svg" height="40" alt="Tailwind CSS" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg" height="40" alt="SQLite" />
</div>

---

### 📌 Funcionalidades Principales
✅ Gestión de pedidos en tiempo real 📦🍕  
✅ Control y actualización de inventario 📊  
✅ Interfaz moderna y responsiva con **Tailwind CSS** 🎨  
✅ Backend en **Flask** con base de datos **SQLite** 🔥  
✅ Dashboard interactivo para seguimiento de ventas y productos 📈  

---

### 🤖 Sobre mí
✨ Creando bugs desde 2004-2006
📚 Actualmente aprendiendo más sobre desarrollo web full-stack  
🎯 Objetivo: Optimizar la gestión de restaurantes con tecnología  
🎲 Dato curioso: Amo la comida tanto como el código 🍔💻  

---

###

<br clear="both">

<img src="https://raw.githubusercontent.com/maurodesouza/maurodesouza/output/snake.svg" alt="Snake animation" />

###
name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
