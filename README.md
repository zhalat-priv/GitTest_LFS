# gitTest_LFS

LFS repleaces large files such as media,audio,etc with text pointers.
It speeds up a work with repository.
1. Download and install extension: git-lfs-linux-amd64-xxx.tar.gz
	https://git-lfs.github.com/
	or
	```
	curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
	sudo apt-get install git-lfs
	```
2. Go to your repo where you want to use LFS
	```
	git lfs install
	```
3. Create a file .gitattributes and put there folder which should be filtered with lfs
	```
	StorageForLargeFiles/* filter=lfs diff=lfs merge=lfs -text
	```
	or
	```
	git lfs track "*.jpg"
	```
	for jpg files
	
4. Checking which files are tracking
	```
	GitTest_LFS/StorageForLargeFiles$ git lfs ls-files
	15dd0b92bb - StorageForLargeFiles/foto.jpeg
	8decc85719 - StorageForLargeFiles/sample.pdf
	```
	or by file attributes:
	```
	GitTest_LFS/StorageForLargeFiles$ git check-attr --all foto.jpeg
	foto.jpeg: diff: lfs
	foto.jpeg: merge: lfs
	foto.jpeg: text: unset
	foto.jpeg: filter: lfs
	```
5. Note that all developers shall have Git LFS installed.
6. More: https://mydeveloperplanet.com/2018/10/31/git-lfs-why-and-how-to-use/
