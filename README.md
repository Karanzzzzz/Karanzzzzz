<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=30&pause=1200&color=00C6FF&center=true&vCenter=true&width=600&height=60&lines=Karan+Deep+Raj;C%2B%2B+%C2%B7+Python+%C2%B7+JavaScript;BCA+Student+%7C+Building+in+Public" />

<sub>Software developer · problem solver · always shipping something small</sub>

<br/><br/>

<!-- LIVE ANIMATED 3D CONTRIBUTION GRAPH — needs one-time setup, see notes below -->
<img src="https://raw.githubusercontent.com/Karanzzzzz/Karanzzzzz/main/profile-3d-contrib/profile-blue-animate.svg" width="100%"/>

</div>

<br/>

<table align="center">
<tr>
<td width="50%" valign="top">

**Focus right now**

`Advanced C++` `Python` `DSA` `Web Dev`

**Open to**

Collaborating on open-source & beginner-friendly tools

</td>
<td width="50%" valign="top">

<img src="https://github-readme-stats.vercel.app/api?username=Karanzzzzz&show_icons=true&theme=tokyonight&hide_border=true" width="100%"/>

</td>
</tr>
</table>

<div align="center">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Karanzzzzz&theme=tokyonight&hide_border=true"/>

<br/>

<img src="https://skillicons.dev/icons?i=cpp,python,js,git,github,vscode&theme=dark"/>

<br/><br/>

<img src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif" width="450"/>

</div>

<br/>

<div align="center">

<a href="https://www.linkedin.com/in/karandeep-raj-085a65312"><img src="https://img.shields.io/badge/-LinkedIn-00C6FF?style=flat-square&logo=linkedin&logoColor=white"/></a>
<a href="mailto:karan.2431727@gmail.com"><img src="https://img.shields.io/badge/-Email-00C6FF?style=flat-square&logo=gmail&logoColor=white"/></a>
<a href="https://leetcode.com/u/karanzzzzz/"><img src="https://img.shields.io/badge/-LeetCode-00C6FF?style=flat-square&logo=leetcode&logoColor=white"/></a>
<a href="https://www.hackerrank.com/profile/24116002266_kara"><img src="https://img.shields.io/badge/-HackerRank-00C6FF?style=flat-square&logo=hackerrank&logoColor=white"/></a>

</div>

<br/>

<div align="center">
<sub>"The best way to predict the future is to invent it."</sub>
</div>

[
  {
    "type": "rainbow",
    "fileName": "profile-blue-animate.svg",
    "backgroundColor": "#0d1117",
    "foregroundColor": "#c9d1d9",
    "strongColor": "rgb(0,198,255)",
    "weakColor": "#30363d",
    "radarColor": "rgb(0,198,255)",
    "growingAnimation": true,
    "saturation": "70%",
    "contribLightness": ["18%", "30%", "40%", "55%", "70%"],
    "duration": "8s",
    "hueRatio": 0
  }
]
name: generate 3d chart for profile contributions

on:
  schedule:
    - cron: "0 */24 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v4
      - uses: yoshi389111/github-profile-3d-contrib@latest
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
          SETTING_JSON: profile-3d-settings.json
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          git commit -m "generate 3d contribution profile" || exit 0
          git push
