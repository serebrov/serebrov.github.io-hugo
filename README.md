[Development notes serebrov.github.io](http://serebrov.github.io)

Building:

- Add new post / change content
- git add, git commit
- Run `./deploy.sh`

# How it Works

Content is under [./content/posts](./content/posts) folder.

Hugo builds the content and puts results into the [./public](./public) folder which is a submodule, pointing to another repository, [serebrov.github.io](https://github.com/serebrov/serebrov.github.io).
That other repository is hosted and served via [Git pages](https://pages.github.com/).
