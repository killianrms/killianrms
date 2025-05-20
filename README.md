### Salut, Je suis Killianrms 👋

- 🔭 Je travaille actuellement sur un [Système de référendum](https://github.com/killianrms/referendum) en java pour l'université et un [Bot de trading](https://github.com/killianrms/prototype_trader_bot) en python pour un projet perso
- 📍 Étudiant à l'IUT de Montpellier-Sète
- 💼 [Portfolio](https://killianrms.com) - [Cv](https://killianrms.com/cv.pdf)

### Mes compétences :

#### Languages:
<p align="left">
  <img align="center" src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img align="center" src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java" />
  <img align="center" src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML" />
  <img align="center" src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="C" />
  <img align="center" src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP" />
  <img align="center" src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL" />
</p>

#### OS:
<p align="left">
  <img align="center" src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows" />
  <img align="center" src="https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white" alt="iOS" />
  <img align="center" src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android" />
  <img align="center" src="https://img.shields.io/badge/Linux-A81D33?style=for-the-badge&logo=Linux&logoColor=white" alt="Linux" />
</p>

#### Logiciels:
<p align="left">
  <img align="center" src="https://img.shields.io/badge/Google-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Google" />
  <img align="center" src="https://img.shields.io/badge/JetBrains-000000?style=for-the-badge&logo=jetbrains&logoColor=white" alt="JetBrains" />
  <img align="center" src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img align="center" src="https://img.shields.io/badge/phpMyAdmin-6C78AF?style=for-the-badge&logo=phpmyadmin&logoColor=white" alt="phpMyAdmin" />
</p>

#### Travail d'équipe:
<p align="left">
  <img align="center" src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  <img align="center" src="https://img.shields.io/badge/GitLab-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white" alt="GitLab" />
</p>

#### Contacts :
contact@killianrms.com

### Snake Animation

To use this, the user needs to create a repository named `killianrms` and add the GitHub Action workflow file to the `.github/workflows` directory. The workflow file should contain the following:

```yaml
name: Generate GitHub Contribution Snake

on:
  schedule:
    - cron: "0 0 * * *"  # Runs daily at midnight UTC
  workflow_dispatch:  # Manual trigger
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
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
