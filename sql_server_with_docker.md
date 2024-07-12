# How to Install in docker
 [LINK](https://hub.docker.com/r/microsoft/mssql-server)

## to restore bak file in docker

### Lihat isi variabel di dalam file bak 
	 docker exec -it {nama_container} /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'password' -Q 'RESTORE FILELISTONLY FROM DISK = "{nama_file}"' | tr -s ' ' | cut -d ' ' -f 1-2

### aksi mengembalikan 
	sudo docker exec -it {nama_container} /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'passwirdnya' -Q 'RESTORE DATABASE {nama_db} FROM DISK = "{lokasi_file}" WITH MOVE "{variabel_ndf}" TO "/var/opt/mssql/data/{nama_db}.ndf", MOVE "{variabel_log}" TO "/var/opt/mssql/data/{nama_db}_log.ldf", REPLACE'
