# Markdown in Emacs with Realtime Preview#

작성 날짜 : 2019. 05. 09


개인적인 생각으로 마크다운이나 텍 파일의 즉각적이며 부드러운 Realtim Preview를 
Emacs로 봐야 한다는 생각은 어느정도 잘못된 것이 아닌가 싶다.
Rendering에 강한 다른 에디터를 찾는 것이 더 쉬운 방법이라는 생각이다.
이 것은 많은 시간을 마크다운의 Realtime Preview를 설정하기 위해서 보낸 시간이 아까워서 하는 하소연이 아니다. 절대로.

결론적으로 `Flymd`에 정착했다. 
  * 약간의 딜레이가 있고, 
  * 이맥스 창 바깥의 웹브라우저를 뷰어로 사용하고, 
  * 디자인이 이쁘지 않은 설정 단추를 보여주는,
`Flymd`를 선택한 이유는 적당한 수준의 Realtime Preview를 보여주기 때문이다.

사실, 마크다운의 Syntax color를 사용하면 구지 Preview를 봐야 하나?

.... 봐야지.. 잘 나오는지 확인을..


## Flymd 설치 ##

나는 macOS 상에서 `Flymd`는 `FireFox`와 궁합이 좋다.
(메인 웹브라우저를 Chrome으로 사용 중이라 이 부분 또한 아쉬운 점이다.)

1. 우선 `FireFox`를 설치한다. 
1. emacs에서 `flymd` 패키지를 설치한다. 

	``` lisp
	M-x package-install RET flymd RET
	```

1. 다음 설정을 `.emacs`에 추가한다. 

	``` lisp
	(require 'flymd)
	(defun my-flymd-browser-function (url)
		(let ((process-environment (browse-url-process-environment)))
			 (apply 'start-process
 			 (concat "firefox " url)
			 nil
			 "/usr/bin/open"
			 (list "-a" "firefox" url))))
	(setq flymd-browser-open-function 'my-flymd-browser-function)
	```

설치는 이것으로 끝.

## Flymd 사용 ##

`.md`파일에서 `markdown-mode`라면 다음 명령어를 입력해보자.

``` lisp
M-x flymd-flyit
```

`FireFox`가 나타나고 `html`로 컴파일 된 마크다운 문서가 나타나면 성공.


## Flymd의 편리한 사용 ##


이제 설치가 완료 되었지만 개인적인 편리함을 위해서 몇가지를 추가했다.

1. 단축키 지정

	``` lisp
	(defun my-markdown-mode-hook ()
		(local-set-key (kbd "<f5>") 'flymd-flyit))
	(add-hook 'markdown-mode-hook 'my-markdown-mode-hook)
	```

1. `flymd` temp 파일 제거

	수정 중인 마크다운 파일이 있는 폴더에 다음 다 파일이 자동 생성된다. 

	* `flymd.html`
	* `flymd.md`
   
	마크다운 문서 버퍼를 제거하면 두 파일이 삭제되도록 하는 설정이 기본으로 제공된다. 
	
	``` lisp
	(custom-set-variables
	 '(flymd-close-buffer-delete-temp-files t))
	```

## Comments ##

다른 자세한 사항을 위해서는 다음 `flymd` github 페이지를 참고하자.

* URL : https://github.com/mola-T/flymd
