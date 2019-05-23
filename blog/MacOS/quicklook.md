# QuickLook of macOS #

작성 날짜 : 2019. 05. 10

macOS에서 키보드의 스페이스 바를 눌러 pdf 및 그림 파일을 확인하는 것에 익숙해 지면 다른 OS로 바꾸기 어렵다.
윈도우에서도 스페이스 바를 누르고 '아, macOS 아니지.'라고 생각한 적이 한 두 번이 아닌데,
그 기능의 이름이 바로 `퀵룩`(`QuickLook`)이다.

사실, 이 퀵룩 기능에 `플러그인`(`plug-in`)을 추가해서 기본으로 적용되지 않는 다양한 확장자에도 적용이 가능하다.
퀵룩에 적용되는 플러그인은 아래 폴더에 저장되어 있다.

	~/Library/QuickLook

따라서 개인적으로 플러그인 제작이 가능한 유저는 따로 만들어서 이곳에 저장하면 될 테지만 난 못함.


기본기능 이외에 추가해서 개인적으로 가장 잘 사용하는 두 가지 플러그인은 다음 두 가지다. 

  * `QLMarkdown` : 마크다운용
  * `ipynb-quicklook` : ipython용

참고한 링크 주소는 페이지 가장 아래 정리해 둔다. 


## QLMarkdown ##

터미널에서 아래 명령어를 입력한다.

	$ brew cask install qlmarkdown

그리고 아래 명령어로 퀵룩을 재시작한다.

	$ qlmanage -r

끝.

`.md`파일에서 스페이스 바를 눌러 이쁘게 표시되는 마크다운 프리뷰를 감상하자.



## ipynb-quicklook ##

`ipython` 플러그인은 마크다운보다는 약간 복잡하다.

먼저 아래 명령어로 `Jupyter Notebook Viewer`를 설치한다.
사실 퀵룩에서 보여주는 ipython은 Jupyter Notebook Viewer를 띄워줄 뿐이다.
	
	$ brew cask install jupyter-notebook-viewer


그리고 [ipython quicklook realese](https://github.com/tuxu/ipynb-quicklook/releases) 페이지로 가서 
`ipynb-quicklook.qlgenerator.zip` 파일을 다운받아 압축 해제하면 `ipynb-quicklook.qlgenerator` 폴더를 볼 수 있다.
(파일처럼 보이겠지만 아니다.) 이 폴더를 아래 주소에 옮겨둔다. 그리고 퀵룩을 재실행.

	mv -R ipython-quicklook.qlgenerator ~/Library/QuickLook
	$ qlmanage -r

이제 `.ipynb`파일에서 스페이스 바를 눌러보면 Jupyter Notebook 폼의 ipython 프리뷰를 볼 수 있다. 이쁨.


## Comments ##

퀵룩 플러그인을 만들 생각은 한 번도 해 본 적이 없다.
퀵룩을 사용하는 목적은 알려진 많은 플러그인으로 해결이 가능하지 싶다. 
퀵룩을 만들고자 하는 유저는 아주 민감하게 컴퓨터 사용에 불편함을 느끼는 사람이 아닐까.
근데 그걸 잘 느끼는 사람이 만든 프로그램이 편리한 컴퓨터 사용에 정말 큰 도움을 주는 듯.

물론 이외에도 Python이나 C 등등을 위한 여러 플러그인이 많다!
필요한 유저들은 아래 링크 페이지를 검색해서 원하는 플러그인을 찾으면 된다. 
없을 수도 있고. 하지만 다들 구글링을 하겠지..

그리고 참고한 링크들도 같이 아래 추가해 둔다.

  * URL : https://www.quicklookplugins.com/ <-- 여기서 플러그인을 검색
  * URL : https://github.com/tuxu/nbviewer-app
  * URL : https://github.com/tuxu/ipynb-quicklook
  * URL : https://github.com/sindresorhus/quick-look-plugins 
