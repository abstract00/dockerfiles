FROM ubuntu:20.04

RUN apt-get update && \
	apt-get install -y \
		wget \
		unzip \
		python3 \
		python3-pip

RUN pip3 install -U pip && \
	pip3 install \
		jupyterlab \
		matplotlib \
		pandas \
		pandas-datareader \
		scikit-learn \
		scipy \
		seaborn \
		xlrd

RUN wget https://moji.or.jp/wp-content/ipafont/IPAexfont/ipaexg00401.zip && \
	unzip /ipaexg00401.zip && \
	rm -r -f /ipaexg00401.zip && \
	mv /ipaexg00401/ipaexg.ttf \
		/usr/local/lib/python3.8/dist-packages/matplotlib/mpl-data/fonts/ttf/ && \
	rm -r -f /ipaexg00401

WORKDIR /project

CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--LabApp.token=''"]

