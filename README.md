A downstream version of
[restic/restic](https://hub.docker.com/r/restic/restic/) that adds
bandwith control.

Set environment variable BANDWITH_LIMIT to a limit suitable for `qc`
and the container will be limited to that bandwith.  Your container
must have NET_ADMIN priviledges to work.

Example:
    
     docker run --rm -e BANDWIDTH_LIMIT=2000Mbits -e AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID} -e AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}  -e RESTIC_PASSWORD=${PASSWORD} -h ${hostname} --cap-add NET_ADMIN -v ${DIR}:${DIR} deweysasser/restic -r s3:s3.amazonaws.com/${BUCKET}/restic backup ${DIR}
