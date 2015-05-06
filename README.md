# Faker

> **[Fork edit]**
>
> This fork aims to generated better `zh-TW` results, primarily used for
> https://www.zeczec.com, which should explain some of the language choices.

This gem is a port of Perl's Data::Faker library that generates fake data.

It comes in very handy for taking screenshots (taking screenshots for my
project, [Catch the Best](http://catchthebest.com/) was the original impetus
for the creation of this gem), having real-looking test data, and having your
database populated with more than one or two records while you're doing
development.

##Installing w/ Bundler

```bash
gem "faker", :git => "https://github.com/muan/faker.git"
```

Remember to initialize Faker with `Faker::Config.locale = "zh-TW"`

##Usage (fork edit)

```ruby
Faker::Name.name      #=> "王嘉玲"

Faker::Internet.email #=> "wangting@guizhigongzuoshi.org"
```

###Faker::Address (fork edit)
-----------------

```ruby
Faker::Address.city #=> "高雄市"

Faker::Address.street_name #=> "文律街"

Faker::Address.street_address #=> "行後路一段 4 號"

Faker::Address.secondary_address #=> "9 樓之 2"

Faker::Address.building_number #=> "80"

Faker::Address.zip_code #=> "58517"

Faker::Address.zip #=> "58517"

Faker::Address.postcode #=> "58517"

Faker::Address.time_zone #=> "Asia/Taipei"

Faker::Address.street_suffix #=> "路"

Faker::Address.city_suffix #=> "市"

Faker::Address.city_prefix #=> "宜蘭"

Faker::Address.country #=>  "比利時"

Faker::Address.latitude #=> "-58.17256227443719"

Faker::Address.longitude #=> "-156.65548382095133"


```

###Faker::Bitcoin

```ruby

Faker::Bitcoin.address #=> "1HUoGjmgChmnxxYhz87YytV4gVjfPaExmh"
Faker::Bitcoin.testnet_address #=> ""msHGunDvoEwmVFXvd2Bub1SNw5RP1YHJaf""

```

###Faker::Business

```ruby

Faker::Business.credit_card_number #=> "1228-1221-1221-1431"

Faker::Business.credit_card_expiry_date #=> <Date: 2015-11-11 ((2457338j,0s,0n),+0s,2299161j)>

Faker::Business.credit_card_type #=> "visa"

```

###Faker::Code

```ruby

Faker::Code.isbn #=> "759021701-8"

Faker::Code.ean #=> "4600051000057"

```

###Faker::Commerce (fork edit)

```ruby

Faker::Commerce.color #=> "橘色"

# Optional arguments max=3, fixed_amount=false
Faker::Commerce.department #=> "健康與美容"
Faker::Commerce.department(5) #=> "電腦，雜貨，汽車，遊戲與音樂"
Faker::Commerce.department(2, true) #=> "健康與體育"

Faker::Commerce.product_name #=> "智慧型木頭滑板"

Faker::Commerce.price #=> "44.6"

```

###Faker::Company (fork edit)

```ruby

Faker::Company.name #=> "主最球股份有限公司"

Faker::Company.suffix #=> "有限公司"

# Generate a buzzword-laden catch phrase.
Faker::Company.catch_phrase #=> "Business-focused coherent parallelism"

# When a straight answer won't do, BS to the rescue!
Faker::Company.bs #=> "雲端"

Faker::Company.ein #=> "34-8488813"

Faker::Company.duns_number #=> "08-341-3736"

# Get a random company logo url in PNG format.
Faker::Company.logo #=> "http://pigment.github.com/fake-logos/logos/medium/color/5.png"

```

###Faker::Date

```ruby
# Random date between dates
Faker::Date.between(2.days.ago, Date.today) #=> "Wed, 24 Sep 2014"

# Random date in the future (up to maximum of N days)
Faker::Date.forward(23) # => "Fri, 03 Oct 2014"

# Random date in the past (up to maximum of N days)
Faker::Date.backward(14) #=> "Fri, 19 Sep 2014"
```

###Faker::Internet (fork edit)

```ruby
# Optional argument name=nil
Faker::Internet.email #=> "xinyi.yang@yuzhiyouxiangongsi.com.tw"

Faker::Internet.email('小明') #=> "ming.xiao@weixufugongzuoshi.tw"

# Optional argument name=nil
Faker::Internet.free_email #=> "jiahao.shi@msa.hinet.net"

Faker::Internet.free_email('小明') #=> "ming.xiao@yahoo.com.tw"

# Optional argument name=nil
Faker::Internet.safe_email #=> "christelle@example.org"

Faker::Internet.safe_email('小明') #=> "xiao_ming@example.com"

# Optional arguments specifier=nil, separators=%w(. _)
Faker::Internet.user_name #=> "xiaoting"

Faker::Internet.user_name('小明') #=> "ming.xiao"

Faker::Internet.user_name('王小明', %w(. _ -)) #=> "ming.wang.xiao"

# Optional arguments: min_length=8, max_length=16
Faker::Internet.password #=> "vg5msvy1uerg7"

Faker::Internet.password(8) #=> "yfgjik0hgzdqs0"

Faker::Internet.password(10, 20) #=> "eoc9shwd1hwq4vbgfw"

Faker::Internet.domain_name #=> "dashiyagongzuoshi.com"

Faker::Internet.fix_umlauts('äöüß') #=> "aeoeuess"

Faker::Internet.domain_word #=> "chuliyouxiangongsi"

Faker::Internet.domain_suffix #=> "com.tw"

Faker::Internet.ip_v4_address #=> "24.29.18.175"

Faker::Internet.ip_v6_address #=> "ac5f:d696:3807:1d72:2eb5:4e81:7d2b:e1df"

# Optional argument prefix=''
Faker::Internet.mac_address #=> "e6:0d:00:11:ed:4f"
Faker::Internet.mac_address('55:44:33') #=> "55:44:33:02:1d:9b"

# Optional arguments: host=domain_name, path="/#{user_name}"
Faker::Internet.url #=> "http://thiel.com/chauncey_simonis"
Faker::Internet.url('example.com') #=> "http://example.com/clotilde.swift"
Faker::Internet.url('example.com', '/foobar.html') #=> "http://example.com/foobar.html"

# Optional arguments: words=nil, glue=nil
Faker::Internet.slug #=> "pariatur_laudantium"
Faker::Internet.slug('foo bar') #=> "foo.bar"
Faker::Internet.slug('foo bar', '-') #=> "foo-bar"


```

###Faker::Lorem (fork edit)

```ruby

Faker::Lorem.word #=> "話"

Faker::Lorem.term #=> "感蘇" # fork edit

# Optional arguments: num=3, supplemental=false
Faker::Lorem.words #=> ["程", "政", "地", "部", "識", "間"]
Faker::Lorem.words(4) #=> ["控", "速", "度", "著", "場", "逾", "關", "外"]
Faker::Lorem.words(4, true) #=> ["悅", "控", "虞", "所", "典", "問", "況", "仍"]

# Optional arguments: char_count=255
Faker::Lorem.characters #=> "uw1ep04lhs0c4d931n1jmrspprf5wrj85fefue0y7y6m56b6omquh7br7dhqijwlawejpl765nb1716idmp3xnfo85v349pzy2o9rir23y2qhflwr71c1585fnynguiphkjm8p0vktwitcsm16lny7jzp9t4drwav3qmhz4yjq4k04x14gl6p148hulyqioo72tf8nwrxxcclfypz2lc58lsibgfe5w5p0xv95peafjjmm2frkhdc6duoky0aha"
Faker::Lorem.characters(10) #=> "ang9cbhoa8"

# Optional arguments: word_count=4, supplemental=false, random_words_to_add=6
Faker::Lorem.sentence #=> "摩擔獨召孩技應今際優虞微對力尊元部與。"
Faker::Lorem.sentence(3) #=> "聞獨區語力者。"
Faker::Lorem.sentence(3, true) #=> "說貝謀引且國翻解！"
Faker::Lorem.sentence(3, false, 4) #=> "為結民亂經唐情數？"
Faker::Lorem.sentence(3, true, 4) #=> "廣佔際究府棄欠露確而！"

# Optional arguments: sentence_count=3, supplemental=false
Faker::Lorem.sentences #=> ["入都頻簡狀質層何事楚審後旨集究下。", "任部退效全西信集桃和監行書化楚都。", "書亂括規退了速反。", "閻的情洲年常是督華看媒光謀許？", "字論活為議誤。", "我元益定期外露通投所洲己！"]
Faker::Lorem.sentences(1) #=> ["孩利近感選任地個區古師供。", "悅規提赴人中冕狀權說。"]
Faker::Lorem.sentences(1, true) #=> ["面歷惜現合評俊都十虞沒等但港！", "小急場財報很高說平況廣年行蘇方糟？"]

# Optional arguments: sentence_count=3, supplemental=false, random_sentences_to_add=3
Faker::Lorem.paragraph #=> "語平意希被來。要後已監定懂。聞去其獨言集們哥量詩人者捨主。層歐缺由失行所是翻當。與所席古屈辭展低年提民壟。悔感響標宣十身典悅寫路躍奬商意島？銳沒名正棄更！自反年悔亞創接曾及響露佔應任。仍數向桃尊語馬集歲由化世近宣。十行括如席告壟現書旬己來讓漢冰過。在樂代作島致我余。場化而業典入首反赴社邀壟決們二歷。響益降研致版事糟灣說薦建而瑞。之詞化活洲頒了書。長傳經場澳程語律典懂謀全少爭？家李由醒對起悔休仍虞。"
Faker::Lorem.paragraph(2) #=> "前講只曾道不科俊反成表邀佔多！泰本亞言德釋法明亂能？終西向作澳關代控？增等新降陸相架因包未民邀素急。傳站增醒根狀給翻古妻健點雖余。獎唐於評數升活點球際。題創委常立文乃頻！上關花以非織也商講民響高標聞。集港標提週今話而與報識己日極能讀。謀更與走活精辭亂和將選話。"
Faker::Lorem.paragraph(2, true) #=> "尊翻顯集分虞們元。於傳技長策話都匯！導現亞文利部澳寫欠也。顯欠根匯等躍常且。發德傳中質不簡正！話十記微書簡且海旬括？由願內球世遭回控治信？低題規讓好而其惜俊估？我區余根和能引監升非組而常的學致。爾只系歸期曹解匯師未被詩告都走亂。示我討漢源少路而量一急審！意織文新正虞會今查花致退。"
Faker::Lorem.paragraph(2, false, 4) #=> "意推錯聞本現！力加翻願看版。大路解速界開東面排漢策接的休了反。產權是層懂分估當討%上在德研低相。推沒趙及關部歲恩來確要際三的。業推綁歐選也西教集表。壟程影海通狀講結？旨介為迴難高導還殺健！議諾演外身很現內十查香接釋其！期語結正一站優島末樂綁和。"
Faker::Lorem.paragraph(2, true, 4) #=> "二承薦們提成。僅洲源愈開路等國解曾。注上席桃引他反而年商！台冰應召況然。沒古漢有後講歲利最洲遽諾誤悔。爾在且們內團古訂屈中情唐。長曾釋後棄世識記末從缺十織透臨歷！素只糟如主球透道因樂於任。"

# Optional arguments: paragraph_count=3, supplemental=false
Faker::Lorem.paragraphs #=> ["世能別所社臘德首。今示件時討於童間明因！然立件外廣桃。首制素就界樂日躍。感九冰躍灣貝臨曹議別？財願確閻恩屈經譯洲出地織。之場頻指貝己及承且這。門被兩佔宣薦。歐擔網治寫源品桃展南和三作李。委給蘇安歷獨名曾雖字期仍讓要。漢西於分政都恩選方二顯供。局活度平傳律。導括事最邀辭。用控講討化正赴今量休優門。流根語團大缺！蘇序升中層日信如？", "及避成回澳冠幾退微今程投審島週個。其如詩閻介體查程戰反。少事民治本且屈究？訪謙接標限休規澳升還。最評門蘇已法然情在引。莫控上占與致！詞瑞過這告選西事。訂壇入量規臘僅退。展行反更會委奬週。很場事視題非有欠也得際棄？關捨俊恩有悔度排醒避現報。古用為德泰%。", "質棄府反正可島孩。邀增效仍架當展港銳後師終。出告余序哥壇！精露提顯專源讓發。發休響沒露力希指區曾在連世際訪討。集排微悔壟新才誤簡就反妻？分已供個化誤估殺有小趙島希閻雖洲。終僅唯歌自合獎多委對。的擔佈童然孩端非化錯妻貝充感部誤。來使港標李立策糟更露哥向。方東高範律界懂事。審表尊並且微讀自頻誤。", "己程明非等演。宣場解所幾本作歲報控。宣創古貝愈家降等上括大澳重因。供地爭閻際乃歸東回向席財言選。已產臨界馬升聯就解愈。占委增歲前工展史歐狀可現。楚仍休演會三終場集感。益東語桂狀未？於包政人末監。避極占身視日德時師建？綁推日樂爭去策排新席。得監世仍華獎悅情！集控與貝發的九李任歌語出督決府面。面然遭不就和桃估能端民品未其。誤臨洲督楚發？時別宣冕乃女這身！", "發決能結宣關佔不。規家包承題接南且如介己名團架！自走令唯力出研末。增讀古遭而訂灣悔女結國區。悔等成退當末力投效年降選議度面召。選冠而歷起過德期等屈正有避願趙財。工都通唐仍更。示其蘇花社將是諾佔府德佈經泰。召高去佈讀如演發謙他趙遭。反師海歸面這且品層程。貝集光查唯全關三能宣。府權根並女讀字聯加團版別。幾斷工信場政馬戰楚當電控！等錯地間女排記政球體可旨。", "文何所中內根民健際詩光子還專流報！德層題局新出虞師許道。斯度結活泰門報釋精創好壇？府導架廣明球願定言著閻情難用捨集！響感未唐也媒個而。問都莫告辭謀。數社孩序他獨？話府包斯名訂童正將出序審錯歸個屈。響邀語前供辭漢承終當。因語素佈流顯？宣後來妻電工接童陸亂法愈響令度出。雖當常急外際旨對並歌起加多教！廣九傳位問門？可銳益情精中尊部說釋詩小現二擔冕。"]
Faker::Lorem.paragraphs(1) #=> ["主部香躍透等許審。平時這薦外全確古缺使歐集活匯。充當監懂及將發與捨創簡據瑞光女限。棄充者說召愈許宣多廣！讓日退層澳台加雖低當架情古學況話。規唯解己技今全精他電著願注漢灣站。醒身重台將灣家精。系字楚泰究學等簡問這女一桂休。過辭光權遽制亞外遭媒開然民摩。又端避主點這。健近效樂乃前妻曹正法。的據子評願主視我！諾逾應標本架多部聞台懂休童釋。供歸商包佈灣通們而楚重海詩斷應會！", "益%己識家古從題聯他臘閻。釋簡醒錯顯策站史宣關提可。走明亂範識別詞佔。委都降據尊泰後綁詞合！精介銳辦希獨序薦系冕國冠？薦休長個選召投孩旨這在注流斷體現。言記影薦據出包錯臨視制優！情間僅介灣投身退謙南個源！和瑞要解學最譯週升史翻家增我。推全屈曹週上微漢。於仍回當介亞且顯。道增面走多平低展？選島限家控言局前回亞被虞童旨代沒。召童界包南控程內蘇產訂問願只。常上者也論中。未議委媒個部後休排更代殺外失監話。"]
Faker::Lorem.paragraphs(1, true) #=> ["業專釋應委分外中少加台譯急社。就前釋同間馬事者媒律發根。辦李站冰標失評曾。界擔質端二文。遭南微包自臨道糟活質好流？糟來與開唐團己赴國議曹捨德讀。旬臘據字澳優爭時注作。導缺赴到島近專建獎包素元活究起詞。委兩和作斷降訂視局冰頻投臘導？問言許入一書範過正對。還產爭集低事。逾爭優漢架反從由？莫合難長幾演量的記有層現！網投期與爭規。表余斯序可宣文活前傳壇化。對立解亞時也聞詩集識。", "媒一遭專多治名虞現委論明審就廣詩？增我與童示二。也話優當身唯起後可記！簡恩歌桃寫末香別兩站看週？承堅演詩電以？科沒詞審且委後看接瑞。謙與由謀師貝而海訂爭和技。狀利致我球聞經對唐亂露由。學希應反商冰非講小版避組。產末與科缺臨。冰棄件辭讀狀來獨沒歌難表殺提到們。等寫赴更週工桂令升話二亂個策。諾低者序欠性自屈關使記規謀示也表。入策走奬席近充任島何社被加因殺規。趙期體演球面一位建於西報。譯內和召斯簡作才仍充。"]
```

###Faker::Name (fork edit)

```ruby

Faker::Name.name #=> "懷鈺婷"

Faker::Name.first_name #=> "家銘"

Faker::Name.last_name #=> "藺"

Faker::Name.prefix #=> ""

Faker::Name.suffix #=> "女士"

Faker::Name.title #=> "資深安全組長"

```

###Faker::Avatar

```ruby

Faker::Avatar.image #=> "http://robohash.org/sitsequiquia.png?size=300x300"

Faker::Avatar.image("my-own-slug") #=> "http://robohash.org/my-own-slug.png?size=300x300"

Faker::Avatar.image("my-own-slug", "50x50") #=> "http://robohash.org/my-own-slug.png?size=50x50"

Faker::Avatar.image("my-own-slug", "50x50", "jpg") #=> "http://robohash.org/my-own-slug.jpg?size=50x50"

Faker::Avatar.image("my-own-slug", "50x50", "bmp") #=> "http://robohash.org/my-own-slug.bmp?size=50x50"
```

###Faker::Number

```ruby

# Required parameter: digits
Faker::Number.number(10) #=> "1968353479"

Faker::Number.digit #=> "1"

```

###Faker::PhoneNumber (fork edit)

```ruby

Faker::PhoneNumber.phone_number #=> "7673800545"

Faker::PhoneNumber.cell_phone #=> "753.573.7204"

Faker::PhoneNumber.subscriber_number #=> "4481"

Faker::PhoneNumber.subscriber_number(2) #=> "63"

Faker::PhoneNumber.extension #=> "4317"

```

###Faker::Time
---------------------

```ruby
# Random date between dates
Faker::Time.between(2.days.ago, Time.now) #=> "2014-09-18 12:30:59 -0700"

# Random date between dates (within specified part of the day)
Faker::Time.between(2.days.ago, Time.now, :all) #=> "2014-09-19 07:03:30 -0700"
Faker::Time.between(2.days.ago, Time.now, :day) #=> "2014-09-18 16:28:13 -0700"
Faker::Time.between(2.days.ago, Time.now, :night) #=> "2014-09-20 19:39:38 -0700"
Faker::Time.between(2.days.ago, Time.now, :morning) #=> "2014-09-19 08:07:52 -0700"
Faker::Time.between(2.days.ago, Time.now, :afternoon) #=> "2014-09-18 12:10:34 -0700"
Faker::Time.between(2.days.ago, Time.now, :evening) #=> "2014-09-19 20:21:03 -0700"
Faker::Time.between(2.days.ago, Time.now, :midnight) #=> "2014-09-20 00:40:14 -0700"

# Random time in the future (up to maximum of N days)
Faker::Time.forward(23, :morning) # => "2014-09-26 06:54:47 -0700"

# Random time in the past (up to maximum of N days)
Faker::Time.backward(14, :evening) #=> "2014-09-17 19:56:33 -0700"
```

###Faker::Hacker
---------------------
Are you having trouble writing tech-savvy dialogue for your latest screenplay?
Worry not! Hollywood-grade technical talk is ready to fill out any form where you need to look smart.

```ruby
# Full Phrase
Faker::Hacker.say_something_smart #=> "Try to compress the SQL interface, maybe it will program the back-end hard drive!"

# Short technical abbreviations
Faker::Hacker.abbreviation  #=> "RAM"

# Hacker centric adjectives
Faker::Hacker.adjective   #=> "open-source"

# Only the best hacker related nouns
Faker::Hacker.noun   #=> "bandwidth"

# Actions that hackers take
Faker::Hacker.verb  #=> "bypass"

# Verbs that end in -ing
Faker::Hacker.ingverb #=> "synthesizing"
```

###Faker::App
-----------------

```ruby

Faker::App.name #=> "Treeflex"

Faker::App.version #=> "0.7.9"

Faker::App.author #=> "Daphne Swift"

```

Customization
------------
Since you may want to make addresses and other types of data look different
depending on where in the world you are (US postal codes vs. UK postal codes,
for example), Faker uses the I18n gem to store strings (like state names) and
formats (US postal codes are NNNNN while UK postal codes are AAN NAA),
allowing you to get different formats by switching locales.  Just set
Faker::Config.locale to the locale you want, and Faker will take care of the
rest.

If your locale doesn't already exist, create it in the \lib\locales\ directory
and you can then override or add elements to suit

```yaml

en-au-ocker:
  faker:
    name:
      # Exiting faker field, new data
      first_name: [Charlotte, Ava, Chloe, Emily]

      # New faker fields
      ocker_first_name: [Bazza, Bluey, Davo, Johno, Shano, Shazza]
      region: [South East Queensland, Wide Bay Burnett, Margaret River, Port Pirie, Gippsland, Elizabeth, Barossa]

```

Contributing
------------
See [CONTRIBUTING.md](https://github.com/stympy/faker/blob/master/CONTRIBUTING.md).

Contact
-------
Comments and feedback are welcome. Send an email to Benjamin Curtis via the [google group](http://groups.google.com/group/ruby-faker).

License
-------
This code is free to use under the terms of the MIT license.
