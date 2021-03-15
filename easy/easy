Bootstrap: docker
From: conda/miniconda3

%files
	./Next_trials_ITAINNOVA.zip /root

%post
	apt-get -y update && apt-get install -y unzip
	conda config --set auto_activate_base false
	conda update -n base -c defaults conda
	conda create -n tf_test tensorflow=2.2.0=gpu_py37h1a511ff_0
	conda init bash
	. ~/.bashrc
	conda activate tf_test
	pip install optuna keras scikit-learn pandas
	unzip /root/Next_trials_ITAINNOVA.zip -d /usr/local/
%runscript
	conda init bash
	. ~/.bashrc
	conda activate tf_test
	python /usr/local/Next_trials/Codigo/easy.py

