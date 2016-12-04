- rails new HowlrWorkflowDemo -d postgresql

- new repo in github

- git init, git add ., git commit -m "initial commit"
  -check that its working

- make some issues
 - 1 - workflow setup
       -[ ] Heroku deployment
       -[ ] guard
       -[ ] .env
       -[ ] CodeClimate
       -[ ] Test coverage
       -[ ] Travis CI(Continuous Integration)
       -[ ] First batch of user stories
       -[ ] Waffle
       -[ ] Main Interceptor
       -[ ] Mail serve (Sendagrid or equivilent)

### Heroku deployment
  - heroku create
  - git push heroku master
  - heroku open (standard starting page)

### waffle

### .env

  - gem 'dotenv-rails'
    - (google and find in case its changes)
	- run all rakes
	- gco -b dotenv (if works merge right into master without making a feature branch)
	- add dotenv gem to Gemfile
	- bundle
	- rails console
		- see if env is working
	(this step of testing didnt work for AE and he moved on)
	- subl .gitignore
		- add .env
	- merge into master

### Code Climate
	-you can add code climate to your project in the readme so the score is always in the readme and then the pull requests etc will be scored
		-require also in test helper

### Travis
	- travis.yml: 
			language: ruby
			rvm:
				- 2.2.3
			install:
				- bundle install
			before_script:
				- psql -c 'create database workout_tracker_test;' -U postgres
			services:
				- postgresql
			addons:
  			code_climate:
    		repo_token: 41fa32a2349c6b5b761e191fd5b095313ad732cceff5d6c9240e1fd522de79ba
			deploy:
			  provider: heroku
			  app: ae-workout-tracker
			  run: "rake db:migrate"
			  api_key:
			    secure: PUm+7/3nuvx2vTwgo4k5GeUy5bbT+/7Y78z/2qa1BpBR+PJ3gjmcGP30x4rmaNftv9verGFm+/lA4zAJbTyrNO/jR1VyUBMxRfQ1Q4242cEIue0tVG9N65JDM4kMlX4c1X3EVr22lZWQS7g05nnXPIGNIQJlvb2+fv0ObWN8n6jDgKFaGSrTXG2Xu1YUjE5qSS4R1DMMgKJ8EzGYt+XEI+sWyGKLRZC2yfWi1JZFdvLaj5DI4puSZAswBmrnpXADul8wI0z+OYp54nxvvsYRSBgD50OtApax8Bd7TAk8MnRhOUUsyqQGFK0Ha9qIU5k2tS9M8++zWHImw9t7bjLaboyQm1o5wMaSF6wExcuESL99T6HHSc4N89F65jRJ6+RSxFAPOhozkV4BHWmwn8GeWzZtaRETlTC+0eQiUp7e3KAMAoPGFqChkWgwqtEZVbpSWd3QVWVER9NuXfiO5uRUnOuUl8hWoUCpUn9BjXawBDGXRcI0jN+Rprj7Enyf3sfPOq3OUZ1u6K6LYYKcnn90fMk15CPa4yfBe50VFBmbByZBWpuilmvT6oJkZ/1Y8n/m97BMwEBB8KEZnyAitr42jitcA75TrbKYPJmOgeF5I+4YqAJadV77LsIFIbxnqkaH2LP6ZSNG+1cgnA9+nTinPw1DnaIZhDHz+lrrDxhdoo8=
			Status API Training Shop Blog About
	- google travis heroky deploy to rails
	Will only push to heroku from the master branch
	(https://docs.travis-ci.com/user/deployment/heroku/)
		- deploy:
  			provider: heroku
  			api_key:
    			secure: "YOUR ENCRYPTED API KEY"
   - in commit line travis encrypt $(heroku auth:token) --add deploy.api_key


### Guard
	- google guard to find how to install
		- install guard gem
		- install guard minitest
		- instal guard terminal notifier
		- bundle exec guard

## Make Milestone (bundles of issues)


## Evaluate your issues and pick one to start on, ex "Users can register for Howlr"
	- add scorcery!
	