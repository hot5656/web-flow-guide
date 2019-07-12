# Emacs 

*   [Root](../README.md)

### temp
 emacs --debug-init
sudo apt-get install elpa-helm-projectile
;; (setq helm-projectile-fuzzy-match nil)
(require 'helm-projectile)
(helm-projectile-on)

;; (setq helm-projectile-fuzzy-match nil)
;; (require 'helm-projectile)
;; (projectile-mode +1)
;; (define-key projectile-mode-map (kbd "C-c C-p") 'projectile-command-map)
;; (helm-projectile-on)


* helm-projectile		input pattern
helm-projectile-switch-project		switch project
* helm-projectile-find-file			find file
* helm-projectile-find-dir			find directory
helm-M-x			helm for M-x

C-h m shows Helm commands and currently active key bindings.

silversearcher-ag

sudo apt-get install global

### emacs training
edit  
	```
	//ggtags
	M-.		1st find tag definition, 2nd all tag
	M-,		return to previous tag
	// projectile
	C-c p f 	search file
	C-c p s g	projectile-grep
	C-c p s s 	projectile-ag(need install the_silver_searcher[advice grep])
	C-c p k 	kill all the porject's buffer
	C-c p S 	save all the porject's buffer

	// key 
    s-x super (windows or cmd) key 

	C-?	Ctrl
	M-? Meta(Alt)
	C-v	向下
	M-v	向上
	C-l	清除重show(游標置螢幕中間)
	C-x k	kill current buffer

				C-p
	C-b(M-b字)		C-f(M-f字)
				C-n

	M-< 文件頭
	M-a(句頭) C-a(行頭)			C-e(行尾) M-e(句尾)
	M->文件尾

	C-d刪一字元 (M-d刪一字)
	C-x u (undo取消)
	C-k 刪至行尾
	M-k 刪至句尾
	C-SPC 標示刪除頭 C-w刪除尾
	C-y	貼上刪除行或區塊
	M-w	複製
	C-w	剪下
	M-x goto-line 輸入數字
	M-g g 輸入行號
	C-k 刪除目前位置到行尾
	C-u 重複

	// windows 
	C-x o next window
	C-x 0 去除方塊所在畫面
	C-x	1 成一視窗
	C-x 2 水平分鴿
	C-x 3 垂直分割

	// file
	C-x C-f 	open one file
	C-x C-s		save file
	C-x C-b		列出緩衝區
	C-x b       切換緩衝區
	C-x C-c		關閉 Emacs
	q           跳回
	M-x dired 瀏覽資料夾 (或用　C-x d) 
	M-x shell (進入 shell)
	M-x linum-mode 顯示行號(toggle)


	// help 
	C-h ?	help
	C-h c C-p	函數名稱
	C-h k C-p	函數說明文件
	C-h f		解釋函數
	C-h b		show key define
	C-h m 		show buffer's mode

	// buffer
	C-x b		更換到另一個緩衝區
	C-x C-b		顯示所有緩衝區資料
	C-x	k		砍掉緩衝區
	q			跳出某些buffer

	// special
	C-u 重複指令 C-u 8 C-f(do C-f 8 times)
	C-g 取消停止指令
	C-z 暫停emacs  (fg 恢復)
	C-s,C-r 搜尋 
	g  refresh buffer
	C-c C-c : end some function(ex:git commit)

	//magit
	;; C-x g : magit-status(also can do as init)
	;; magit : i   add ignore
	;;         tab 展開
	;;         CR  開檔
	;;         ? - help
	;; c c --> triger commit
	;;     --> write commit message --> C-c C-c
	;;     C-c C-c     (with-editor-finish)
	;;     C-c C-k     (with-editor-cancel)
	;;     commit message
	;;        用一行空白行分隔標題與內容
	;; b(branch) b(branch-checkout)
	;; b(branch) c(new branch-checkout)
	;; b(branch) n(new branch)
	;; z z --> stash(儲藏)
	;; z p --> stash pop(取出)
	;; E(Ediff) m(Resolve) --> edit
	;;          *Ediff Control buff
	;; k   --> Discard(support stash)
	;; m(merge) m(merge)
	;; X(reset) s(soft) - 保留修改
	;;          h(hard) - 修改刪除
	;; rebase 放在起分支點
	;;          r(rebase) i(interactively) --> continue --> 可調整commit順序(分支消失)
	;; M(remote) a(add) --> name:origin --> url
	;; P(push) p(origin/master) --> name --> password
	;; F(pull) p(origin/master)
	;; magit status
	p/n		previous/next
	s		magit-stage
	k		magit-discard
	i		magit-ginitgore
	tab		show toggle
	RET		view
	;; Ediff ~:now ~^previous 
	|	vert/horiz
	p	previous diff
	n	nex diff
	v/V down/up page
	i	highlighting
	D	diff output
	j	jump to diff
	=	compare region
 	;; buffer list(M-x buffer-manu)
 	p/n	previous/next
 	m	mask
 	u	remove make
	d	select wait delete buffer --> x (do all delete)
	s	select wait save buff
	x	excute for "d or s"
	u	remove all select
	;; 
	C-x 4 b buffer <RET>	select to one buffer to another buffer
	C-x <LEFT>		previous buffer
	C-x <RIGHT>		next buffer
	C-x C-f			open one file
	C-x C-s			save buffer
	C-x s 			save all file

	// directory control
	+ add directory
	C-M-j (use ivy 僅執行輸入值) - 強制 enter
	```

Lisp
	```
	C-x C-e		run 1 Lisp command

	;; dump buffer file
	buffer-file-name

	(+ 1 2 3)

	(+ (* 2 3)
	   (/ 4 2))

	;; send message to minibuff & message
	;; return value is this is help!
	(message "this is help!")
	;; same as printf 
	(format "Hello World!~")
	;; print
	;; 1st is print show
	(print "Print to mini buffer")
	;; insert to current burrent
	(insert ";insert this text")

	;; list
	(list 'my (+ 1 1) "son")
	;; simple list
	(quote (1 2 3))
	'(1 2 3)
	;; get 1st item
	(car '(1 2 3))
	;; get 2.. item
	(cdr '(1 2 3))
	;; add one item to list
	(cons 1 '(2 5))
	;; simple add one item to list
	'(1 . (2 5))
	;; just link list as one item  
	(cons '(2 5) 1)
	'((2 5) . 1)
	'((2 5) . (1 3))
	;; list 2 string
	'(" this is " . "a text")

	;; 2nd item
	(cadr '(1st 2nd 3rd 4th))
	;; direct 2nd item(index from 0)
	(nth 1 '(1st 2nd 3rd 4th))

	;; check member in list - not null mean true
	(member 'b '(a b c))
	(member '(a) '((a) (b)))
	;; memq need actually
	(memq '(b) '((a) (b)))

	;; key word
	(defvar superman (list :name "Superman" :secret-id "Clark kent"))
	(format "%s" superman)
	(print superman.name)

	;; global variable
	(defvar *nums* '(2 4 6))
	(push 1 *nums*)
	;; show variable
	*nums*
	;; set variable - 2nd way
	(set 'some-list '(a b c))
	some-list
	;; add item
	(cons 'z some-list)

	;; compare
	;; actual equal
	(eq some-list '(a b c))
	;; actual equal(number also ok)
	(eql some-list '(a b c))
	;; simple compare
	(equal some-list '(a b c))

	;; setq 
	(setq my-list '(4 5 6))
	my-list

	;; call function 5,6 --> 10
	(setf (cdr my-list) 10)
	my-list

	;; local variable
	(let ((a 1) (b 3))
	  (format "now a is %d b is %d" a b))
	a

	;; 含運算式
	(let* ((a 1) (b (+ a 4)))
	  (format "now a is %d b is %d" a b))
	a

	;; function
	(defun say-hello ()
	  (message "hello world"))

	(say-hello)
	;; check function?
	(functionp 'say-hello)

	;; optional args
	;;    &optional (x y x)
	;;    &rest ...
	(defun print-list (&optional x y z &rest ns)
	  (format "%s" (list x y z ns)))

	(print-list)
	;; no func-arity for new emacs
	(func-arity 'print-list)
	(print-list 1 2)
	(print-list 1 2 3 4 5 6)

	;; local function
	(cl-flet ((double-it (num)
			     (* num 2)))
	  (double-it 10))

	;; multi return value
	;; expt 幾次方
	(defun squares (num)
	  (values (expt num 2) (expt num 3)))

	;; try multiple value
	;; require on el
	(require 'cl)
	(multiple-value-bind (a b) (squares 2)
	  (format "%d and %d" a b))

	;; 函數當參數
	(apply #'+ '(1 2 3))
	;; 2nd way
	(funcall #'+
		 1 2 3)

	;; key biding
	(global-set-key (kbd "M-#") 'sort-lines)

	;; show major mode
	major-mode

	C-h k key
	C-h m mode
	C-h f function
	C-h a region
	C-h v variable
	C-h C-h help
	C-h i   info-manual
	```

basic setting
	```
	// emacs configure directory
	~/.emacs.d/
	// configure init file
	// 1st priority
	~/~/.emacs
	// 2nd pripority
	~/.emacs.d/init.el
	```

init.el
```
;; hide welcome message
(setq inhibit-startup-message t)
;; add MELPA
(require 'package)
(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/"))
(package-initialize)

;;
;; set autosave and backup directory
;; /tmp/emacs1000
(defconst emacs-tmp-dir (format "%s%s%s/" temporary-file-directory "emacs" (user-uid)))
(setq backup-directory-alist
      `((".*" . ,emacs-tmp-dir)))
(setq auto-save-file-name-transforms
      `((".*" ,emacs-tmp-dir t)))

;;
;; custome variable path
;;
(setq custom-file "~/.emacs.d/custom-variables.el")
(load custom-file)

;;
;; use use-package(未安裝即安裝)
;; 某 mode 僅啟動某 package
(unless (package-installed-p 'use-package)
  (package-refresh-contents)
  (package-install 'use-package))

;; diminish - 次模式隱藏(if not install then install)
(use-package diminish :ensure t)
;; bind-key(if not install then install)
(use-package bind-key :ensure t)
;; package auto update(if not install then install,not do any times)
(use-package auto-package-update
  :ensure t
  :config
  (setq auto-package-update-delete-old-versions t)
  (setq auto-package-update-hide-results t)
  (auto-package-update-maybe))

;;
;; basic setup
;;
;; if terminal mode not nees menu-bar disable
;; (menu-bar-mode -1)
;; 括號顯示對應
(show-paren-mode t)
;; 相對括號自動產生
(electric-pair-mode t)
;; define pair generate
(setq electric-pair-pairs '(
			    (?\' . ?\')
			    ))
;; set tab auto transfor to space
;; (setq-default indent-tabs-mode nil)
;; 方便切換 雙畫面
;; C-c left previous windows status
;; C-c right redo  
(winner-mode t)

;;
;; hideshow(縮開程式block)
;; C-c @ C-h 
;; C-c @ C-s
(add-hook 'prog-mode-hook #'hs-minor-mode)

;;
;; multiple cursors
;; C-x C-m C-g : edit all
;; M-3/M-4 : select
;; C-g : edit
;; 2nd C-g : 恢復原狀
(use-package multiple-cursors
  :ensure t
  :bind(
	("M-3" . mc/mark-next-like-this)
	("M-4" . mc/mark-previous-like-this)
	:map ctl-x-map
	("\C-m" . mc/mark-all-dwim)
	("<return>" . mule-keymap)
	))

;; ***** ivy mode *****
;;
;; ivy mode
;; ibuffer 優化
(use-package ivy
  ;; int not install, auto install
  :ensure t
  ;; 隱藏 ivy mode(即 ivy 次模式)
  :diminish (ivy-mode . "")
  :config
  (ivy-mode 1)
  ;; 加快速度
  (setq ivy-use-virtual-buffers t)
  (setq enable-recursive-minibuffers t)
  ;; 最多 show 10 筆
  (setq ivy-height 10)
  ;; 無初設資料
  (setq ivy-initial-inputs-alist nil)
  ;; 顯示所在位置 ex: 2/20
  (setq ivy-count-format "%d/%d")
  ;; Regular Expression 搜尋 不在乎前後順序
  (setq ivy-re-builders-alist '((t . ivy--regex-ignore-order)))
  )

;; counsel
;; command search
(use-package counsel
  :ensure t
  :bind (("M-x" . counsel-M-x)
	 ("\C-x \C-f" . counsel-find-file))
  )

;; swiper - 取代 i search
;; C-s 後,可在下視窗看到所有符合資料
(use-package swiper
  :ensure t
  :bind (("\C-s" . swiper))
  )

;;
;; ***** yasnippet - 帶入預存代碼 *****
;;
;; 有時候not found是因為package not refresh --> run package-refresh-countes
;; default no load any reserve code --> add yasnippet-snippets
;;
;; yas-describe-tables --> check support snippet
;; ex: as
;; 輸入後按tab
;;
;; yas-new-snippet --> add new snippet file
;; # -*- mode: snippet -*-
;; # name: show message
;; # key: show
;; # --
;; (message "hello")$0
;; *****> save file --> C-c C-c(yas-load-snippet-buffer-and-close)  
;; if no support emacs-lisp-mode
;; *****> yas-active-exttr-mode --> emacs-lisp-mode
(use-package yasnippet
  :ensure t
  ;; 未load前,先執行
  :init
  (add-hook 'prog-mode-hook #'yas-minor-mode)
  :config
  (yas-reload-all)
  (use-package yasnippet-snippets
    :ensure t)
  )


;;
;; ***** company(complete anything) 自動補全 *****
;;
;; C-h v --> company-backend (check company-backend setting)
(use-package company
  :ensure t
  :config
  (global-company-mode t)
  (setq company-idel-delay 0)
  (setq company-minimum-prefix-length 3)
  (setq company-backends
	'((company-files company-yasnippet company-capf company-keywords)
	  (company-abbrev company-dabbrev)))
  )
;; emacs-lisp-mode add some
(add-hook 'emacs-lisp-mode-hook (lambda()
				  (add-to-list (make-local-variable 'company-backends)
					       'company-elisp)))
;; change C-n C-p to company select in company buffer
(with-eval-after-load 'company
  (define-key company-active-map (kbd "M-n") nil)
  (define-key company-active-map (kbd "M-p") nil)
  (define-key company-active-map (kbd "\C-n") #'company-select-next)
  (define-key company-active-map (kbd "\C-p") #'company-select-previous)
  )
;; diagnostic
;; company 後 --> M-x company-diag 可分析
;; tab yasnippet 執行
;; company tab 補齊有時會有問題 加入以下 --> not work well
;;(advice-add 'company-complete-common :before (lambda() (setq my-company-point (point))))
;;(advice-add 'company-complete-common :after (lambda()
;;					    (when (equal my-company-point (point))
;;					      (yas-expand))))


;;
;; ***** flycheck mode 語法檢查 *****
;;
;; C-c ! v --> check using library
;; C-c ! l --> dump check result
;; (use-package flycheck
;;  :ensure t
;;  :config
;;  (global-flycheck-mode t)
;;  )

;;
;; ***** magit ****
;;
;; C-x g : magit-status
;; magit : i   add ignore
;;         tab 展開
;;         CR  開檔
;;         ? - help
;; c c --> triger commit
;;     --> write commit message --> C-c C-c
;;     C-c C-c     (with-editor-finish)
;;     C-c C-k     (with-editor-cancel)
;;     commit message
;;        用一行空白行分隔標題與內容
;; b(branch) b(branch-checkout)
;; b(branch) c(new branch-checkout)
;; b(branch) n(new branch)
;; z z --> stash(儲藏)
;; z p --> stash pop(取出)
;; E(Ediff) m(Resolve) --> edit
;;          *Ediff Control buff
;; k   --> Discard(support stash)
;; m(merge) m(merge)
;; X(reset) s(soft) - 保留修改
;;          h(hard) - 修改刪除
;; rebase 放在起分支點
;;          r(rebase) i(interactively) --> continue --> 可調整commit順序(分支消失)
;; M(remote) a(add) --> name:origin --> url
;; P(push) p(origin/master) --> name --> password
;; F(pull) p(origin/master) 
(use-package magit
  :ensure t
  :bind(("C-x g" . magit-status))
  )
;; support add branch then add bracnch
(setq magit-branch-read-upstream-first 'fallback)

;;
;; ***** projectile (project manager)*****
;;
;; C-c p ? : show help
;; C-c p f : search file
;; C-c p a : switch .c .h
;; C-c p s g :	projectile-grep
;; C-c p s s :  projectile-ag(need install the_silver_searcher[advice grep]) - don't 'care ignore files   
(use-package projectile
  :ensure t
  :bind-keymap ("\C-c p" . projectile-command-map)
  :config
  (projectile-mode t)
  (setq projectile-completion-system 'ivy)
  (use-package counsel-projectile
    :ensure t)
  )
;; ag
(use-package ag
  :ensure t
  :config
  (setq ag-highlight-search t)
  )

;;
;; ***** ggtags(function define..switch) *****
;;
;; need install global
;;  sudo apt-get install global
(use-package ggtags
  :ensure t
  ;; :commands ggtags-mode
  ;; :diminish ggtags-mode
  ;; :bind (("M-*" . pop-tag-mark)
  ;;       ("C-c t s" . ggtags-find-other-symbol)
  ;;       ("C-c t h" . ggtags-view-tag-history)
  ;;       ("C-c t r" . ggtags-find-reference)
  ;;       ("C-c t f" . ggtags-find-file)
  ;;       ("C-c t c" . ggtags-create-tags))
  :init
  (add-hook 'c-mode-common-hook
            #'(lambda ()
                (when (derived-mode-p 'c-mode 'c++-mode 'java-mode)
                  (ggtags-mode 1)))))

```

### some setting 
brief
```
	// buffer 
C-x <LEFT> Select the previous buffe
C-x <RIGHT> Select the next buffer
C-x b        Select a buffer
C-x k		 select kill buffer(some have default buffername)
	c-x c-b	ibuffer
	c-x view-buffer 	view buffer(space backspace - q leave)

	// helm
	helm-projectile-find-file 	find file
	helm-projectile-switch		switch other projectile
	C-SPC 		mark each file individually
	M-a 		mark all

	<!-- M-x		My execute -->
	M-x		输入函数名就可以調调用函数
	M-x	magit-status

	c-x c-b	ibuffer
	c-r		privious search
	c-s		next search
	p/n		上下
	m		是選文件，可選多個
	n		移除文件選擇
	g 		刷新文件目錄
	q		離開畫面
	c-g		quit command
	c-x k	kill buffer
	C-x 2	垂直切割目前的 Window
	C-x 3	水平切割目前的 Window
	c-v		往後一頁
	m-v		往前一頁

	c-p		前一行
	c-n		後一行
	c-b		往左
	c-f		往右
	C-a 移动到行首，C-e 移动到行尾。
　　M-a 移动到句首，M-e 移动到句尾


	C-x C-c	關閉 Emacs	
	c-x c-f 開檔 (tab..)
	C-x C-s	这个命令是用来保存文件的
	C-x C-w	另存

	c-x	u	undo
	c-h ?	help
	help r	manual
	help t
	backspace/space	help buffer up/down
	```
*	customize (example magit)  
	options --> Customize Emacs --> Specific Group --> input "magit"
*	mode line  
	```
	%%	只讀，未更改
	--	可寫，未更改
	**	可寫，已更改
	%*	只讀，已更改
	```
*	ibuffer
	```
	p/n		上下
	m		是選文件，可選多個
	n		移除文件選擇
	D		是kill buffer
	cr/e	(就是edit)来编辑文件
	= 		與存檔文件做diff
	g 		刷新文件目錄
	```
*	buffer
	```
	C-x C-b 	list all buffer
	C-b		切換 Buffers	
	?? C-x k	殺掉 Buffer	
	```
*	Frames  
	Frames是 Emacs 的 GUI 視窗，Emacs 可以產生出多個視窗，但是共用同一個 daemon。  
	其中一個節點用 C-x C-c 關閉 Emacs 會導致整棵樹的所有 Frame 也一起被關閉。
	```
	C-x 5 0	關閉目前的 Frame
	C-x 5 1	關閉目前以外的所有 Frame
	C-x 5 2	建立新的 Frame
	C-x 5 o	切換至其他 Frame
	```
*	Windows  
	Windows是在同一個 Frame 中可在切割出的視窗，我們可以在同一個畫面再水平或垂直地切割出多個視窗，顯示不同的 Buffer，並且在其中進行切換，這樣就不須使用到多個 Frame 來分割畫面。
	```
	Emacs	功能
	C-x 0	關閉目前的 Window
	C-x 1	關閉目前以外的所有 Window
	C-x 2	垂直切割目前的 Window
	C-x 3	水平切割目前的 Window
	C-x o	切換至其他 Window
	```
*	install package  
	Options-->Emanage Emacs Package  
	M-x package-list-packages
	```
	套件		功能	說明
	magit				Git 管理操作	
	org 				Outline-based notes management and organizer
	helm-projectile		
	helm-ag

	company				自動補齊		需要根據不同語言來額外安裝其他 company 的套件。
	projectile			專案管理	
	ivy					自動補齊		與 company 不同的是自動補齊指令輸入等比較通用型的部份。
	counsel				強化指令輸入	
	counsel-projectile	強化 projectile	
	swiper				強化文字搜尋	
	avy					強化游標移動	
	undo-tree			強化 undo、redo	
	multiple-cursors	多游標	
	which-key			顯示 Key Map	
	```
*	add parameter
	```
	emacs -q
	```

*	初始化檔案
	```
	Emacs 預設的讀取順序是 ~/.emacs，~/.emacs.el，~/.emacs.d/init.el，筆者推薦用 .emacs.d/ 來管理設定
	```
*	emacs ~/.emacs  
	不要提示  
	setq 是指派變數 (assign) 的 Function，t 和 nil 分別指 true 和 false，所以 (setq inhibit-startup-message t) 就是將 inhibit-startup-message 這個變數的值設為 true。
	```
;; ~/.emacs
(setq inhibit-startup-message t)
	```
	add MELPA
	```
(require 'package)
(let* ((no-ssl (and (memq system-type '(windows-nt ms-dos))
                    (not (gnutls-available-p))))
       (proto (if no-ssl "http" "https")))
  ;; Comment/uncomment these two lines to enable/disable MELPA and MELPA Stable as desired
  (add-to-list 'package-archives (cons"melpa"(concat proto"://melpa.org/packages/")) t)
  ;;(add-to-list 'package-archives (cons"melpa-stable"(concat proto"://stable.melpa.org/packages/")) t)
  (when (< emacs-major-version 24)
    ;; For important compatibility libraries like cl-lib
    (add-to-list 'package-archives'("gnu" . (concat proto "://elpa.gnu.org/packages/")))))
(package-initialize)
	```
	管理 Buffers  
	list-buffers --> Buffer Menu
	```
(global-set-key (kbd "C-x C-b") 'ibuffer)
	```
	M-x add helm-M-x
	```
;; M-x add helm-M-x
(global-set-key (kbd "M-x") 'helm-M-x)
	```
*	 Emacs 按鍵  
	C=Ctrl M=Alt （註：C-h 在 Emacs 預設是 help，之後我們會將它變成刪除鍵）
	```
	C-s		:搜尋　　	一直按一直往下找

	Emacs	對應鍵		功能
	C-p		Up			游標往上一格
	C-n		Down		游標往下一格
	C-b		Left		游標往後一格
	C-f		Right		游標往前一格
	C-a		Home		游標移到最前面
	C-e		End			游標移到最後面
	C-d		Delete		刪掉後面一個字
	C-h		Backspace	刪掉前面一個字
	C-i		Tab			縮排
	C-m		Enter		換行、確定
	```
	Kill Ring是 Emacs 特有的像是剪貼簿的列表，它會將你上次透過像是 C-k 或 C-w 所 Kill 掉的字串存進去，之後可以利用 C-y 將它貼回 Buffer。C-y 預設會取用最後存入的字串，如果想要貼回 Kill Ring 中其中一段字串，可以重複按 M-y 來選擇。
	```
	Emacs	功能						說明
	C-v		往下一頁	
	M-v		往上一頁	
	C-l		維持游標位置並重新定位畫面	重複執行的話會分別在 top、center、bottom 的位置作切換
	C-s		往下搜尋文字	
	C-r		往上搜尋文字	
	C-g		離開指令					遇到指令執行不順可先嘗試按按這個來結束指令執行
	C-o		換行但不移動游標	
	C-k		殺掉游標後到換行字元前的文字	
	C-w		殺掉目前選取的文字	
	C-y		貼上保存在 kill ring 的文字	通常搭配 C-k 或 C-w 使用，來達成剪下貼上等功能
	C-b		切換 Buffers	
	C-x k	殺掉 Buffer	
	M-<		移動游標到 Buffer 最前面	
	M->		移動游標到 Buffer 最後面	
	C-x C-s	存檔	
	C-x C-c	關閉 Emacs	
	```
*	 command  
	M-x		:執行一個emacs命令
	C-g		:離開一個emacs命令
	```
	help 		help
	 M-x shell	shell
	```
*	remote file control
	使用方法
	```
	/method:host:filename
	/method:user@host:filename
	/method:user@host#port:filename
	```
	ssh example
	```
	/ssh:myuser@myhost:~/hello.rb
	```
*	magit
	magit-status	看git當前狀態
		? 可看command
		table 隱藏/顯示 內容
		CR 看 item 內容


	```
	magit-status	看git當前狀態(? 可看command)
	```

*	helm-projectile
	```
	// search file (pattern)
	helm-projectile

	// helm for M-x
	helm-M-x
	```


