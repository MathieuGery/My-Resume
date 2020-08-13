# My-Resume
My resume web site volume backup docker

#Create backuo
docker run --rm --volumes-from octobercms_october_1 -v ~/backup:/backup ubuntu bash -c "cd /var/www/html && tar cvf /backup/backup.tar ."

#Restore backup
docker run --rm -v my-resume_october-volume:/recover -v ~/Documents/nosync.nosync/My-Resume/backup/:/backup ubuntu bash -c “cd /recover && tar xvf /backup/backup.tar”
