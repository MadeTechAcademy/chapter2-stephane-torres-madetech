# Measure the impact!

Commit your data here

Original build file listing:
/my-app
├── .dockerignore
├── Gemfile
├── Gemfile.lock
├── Rakefile
├── app
│   ├── .env
│   └── .ruby-version
├── entrypoint.sh
└── tests
    ├── out
    │   └── first_test_log.txt
    └── test_something.rb




Better build file listing:

/my-app
├── .dockerignore
├── Gemfile
├── Gemfile.lock
├── Rakefile
├── app
│   └── .ruby-version
├── entrypoint.sh
└── tests
    ├── out
    │   └── first_test_log.txt
    └── test_something.rb


Reworked:
/my-app
├── Gemfile
├── Gemfile.lock
├── Rakefile
├── app
│   └── .ruby-version
└── entrypoint.sh

2 directories, 5 files
Well done Steph!





