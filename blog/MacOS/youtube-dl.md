# youtube-dl for macOS #

작성 날짜 : 2019. 06. 28

유튜브를 보다보면 소장하고 싶은 영상이나 노래가 있다.
이 때 다운로드할 수 있는 다양한 방법이 있지만, 개인적으로 가장 간단하게 보이는 방법은 `youtube-dl`처럼 보이더라.
사용법을 간단하게 정리해 놓는다.
개발자 깃헙 사이트는 아래와 같다.

  * URL : https://github.com/ytdl-org/youtube-dl

## `youtube-dl` 다운로드 ##

터미널에서 다음 명령어를 입력한다. 

	$ brew install youtube-dl

## 간단 사용법 ##

기본 사용 방법은 다음과 같다. 

	$ youtube-dl [OPTIOINS] <URL>

일단 영상 주소의 정보를 확인한다. 

	$ youtube-dl -F <URL>
	
	  ...
	  format code  extension  resolution note
	  ...

여기서 `format code`를 선택해서 다운로드 하면 된다.

	$ youtube-dl -f <format code> <URL>
	
영상마다 위 정보는 다르니 같은 `format code`가 항상 먹히지는 않으니 참고.

## 소리만 다운로드 ##

소리만 다운 받길 원한다면 추가로 확인할 것이 있다. 
`ffmpeg`코덱이 설치되어 있지 않으면 `mp3`로 변환이 불가하여 다음 명령어로 설치한다. 

	$ brew install ffmpeg

그리고 다음 명령어로 `mp3`만을 추출할 수 있다.

	$ youtube-dl --extract-audio --audio-format mp3 <URL>

## Comments ##

아프리카tv, 카카오tv, 네이버tv도 가능하다고 한다!?

... 물론, 유튜브를 비롯한 모든 사용은 불법이니 실제 사용의 책임은 각자의 몫으로..


