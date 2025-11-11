### ffmpeg 설치
```
docker exec -it --user root yojulab_learn_n8ns-app_n8n-1 apk add --no-cache ffmpeg imagemagick ghostscript
```

### 디렉터리 생성 및 폴더초기화 명령어
```
mkdir -p  {{ $json.resource_dir }} &&
cd {{ $json.resource_dir }} &&
rm -f *
```

### Read/Write Files from Disk 에서 파일 생성 명령어
```
{{ $('Edit Fields').item.json.resource_dir }}out.pcm
```

### 이미지+소리 합성 명령어 예시
```
ffmpeg -loop 1 -i out.png -f s16le -ar 24000 -ac 1 -i out.pcm -c:v libx264 -c:a aac -pix_fmt yuv420p -shortest out.mp4
```
```
//n8n에서 실행할때는 해당 폴더위치 지정

cd {{ $('Edit Fields').item.json.resource_dir }} &&
ffmpeg -loop 1 -i out.png -f s16le -ar 24000 -ac 1 -i out.pcm -c:v libx264 -c:a aac -pix_fmt yuv420p -shortest out.mp4

```

### concat과 list.txt를 활용한 video 결합
```
ffmpeg -f concat -safe 0 -i videos_list.txt -c copy final_video.mp4
```

### linux에서 파일 삭제와 생성, 내용 추가
```
~/resources $ rm -f videos_list.txt
~/resources $ rm -f final_video.mp4
~/resources $ cat videos_list.txt
cat: can't open 'videos_list.txt': No such file or directory
~/resources $ touch videos_list.txt
~/resources $ echo "output_11.mp4 hello!"
output_11.mp4 hello!
~/resources $ echo "output_11.mp4 hello!" >>  videos_list.txt
~/resources $ echo "output_12.mp4 hello!" >>  videos_list.txt
~/resources $ echo "output_13.mp4 hello!" >>  videos_list.txt
~/resources $ echo "file output_11.mp4" >>  videos_list.txt
~/resources $ echo "file output_12.mp4" >>  videos_list.txt
~/resources $ echo "file output_13.mp4" >>  videos_list.txt
```