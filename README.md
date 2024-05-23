# UoM_DMS_Toolkit

### 😁 an IDEA by PATRIC NILACKSHAN

<br>

## Introduction
UoM_DMS_Toolkit streamlines file tasks for students, faculty, and staff at UoM. Enjoy data-free downloads/uploads and multimedia processing, including M3U8 to MP4 conversion. Say goodbye to bandwidth worries and focus on your education!

<br>
<br>

## Prerequisites
### Ensure the following prerequisites are met before using the CLI codes:

- Update package lists:

`
sudo apt update -y
`

- Install ffmpeg for multimedia processing:

`
sudo apt install ffmpeg -y
`

<br>
<br>

## Usage
### Mapping DMS WebDAV Share
`
net use Z: https://dms.uom.lk/remote.php/webdav/ /user:userName userPassword
`

<br>

### Download files from URLs using either wget or curl:
`
wget -O FileName downloadLink
`
<br>
or
<br>
`
curl -o FileName downloadLink
`

<br>

### Download M3U8 files and convert them to MP4 using ffmpeg
#### Optional ( If you want to download from a .m3u8 link )
`
ffmpeg -i https://example.com/video.m3u8 -c copy -threads 8 output.mp4
`

<br>

### Uploading Files to DMS
`
curl -u userName:userPassword -T "FileName" "https://dms.uom.lk/remote.php/webdav/"
`

<br>

### Share a file or folder from the DMS using Nextcloud API:

`
curl -u userName:userPassword -X POST -d "path=Movie.mp4&shareType=3&permissions=1" "https://dms.uom.lk/ocs/v2.php/apps/files_sharing/api/v1/shares?format=xml" -H "OCS-APIRequest: true"
`

<br>

### Get details of all shares:
`
curl -u userName:userPassword -X GET "https://dms.uom.lk/ocs/v2.php/apps/files_sharing/api/v1/shares" -H "OCS-APIRequest: true"
`

<br>

### Delete a share with its share_id:
`
curl -u userName:userPassword -X DELETE "https://dms.uom.lk/ocs/v2.php/apps/files_sharing/api/v1/shares/<share_id>" -H "OCS-APIRequest: true"
`

<br>

## Conclusion
These CLI codes provide a convenient way to interact with the DMS for educational purposes, enabling data-free downloads, uploads, and sharing of files and folders.

<br>

# &#169; PATRIC NILACKSHAN
