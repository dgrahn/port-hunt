![Banner](https://raw.githubusercontent.com/dgrahn/port-hunt/main/banner.png)

# port-hunt
![GitHub last commit](https://img.shields.io/github/last-commit/dgrahn/homelab-services?style=flat-square)
![Github issues](https://img.shields.io/github/issues-raw/dgrahn/homelab-services?style=flat-square)
![Github pull requests](https://img.shields.io/github/issues-pr/dgrahn/homelab-services?style=flat-square)
![License](https://img.shields.io/github/license/dgrahn/homelab-services)
![Follow Me](https://img.shields.io/twitter/follow/realDanGrahn?style=flat-square)

A simple hide-and-seek game for port scanning practice.

# Table of contents
- [Table of contents](#table-of-contents)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)
- [Footer](#footer)


# Installation
[(Back to top)](#table-of-contents)

1. **Clone:**
    `git clone git@github.com:dgrahn/port-hunt.git`

2. **Run:**
    `docker-compose up`

# Usage
[(Back to top)](#table-of-contents)

This hosts nginx servers on various ports. Each port contains an HTML file that
serves an image that students can "collect". This doesn't have any security
hardening, so don't run it on a public server.


To add an extra port, add these lines to the docker-compose.  You will need to
customize it in threes locations.

```
  nginx[port]:
    image: nginx
    volumes:
      - ./src/[port]:/usr/share/nginx/html:ro
    ports:
    - "[port]:80"
```

After that, add your files to `src/[port]` and restart the docker-compose.

# License
[(Back to top)](#table-of-contents)

[MIT License](https://choosealicense.com/licenses/mit/)


# Footer
[(Back to top)](#table-of-contents)

Like this? Star it. :)

<!-- ![Footer](https://github.com/navendu-pottekkat/awesome-readme/blob/master/fooooooter.png) -->
