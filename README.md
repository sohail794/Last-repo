# Last-repo
Last one
import os
from github import Github

Get GitHub token from environment variable
token = os.getenv('GITHUB_TOKEN')

Create a GitHub instance
g = Github(token)

Get the issue or pull request comment
comment_body = os.getenv('COMMENT_BODY')

Your chatbot logic here
if 'hello' in comment_body.lower():
response = "Hello! 🌟 Thanks for reaching out."

Post a comment with the chatbot response
repo = g.get_repo(os.getenv('GITHUB_REPOSITORY'))
issue = repo.get_issue(int(os.getenv('ISSUE_NUMBER')))
issue.create_comment(response)
name: Chatbot

on:
issue_comment:
types:
- created

jobs:
chatbot:
runs-on: ubuntu-latest

steps:
- name: Checkout code
  uses: actions/checkout@v2
git add constitution_tea.yaml
git commit -m "Add constitution file"
git push origin master
