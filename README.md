# Restaurant-information-system-server
name: Update gist with WakaTime stats
on:
  push:
    branches:
      - master
  schedule:
    - cron: "0 0 * * *"
jobs:
  update-gist:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: Update gist
        uses: matchai/waka-box@master
        env:
          GH_TOKEN: ${{ secrets.GH_TOKEN }}
          GIST_ID: ${{ secrets.GIST_ID }}
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          TIMEZONE: Asia/Seoul
