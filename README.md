# Rapid Reproducible Environment


```shell
vagrant up && vagrant ssh -c "cd /vagrant && docker-compose build && docker-compose up"
```

This will run:
- a vagrant machine...
  - with a docker-compose container group...
    - with a nodejs container...
      - with a server on http://localhost:8000
        - with live-compiling
          - [jade](http://jade-lang.com/)
          - [stylus](http://learnboost.github.io/stylus/)
          - [coffeescript](http://coffeescript.org/)

You can use it as a starting point to add other machines to create more complex
systems.
