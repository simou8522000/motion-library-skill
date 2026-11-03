# The 68 motions

Each entry: **id** — what it looks like (Darija) — what it is good for — how to make it.

`/effects` = rendered on real footage by the effects skill: `fx.py <id> <video> <out.mp4> --start S --end E --text "..." --opt key=value`. Options are listed. `classic` = build it in Remotion (or ffmpeg) with the recipe given.

## ورا الراس (`back`) — 13

- **noise** — الريلز ديالك كيطيحو وكيتكدسو ورا راسك — مزيانة ل: تبيين الخدمة ديالك وبورتفوليو
  - `/effects` — options: images, size
- **orbit** — الريلز كيدورو على راسك، ورا منك فالفوق وقدامك فالتحت — مزيانة ل: بورتفوليو بطريقة فخمة
  - `/effects` — options: images, count, speed, size
- **backdrop-word** — كلمة كبيرة كتطيح ورا منك (كيسميوها حتى text behind subject) — مزيانة ل: الكلمة المفتاح ديال الفكرة
  - `/effects` — options: text, color, font (bold | serif)
- **shortcut-rain** — أزرار الكلافيي كيطيحو بحال الشتا ورا منك — مزيانة ل: التيك، الاختصارات والأدوات
  - `/effects` — options: text (keys with |), count
- **rabbit-hole** — البيت كيتحول نفق ورا منك — مزيانة ل: تدخل فموضوع عميق
  - `/effects` — options: ratio, speed, spin
- **headline-wall** — عناوين كيتكدسو ورا راسك، ومن بعد رقم كيبان قدامك — مزيانة ل: الدليل الاجتماعي والأخبار
  - `/effects` — options: text (headline::meta|…), total, label
- **carousel-spin** — الريلز كيدورو عليك بحال كاروسيل 3D — مزيانة ل: بورتفوليو
  - `/effects` — options: images, count, size, turns
- **match-cut** — صفحات أخبار كيتبدلو على نفس الكلمة، والكلمة ثابتة فبلاصتها — مزيانة ل: ترند كيهضرو عليه الكل
  - `/effects` — options: text, color
- **led-sign** — الضو كيطفا ولافتة LED كتكتب راسها ورا منك — مزيانة ل: جو ليلي واسم البراند
  - `/effects` — options: text, color, push
- **profile-wall** — شبكة الريلز كتعمر الحيط والعداد كيطلع — مزيانة ل: النتائج وعدد الفولوورز
  - `/effects` — options: images, count, label
- **red-collage** — نتا بالأبيض والكحل، كلمة حمرا كبيرة ورا منك، و3 سطور كيضربو — مزيانة ل: Hook قوي بستايل بوستر
  - `/effects` — options: text, lines, tag
- **pastel-word** — بيت لون الخزامى، كلمة كبيرة ورا منك، وكارطة بروفايل كتتبّع — مزيانة ل: براند ناعم ورزين
  - `/effects` — options: text, name, handle
- **check-pills** — ورق مربعات، الريلز ديالك ملصقين ورا منك، وأزرار زرقا كيتكليكاو — مزيانة ل: الخدمات والاختيارات
  - `/effects` — options: text (pills with |), images

## حركة الكاميرا (`cam`) — 8

- **locked-on** — أقواس كيتسدّو على وجهك والكاميرا كتبعك — مزيانة ل: بداية الفيديو والـHook
  - `/effects` — options: zoom (1.35), text
- **lean-in** — زوم سريع على كلمة وحدة — مزيانة ل: تأكيد كلمة مهمة
  - `/effects` — options: zoom (1.45, max 2), speed
- **slow-push** — زوم سينمائي بطيء والبيت كيضبّب — مزيانة ل: لحظة عاطفية
  - `/effects` — options: zoom (1.6), blur
- **over-the-shoulder-zoom** — زوم لزاوية مع مبيان زجاجي، من بعد الزاوية الأخرى مع مبيان ثاني — مزيانة ل: مقارنة رقمين
  - `/effects` — options: text (2 labels), to (197K|672K), zoom
- **camera-shake** — الكاميرا كترعد مع الضربة — مزيانة ل: لحظة صادمة أو خبر قوي
  - classic — Remotion: on the hit frame, offset the whole layer with a decaying noise, e.g. x=sin(f*1.9)*A*exp(-f/6), A≈14px, 8-12 frames. Pair with a hit SFX.
- **jump-cut** — قطع مباشر مع تبديل حجم اللقطة بين الجمل — مزيانة ل: حيد الصمت والتنفس بلا ما يبان
  - classic — Cut on the silences (pause-cut), and alternate scale 1.0 / 1.18 between takes with transform-origin on the face so cuts read as intentional.
- **parallax** — الطبقات كيتحركو بسرعات مختلفة فيعطيو عمق — مزيانة ل: إحساس 3D فلقطة عادية
  - classic — Split into 2-3 layers (background, person via matte, foreground) and move them with the same eased curve at different amplitudes (3%, 8%, 20%).
- **ken-burns** — زوم وتحريك بطيء على صورة ثابتة — مزيانة ل: تحريك الصور والسكرينات
  - classic — Still image: interpolate scale 1.0→1.12 and translate a few % over the shot with easeInOut. Never on the face video itself.

## النص والعناوين (`text`) — 10

- **kinetic-typography** — الكلمات كيطلعو وحدة بوحدة مع الصوت — مزيانة ل: السبتايتلز ديال كل ريل
  - classic — Word timings from Whisper (words.py / align_words.py); each word springs in (scale 0.6→1, opacity) on its own start frame; the key word gets the accent colour.
- **typewriter** — النص كيتكتب حرف بحرف بحال الماشينة — مزيانة ل: سؤال أو فكرة كتشد
  - classic — Reveal characters with Math.floor(progress*text.length) plus a blinking caret; for Arabic reveal whole words (letters change shape when cut).
- **karaoke-captions** — كل كلمة كتضوي فاش كتقولها — مزيانة ل: سبتايتلز كيشدو العين
  - classic — Show the full line; the word being spoken gets a coloured pill behind it (interpolate background between its start and end frame).
- **mask-reveal** — النص كيبان من ورا قناع كيتمسح — مزيانة ل: العناوين والأسماء
  - classic — Wrap the title in overflow:hidden and wipe it in with clip-path inset() from 100% to 0% over ~10 frames, ease out.
- **highlight-marker** — ماركر أصفر كيدوز تحت الكلمات المهمة — مزيانة ل: تأكيد جملة
  - classic — A yellow bar behind the words (background-size 0%→100% on the key phrase), 12-15 frames, starting when the phrase is spoken.
- **number-counter** — رقم كبير كيتحسب حتى كيوصل للنتيجة — مزيانة ل: الإحصائيات والنتائج
  - classic — interpolate(frame,[start,start+40],[0,target]) with an ease-out, Math.round, tabular-nums font; land the final value on a beat.
- **text-scramble** — الحروف كيتخلطو ومن بعد كيستقرو على الكلمة — مزيانة ل: التيك واسم البراند
  - classic — For N frames replace each letter with a random glyph (seeded by frame), then lock letters left to right onto the real word. Latin text only.
- **lower-third** — شريط فيه الاسم والصفة فالتحت — مزيانة ل: تقديم الشخص اللي كيهضر
  - classic — Two bars (name + role) slide in from the side with 4-frame stagger, hold 2-3 s, slide out. Keep inside the safe area above captions.
- **headline-box** — زوم مع عنوان نقي فسطرين — مزيانة ل: Hook فأول ثانية
  - `/effects` — options: text (2 lines), zoom
- **split-headline** — كارطة عنوان كتهبط وكتدفعك للنص التحتاني — مزيانة ل: عنوان خبر أو موضوع
  - `/effects` — options: text, hl, pill

## كروت وواجهات (`ui`) — 13

- **lineup** — كروت مرقمة كيتفرشو فوق راسك — مزيانة ل: لائحة ديال خطوات أو أسباب
  - `/effects` — options: text (a|b|c)
- **the-bill** — التعليمات ديالك كتطبع بحال بون ديال الحانوت — مزيانة ل: خطوات أو عرض بالثمن
  - `/effects` — options: text (lines with |)
- **todo** — لائحة مهام حدا راسك كتشيك مع الكلام — مزيانة ل: شرح خطوات
  - `/effects` — options: text (items with |), ticks, title
- **checklist** — لائحة مهام تحت الذقن، كل خطوة كتخضار — مزيانة ل: شرح عملية خطوة بخطوة
  - `/effects` — options: text (step::meta|…), title
- **comment-box** — كومنتير ديال إنستغرام كيتكتب وكيتنشر — مزيانة ل: جواب على سؤال ديال متابع
  - `/effects` — options: text
- **tap** — بوطونة Follow كتولي Following — مزيانة ل: CTA فالآخر ديال الفيديو
  - `/effects` — options: at, x, y, color
- **messages** — إشعارات iMessage كيبانو وحدة ورا وحدة بضو خفيف — مزيانة ل: رسائل الكليان والطلبات
  - `/effects` — options: text (messages with |), title, y
- **apple-toggles** — سويتشات آيفون كيتشعلو تحت الذقن سطر بسطر — مزيانة ل: مميزات خدمة
  - `/effects` — options: text (rows with |), ticks, color, pos=below
- **glass-widgets** — ويدجتس زجاجية ضبابية كيعومو حدا راسك — مزيانة ل: الأرقام، الأدوات والتيك
  - `/effects` — options: text, name, handle, look=simple
- **liquid-glass-graph** — كارطة زجاج فيها مبيان كيطلع ورقم كيتحسب — مزيانة ل: النتائج والأرقام
  - `/effects` — options: text, from, to, color · look=bento
- **countdown-flip** — ساعة كتقلب 3، 2، 1 فوق راسك — مزيانة ل: العد التنازلي والتشويق
  - `/effects` — options: from
- **tier-list** — Tier list كتطيح وحاجة كتطير مباشرة لـS — مزيانة ل: مقارنة أدوات أو خدمات
  - `/effects` — options: title, item, others
- **progress-bar** — شريط فالفوق كيعمر مع الفيديو — مزيانة ل: يخلي الناس يكملو حتى للآخر
  - classic — A thin bar at the top whose width = frame/durationInFrames. Brand colour, 6-8px.

## تكوين الكادر (`frame`) — 8

- **reel-frame** — الفيديو كيصغر ويولي كارطة ديال ريل — مزيانة ل: تهضر على ريل أو محتوى
  - `/effects` — options: text (handle)
- **place-in-grid** — كتصغر لوسط شبكة البروفايل، والريلز كيبانو داير بيك بالمشاهدات — مزيانة ل: تقديم الحساب ديالك
  - `/effects` — options: images, views (9 counts)
- **phone-fan** — الريلز كيتفرشو بحال الكارطة فاليد — مزيانة ل: عرض بزاف ديال الأعمال
  - `/effects` — options: images, text
- **cover-star** — كتولي غلاف ديال مجلة — مزيانة ل: قصة نجاح أو تقديم شخص
  - `/effects` — options: text, lines, issue, color · look=editorial
- **broll-split** — B-roll فالفوق مع ستيكر ديال الثمن، ونتا تحت — مزيانة ل: عرض منتوج بثمنو
  - `/effects` — options: images, text (tag)
- **picture-in-picture** — وجهك كيصغر فإطار صغير فوق الشاشة — مزيانة ل: شرح موقع أو تطبيق
  - classic — Face video scaled to ~32% in a rounded card with shadow over the full-screen content; spring the card in and out when the content starts/ends.
- **split-screen** — الكادر كيتقسم: المحتوى فالفوق ونتا تحت — مزيانة ل: ديمو مع الهضرة
  - classic — Content on the top half, face on the bottom half; the captions sit on the seam between the two halves (splitAt() drives both).
- **swipe** — سلايدر ديال قبل وبعد — مزيانة ل: نتيجة الخدمة ديالك
  - `/effects` — options: grade

## الانتقالات (`trans`) — 8

- **whip-pan** — الكادر كيتجبد بسرعة لجنب مع بلور — مزيانة ل: الانتقال بين جوج لقطات
  - classic — Translate the outgoing shot 0→-100% and the incoming 100%→0% over 6-8 frames with directional motion blur (blur filter or sample frames). Add a whoosh.
- **zoom-transition** — زوم داخل اللقطة كيدخلك للقطة الجاية — مزيانة ل: انتقال قوي بين فكرتين
  - classic — Scale the outgoing shot up to ~3x into a point while fading to the next shot, which starts at 0.6x and springs to 1.
- **glitch-transition** — تخربيق ديجيتال بين جوج لقطات — مزيانة ل: التيك والمفاجأة
  - classic — 3-6 frames of RGB split (offset copies with mix-blend screen), horizontal slice offsets and noise between the two shots; glitch SFX.
- **circle-wipe** — اللقطة الجديدة كتبان من دائرة كتكبر — مزيانة ل: انتقال ناعم
  - classic — Incoming shot masked with clip-path circle(r at x y), r from 0 to 150% over 12-15 frames, ease in-out.
- **slide-push** — اللقطة الجديدة كتدفع القديمة لفوق — مزيانة ل: الانتقال بين الأفكار
  - classic — Incoming shot pushes the old one up: both translateY together over 10 frames with an eased curve.
- **light-leak** — تسرب ديال ضو دافي كيدوز فالكادر — مزيانة ل: جو دافي وانتقال ناعم
  - classic — An orange/pink radial gradient layer with mix-blend screen sweeping across the frame over 15-20 frames, peak opacity ~0.7 on the cut.
- **dot-reveal** — اللقطة كتبنى من نقط مضوية ومن بعد كتوضح — مزيانة ل: بداية فخمة
  - `/effects` — options: color, cell
- **uninstall** — شريط Uninstall مخربق كيكسر الكادر — مزيانة ل: تخلص من عادة أو أداة قديمة
  - `/effects` — options: text

## اللون والإضاءة (`look`) — 4

- **moody** — تلوين سينمائي غامق — مزيانة ل: قصة ومزاج درامي
  - `/effects` — options: grade (moody, bw, warm, cool, pop)
- **spotlight** — الضو كيطفا وكتبقى غير نتا مضوي — مزيانة ل: لحظة جدية أو سر
  - `/effects` — options: text, color, push · look=sparkle (glitter-spotlight)
- **timeline** — لوك فيلم أحمر غامق مع تايملاين ديال المونتاج — مزيانة ل: تهضر على المونتاج
  - `/effects` — options: text, sub, tc
- **pause-point** — الصورة كتوقف ومعاها سهم مرسوم باليد — مزيانة ل: تشير لتفصيل مهم
  - `/effects` — options: text, color, label_x

## لمسات (`acc`) — 4

- **reject-stamp** — طابع أحمر كبير كيطيح بقوة — مزيانة ل: غلطة أو حاجة ممنوعة
  - `/effects` — options: text, color, angle, y
- **scribble** — رسومات بالماركر كيترسمو بوحدهم داير بيك — مزيانة ل: ستايل عفوي وخفيف
  - `/effects` — options: text, color
- **icon-pop** — أيقونات 3D كيطلعو بقفزة حدا الكلام — مزيانة ل: توضيح كل فكرة بصورة
  - classic — Colored 3D icon (iconify-icons skill) springs in next to the spoken word: scale 0→1.1→1, small rotation, pop SFX; out with scale down.
- **motion-path** — خط متقطع كيترسم ونقطة كتمشي عليه من فكرة لفكرة — مزيانة ل: ربط فكرة بفكرة (فالستايل ديالكم)
  - classic — Draw a dashed SVG path with strokeDashoffset, then move a dot/arrow along it with getPointAtLength; links one idea card to the next (Web Astra house style).
