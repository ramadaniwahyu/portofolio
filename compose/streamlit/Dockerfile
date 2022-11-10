# base image
FROM python:3.9

# streamlit-specific commands
RUN mkdir -p /root/.streamlit
RUN bash -c 'echo -e "\
[general]\n\
email = \"\"\n\
" > /root/.streamlit/credentials.toml'
RUN bash -c 'echo -e "\
[server]\n\
enableCORS = false\n\
" > /root/.streamlit/config.toml'

# copy over and install packages
COPY ./app/req.txt ./req.txt
RUN pip install cython
RUN pip install -r req.txt

# copying everything over
COPY . .