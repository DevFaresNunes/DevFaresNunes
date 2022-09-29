<div align="center">
  <img align="center" alt="Coding gif"  style="border-radius:300px;" src="https://preview.redd.it/mw4y58i658981.gif?width=750&auto=webp&s=d1f8893494ed1d8e9f731f4b7e7915ca7e4039dc">
</div>

<h2 align="center">Hi, I'm Fares Nunes! A Front End Developer from Brazil</h2>

<p align="center" style="background:blue">
  <a href="https://www.linkedin.com/in/fares-nunes-281b1a240/" target="_blank">
    <img align="center" src="https://img.shields.io/badge/-Fares%20Nunes-blue?style=flat-square&logo=Linkedin&logoColor=white" alt="linkedin"/>
  </a>
  <a href="mailto:faresnunes.dev@gmail.com">
    <img align="center" src="https://img.shields.io/badge/-faresnunes.dev-blue?style=flat-square&logo=Gmail&logoColor=white" alt="gmail"/>
  </a>
</p>

<br />


<div align="center" style="display: inline_block">
  <img align="center" alt="JavaScript" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="TypeScript" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-plain.svg">
  <img align="center" alt="React" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg">
  <img align="center" alt="HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
</div>

name: generate animation

on:
  # run automatically every 12 hours
  schedule:
    - cron: "0 */12 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
