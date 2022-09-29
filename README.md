<div align="center">
  <img align="center" alt="Coding gif"  style="border-radius:300px;" src="https://preview.redd.it/mw4y58i658981.gif?width=750&auto=webp&s=d1f8893494ed1d8e9f731f4b7e7915ca7e4039dc">
</div>

<h2 align="center">Olá eu sou o Fares! <br> Sou um desenvolvedor FrontEnd.</h2>

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

- uses: Platane/snk@v2
  with:
    # github user name to read the contribution graph from (**required**)
    # using action context var `github.repository_owner` or specified user
    github_user_name: ${{ github.repository_owner }}

    # list of files to generate.
    # one file per line. Each output can be customized with options as query string.
    #
    #  supported options:
    #  - palette:     A preset of color, one of [github, github-dark, github-light]
    #  - color_snake: Color of the snake
    #  - color_dots:  Coma separated list of dots color.
    #                 The first one is 0 contribution, then it goes from the low contribution to the highest.
    #                 Exactly 5 colors are expected.
    outputs: |
      dist/github-snake.svg
      dist/github-snake-dark.svg?palette=github-dark
      dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
