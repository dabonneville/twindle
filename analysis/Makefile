
lists:
	python lists.py SPIEGEL_Daten/Politikertreppe
	python lists.py zeitonline_pol/bundestagsabgeordnete

reports:
	datafreeze --db $(shell echo "$(DB_URL)" | sed 's/tcp:/postgresql:/g') Freezefile.yaml

dumpraw:
	mkdir -p dumps
	python dumpraw.py
	s3cmd put --rr --guess-mime-type dumps/* s3://json.twindle.pudo.org/tweets/ && rm -f dumps/*

