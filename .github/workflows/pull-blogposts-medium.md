name: Pull blogposts from medium
on:
  schedule:
    - cron: '0 * * * *'
  push:
    branches: [ main ]
jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts from medium
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          max_post_count: "5" 
          feed_list: "https://medium.com/feed/@soumendra"