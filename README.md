### scikit-learn image based on alpine
Docker image with python3.6, numpy, scikit, ipython, jupyter.

### print python version
$ docker run -it --rm -v $(pwd):/code -p 8000:8000 tallesman/scikit-learn python --version
Python 3.6.5

### run built-in python cgi server (.py files in cgi-bin or htbin dir)
$ docker run -it --rm -v $(pwd):/code -p 8000:8000 tallesman/scikit-learn built-in cgi
Serving HTTP on 0.0.0.0 port 8000 ...
172.17.0.1 - - [27/Nov/2016 02:53:20] "GET /cgi-bin/test.py HTTP/1.1" 200 -

### run Jupyter Notebook container (see token in log)
docker run  -p 8888:8888 -v $(pwd):/code  -d tallesman/scikit-learn

### Or use PASSWORD environment variable instead of token
docker run  -p 8888:8888 -v $(pwd):/code -e PASSWORD=yoursecretpass -d tallesman/scikit-learn

### open browser
open http://$(docker-machine ip default):8888