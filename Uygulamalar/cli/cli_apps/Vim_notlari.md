* buyuk kucuk harf donusturme;
Degistirecegin yeri secip visual mode'a gec
`U Uppercase u Lowercase`

*satir atlama: jump --> j satir sayisi
`5j`	

* imlecin bir altindaki satirla bulundugu satiri birlestirme; 
`J`	

* normal modda `e` kelimenin son karakterine goturur. 
* Pencere acikken buffer'i kapatma
`:Bclose`

* Tum satiri secme 
`shift+v` 

* pencereleri yeniden boyutlandirma 
`c+w sayi +-

* bos buffer'da bir dosya acma 
:n
* buffer'lar arasi gezinme;
:bn, :bp

* bos satirlari silme;
:g/^$/d

* her satir sonuna 2 bos karakter ekle 
:%norm A  

* her satirin sonundaki boslugu sil
:%s/\s\+$//

 %       = for every line
 norm    = type the following commands
 A*      = append '*' to the end of current line

* Bir kisayola iki kisayol ait komut atama; kisayol tuslari arasina \| eklenir.
`:nnoremap f }) \| zz`


* Vimdiff'teyken gorunumu dikey-yatay olarak degistirmek;
<C-w>J (or <C-w>K) when you are in vertical split and <C-w>H (<C-w>L) in horizontal

* Metin icerisindeki turkce karakterleri aratmak;
:set digraph
Ctrl-k c, -> ç
Ctrl-k C, -> Ç
Ctrl-k g( -> ğ
Ctrl-k G> -> Ğ
Ctrl-k i. -> ı
Ctrl-k I. -> I
Ctrl-k s, -> ş
Ctrl-k S, -> Ş
Ctrl-k u: -> ü
Ctrl-k U: -> Ü

* Buffer'larla calisma
Bu alanda sik kullanilan cesitli eklentiler mevcut, bunlardan Unite.vim ile
calisacagim.
`:Unite-vertical file buffer` ile nerdtree'deki gibi dosyalari ve buffer'lari goruntuleyebiliyoruz.

* satirlari sutuna cevirme;
`:%s/\n/`

* tab duzenlemeleri;
* vertical help icin :vertical yaz.

* Aramada  regex pattern'lerini kullanma;
\<aranacak_pattern\>

* satir sonlarindaki ^M  karakterleri kaldirma.
`%s/\r/\r/g`

* json biceminde olup da duz metin gibi gorunen tamponu okunakli hale getirmek
icin;
```
:%!python -m json.tool
```
* .vimrc'yi cagirmadan baslatma
```
vim -u NORC
```

### eklentiler 
* Kisa Kisa kullandigim eklentileri tanitmak istiyorum.

bclose.vim
goyo.vim
L9
neocomplete.vim
neomru.vim
neosnippet.vim
nginx.vim
nerdtree
vim-easymotion
vim-json
vimroom
vim-surround
vim-tmux-navigator
vim-zenroom2
vim-buffergator


#### Eklenti Notlari;
* unite vimproc ve neobundle'dan henuz verim alamadigimdan listeden cikarttim.

* nerdtree

* easymotion
backward search: <header><header>b

#### Vim help'ten notlar:
* sadece help penceresini acma;
help |only

* belli bir basliga direk gitme;
imleci basliga gotur ve CTRL-]
geri gelmek icin CTRL-T veya CTRL-O (tekrar bastiginda daha eskiye gider)

* help'te arama yapmak
:helpgrep ile kelime ara (ignorecase icin \G)
aranan kelimenin gectigi yerleri gormek icin :cwindow


* :global komutu;
global commands work by first scanning through the [range] lines and
marking each line where a match occurs (for a multi-line pattern, only the
start of the match matters).

* tum fold'lanan yerleri acma

```
set nofoldenable 
```

* Regex karakterleri
\r break line
\s white space

* her dolu satirin altina bos bir satir ekle;
```
:%s/.*\n.*\n.*\n/\0\r/g
```

```
http://vim.wikia.com/wiki/Working_with_CSV_files
```

```
Python Mode
```

#. herhangi bir komutun uzerinde K 'ya bastiginda dokumanini acar.

#. <leader> r ile calistirip ciktisini yeni buffer'a doker


```
Neosnippet ile python snippet'lerini kullanma
```


