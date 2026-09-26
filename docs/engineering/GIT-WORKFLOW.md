# Git Workflow

Branches:
- main
- develop
- feature/*
- fix/*

Typical flow:

develop -> feature -> pull request -> review -> develop

Release:

develop -> main

Commit prefixes:
feat:
fix:
test:
docs:
refactor:
chore:

Do not commit:
- .env.local
- secrets
- service keys
- production data
- personal receipt files
