# The 123 motions

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

## Added 2026-11-05: showreel, launch and HyperFrames motions (55)

`showreel` = a component of the webastra-showreel template (Remotion). `launch` = a product-launch-motion technique (pure seek(t), closed-form springs). `hyperframes` = a template of hyperframes-motion-library (HTML; render transparent and overlay, or rebuild in Remotion).

### حركة الكاميرا (`cam`) — 1

- **push-to-ui** — الكاميرا كتقرب على عنصر حتى يعمر الكادر، ومن بعد كترجع للصورة كاملة — مزيانة ل: تبيين تفصيلة فواجهة
  - launch — `product-launch-motion` technique: camera Tracks (x, y, log-zoom) push so the element fills the frame, then pull back (closed-form springs, pure seek(t)).

### النص والعناوين (`text`) — 3

- **clock-roll** — ساعة كبيرة كتدور الأرقام ديالها حتى كتوقف على الوقت (23:39) — مزيانة ل: وقت محدد، الليل، الاستعجال
  - showreel — `webastra-showreel` component NightOver (reel-26 scenes26.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **odometer** — أرقام كتدور بحال عداد الطوموبيل، كل رقم كيتحرك غير ملي كيدوز اللي تحتو — مزيانة ل: أرقام حقيقية كبيرة (زبناء، رسائل)
  - launch — `product-launch-motion` technique: per-digit strips 0–9, a digit moves only while the one below carries (closed-form springs, pure seek(t)).
- **stream-reply** — جواب الـ AI كيبان كلمة بكلمة مع ضبابة خفيفة، بحال اللي كيكتب دابا — مزيانة ل: ردود البوت والذكاء الاصطناعي
  - launch — `product-launch-motion` technique: reply words revealed one by one with a short blur; the agent cursor follows the last word (closed-form springs, pure seek(t)).

### كروت وواجهات (`ui`) — 13

- **step-hud** — شريط أيقونات صغير فالفوق: الخطوة الحالية كبيرة واللي سالاو عليهم ✓ — مزيانة ل: ريل فيه لائحة مرقمة
  - showreel — `webastra-showreel` component StepHud (Showreel.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **prompt-score** — فكرة كتتكتب، كارطة AI كتجاوب، 3 سطور بأشرطة كتعمر والأحسن كيتختم — مزيانة ل: نتائج AI، مقارنات وتقييم
  - showreel — `webastra-showreel` component Script + ScoreRow; reuse it in Remotion, each beat keyed to a spoken word with say().
- **timeline-panel** — تايملاين ديال المونتاج فوق الفيديو: track لكل كلمة والـ playhead كيمشي — مزيانة ل: شرح المونتاج والـ workflow
  - showreel — `webastra-showreel` component Edit + TRACKS; reuse it in Remotion, each beat keyed to a spoken word with say().
- **brand-flip** — 3 سلايدات بستايلات مختلفة كيتقلبو وحدة وحدة للهوية ديال البراند — مزيانة ل: الهوية، قبل وبعد التصميم
  - showreel — `webastra-showreel` component Carousel + Slide/OFF; reuse it in Remotion, each beat keyed to a spoken word with say().
- **agent-hub** — روبوت فالوسط وخطوط متقطعة كتمشي فيها نقط لتليفون WhatsApp وللموقع — مزيانة ل: الأتمتة والربط بين الأدوات
  - showreel — `webastra-showreel` component Agent + Bubble/Typing; reuse it in Remotion, each beat keyed to a spoken word with say().
- **post-cta** — بوست إنستغرام: الحفظ كيتعمر، الشير كيطير لصاحب، والتعليق كيتكتب — مزيانة ل: CTA ديال save/share/comment
  - showreel — `webastra-showreel` component Cta; reuse it in Remotion, each beat keyed to a spoken word with say().
- **live-chat** — محادثة WhatsApp: الرسالة كتتكتب حرف بحرف وكتتصيفط، والرد كيبان كلمة بكلمة — مزيانة ل: ديمو ديال بوت ولا محادثة حقيقية
  - showreel — `webastra-showreel` component Chat (reel-26 scenes26.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **summary-to-ticket** — بطاقة ملخص: كل سطر كيتعلم ✓، ومن بعد كتتحول لتذكرة خضرا «تم الحجز» — مزيانة ل: تأكيد حجز ولا طلب
  - showreel — `webastra-showreel` component Booking (reel-26 scenes26.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **flag-tiles** — بطاقات بالأعلام كيتشعلو وحدة وحدة مع اسم كل بلد — مزيانة ل: اللغات، اللهجات، البلدان
  - showreel — `webastra-showreel` component Dialects (reel-26 scenes26.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **share-send** — نافذة «رسل لـ…»: كتعلم على صاحبك والبوطونة كتولي «تم الإرسال» — مزيانة ل: CTA ديال الشير
  - showreel — `webastra-showreel` component Send (reel-26 scenes26.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **slide-to-confirm** — زر كيتسحب للتأكيد: القيمة كتبع اليد والزر كيتمدد شوية ملي كيتجر — مزيانة ل: تأكيد، دفع، «نعم أكيد»
  - launch — `product-launch-motion` technique: while held, knob x = cursor x; it stretches with speed; springs back on release (closed-form springs, pure seek(t)).
- **stretch-toggle** — سويتش: الكرة ديالو كتتمدد ملي كتمشي (الجهة القدامية كتسبق) — مزيانة ل: تشعيل ميزة، تذكير، Autopilot
  - launch — `product-launch-motion` technique: edge-split: leading edge on a stiff spring, trailing on a soft one (width = R − L) (closed-form springs, pure seek(t)).
- **liquid-tabs** — مؤشر التابات كيتمدد بحال السائل من تاب لتاب — مزيانة ل: مراحل، أقسام، قبل/بعد
  - launch — `product-launch-motion` technique: same edge-split as the toggle, across tab positions (closed-form springs, pure seek(t)).

### تكوين الكادر (`frame`) — 1

- **face-travel** — الوجه كيتنقل بين الشاشة كاملة، كارطة تحت وإطار صغير، بتلفة خفيفة — مزيانة ل: ريل كامل بالموشن حول الوجه
  - showreel — `webastra-showreel` component Face + KEYS (FULL/CARD/PIP); reuse it in Remotion, each beat keyed to a spoken word with say().

### الانتقالات (`trans`) — 3

- **gradient-swipe** — شريط gradient مايل كيقطع الشاشة فكل تبدال ديال فكرة — مزيانة ل: الانتقال بين المشاهد فالستايل ديالكم
  - showreel — `webastra-showreel` component Swipe (Showreel.tsx); reuse it in Remotion, each beat keyed to a spoken word with say().
- **one-shape** — شكل واحد كيتحول من حالة لحالة (زر → دائرة → كارطة) بلا حتى قطع — مزيانة ل: فيديو إطلاق منتوج ولا تطبيق
  - launch — `product-launch-motion` technique: one element whose size, radius and colour ride springs between states; content swaps inside it (closed-form springs, pure seek(t)).
- **blur-swap** — المحتوى داخل الكارطة كيتبدل بضبابة قصيرة، والكارطة باقية فبلاصتها — مزيانة ل: تبدال النص ولا الأرقام بلا قطع
  - launch — `product-launch-motion` technique: vis(): enter on a spring, exit short and early with blur 10px (closed-form springs, pure seek(t)).

### لمسات (`acc`) — 7

- **stopwatch-slam** — ساعة توقيف كتطيح كبيرة وكتضرب مع رعشة، العقرب كيدور وكيحمار — مزيانة ل: الوقت والتكلفة اللي كتضيع
  - showreel — `webastra-showreel` component Stopwatch (Hook); reuse it in Remotion, each beat keyed to a spoken word with say().
- **orbit-birth** — أيقونات كيتولدو من ورا أيقونة كبيرة، كيطيرو فقوس وكيدورو عليها — مزيانة ل: لائحة حوايج كتديرهم أداة وحدة
  - showreel — `webastra-showreel` component Hook ORBIT + EMERGE_GAP; reuse it in Remotion, each beat keyed to a spoken word with say().
- **rec-tag** — REC أحمر كيرمش على الفيديو حدا الراس — مزيانة ل: قبل التصوير، live، حالة على الفيديو
  - showreel — `webastra-showreel` component RecTag; reuse it in Remotion, each beat keyed to a spoken word with say().
- **letters-to-mic** — الحروف كيطيرو فقوس للميكرو وكتولي موجة صوت — مزيانة ل: نص كيتحول لصوت، أي تحويل
  - showreel — `webastra-showreel` component Voice + Wave; reuse it in Remotion, each beat keyed to a spoken word with say().
- **brand-cursor** — cursor بلون البراند مع اسمو (Web Astra AI) كيتحرك، كيميل مع السرعة وكيضغط — مزيانة ل: الـ AI كيخدم بوحدو قدام الناس
  - launch — `product-launch-motion` technique: gradient arrow + name pill, lean = -vx·0.0045, pill trails the velocity (closed-form springs, pure seek(t)).
- **click-ripple** — ضغطة حقيقية: الزر كيتزير شوية وموجة كتخرج من تحت الـ cursor — مزيانة ل: كل كليك فالديمو
  - launch — `product-launch-motion` technique: press scale 1−0.16·exp(−((t−tc)/0.045)²) + 0.4 s ring (closed-form springs, pure seek(t)).
- **logo-slam** — اللوجو كيتجمع قطعة قطعة وكيضرب على الإيقاع مع موجة — مزيانة ل: النهاية ولا بداية البراند
  - launch — `product-launch-motion` technique: logo parts fly in on springs and land on a beat, ring on the hit (closed-form springs, pure seek(t)).

### أرقام ومبيانات (`data`) — 13

- **bar-chart-grow** — 3 حتى 7 ديال الأعمدة كيطلعو من التحت مع الأرقام — مزيانة ل: مقارنة النتائج
  - hyperframes — template `templates/bar-chart-grow` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **ring-counter** — رقم كبير كيتحسب من 0 مع دائرة ديال التقدم داير بيه — مزيانة ل: إنجاز، KPI، مجموع
  - hyperframes — template `templates/number-counter` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **line-chart-draw** — خط كيترسم من اليسار لليمين والنقط كيطلعو وحدة وحدة — مزيانة ل: التطور مع الوقت
  - hyperframes — template `templates/line-chart-draw` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **metric-pulse** — رقم واحد كبير كينبض مع ضو، وتحتو شنو كيعني — مزيانة ل: نتيجة وحدة قوية
  - hyperframes — template `templates/metric-pulse` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **big-number-card** — كارطة فيها رقم ضخم وجملة وحدة كتشرحو — مزيانة ل: الخلاصة: الوقت، التكلفة، الربح
  - hyperframes — template `templates/big-number-card` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **before-after-stat** — رقمين: قبل وبعد، والفرق كيبان واضح — مزيانة ل: تحسين بأداة ولا طريقة جديدة
  - hyperframes — template `templates/before-after-stat` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **horizontal-bar-compare** — جوج أشرطة أفقية كيتمدو: الطريقة القديمة ضد الجديدة — مزيانة ل: مقارنة جوج أدوات
  - hyperframes — template `templates/horizontal-bar-compare` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **top-rank-list** — ترتيب Top 3: كل سطر كيطلع بوحدو مع رقمو — مزيانة ل: أحسن 3 أدوات ولا أسباب
  - hyperframes — template `templates/top-rank-list` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **turning-point-line** — خط الاتجاه كيترسم ونقطة التحول كتضوي — مزيانة ل: اللحظة اللي تبدل فيها كلشي
  - hyperframes — template `templates/turning-point-line` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **compact-number-callout** — رقم كبير وجملة وحدة عامرين الشاشة كاملة — مزيانة ل: لحظة الرقم الصادم
  - hyperframes — template `templates/compact-number-callout` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **donut-progress** — دائرة كتعمر حتى النسبة والرقم فالوسط كيتحسب — مزيانة ل: نسبة، احتمال، حصة
  - hyperframes — template `templates/donut-progress` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **stat-duel** — جوج أرقام وجه لوجه فالتحت ديال الفيديو، شفافين فوق التصوير — مزيانة ل: مقارنة فوق الهضرة
  - hyperframes — template `templates/stat-duel` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **number-impact** — كلمة ضخمة ونسبة مع مسطرة كتضرب بقوة فوق الفيديو — مزيانة ل: رقم كيصدم فوسط الهضرة
  - hyperframes — template `templates/number-impact` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.

### شرح الأفكار (`explain`) — 14

- **source-citation-card** — كارطة صغيرة لتحت فيها المصدر، التاريخ والرقم — مزيانة ل: تزيد المصداقية لأي رقم
  - hyperframes — template `templates/source-citation-card` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **status-split** — الشاشة كتقسم: العادي ضد غير العادي، ولا قبل ضد دابا — مزيانة ل: لحظة التحول فالقصة
  - hyperframes — template `templates/status-split` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **concept-spotlight** — كارطة زجاجية فيها سمية المفهوم وجملة كتشرحو — مزيانة ل: تشرح كلمة تقنية (AI Agent، API…)
  - hyperframes — template `templates/concept-spotlight` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **three-step-flow** — 3 خطوات على خط تقدم، كل وحدة كتضوي فدورها — مزيانة ل: طريقة من 3 خطوات
  - hyperframes — template `templates/three-step-flow` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **myth-fact-swap** — الخرافة كتتشطب بالأحمر وكتتبدل بالحقيقة — مزيانة ل: «الكل كيقول… ولكن الحقيقة»
  - hyperframes — template `templates/myth-fact-swap` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **key-point-marker** — جملة مهمة لتحت مع خط صغير كيخرجها — مزيانة ل: الخلاصة ولا جملة كتنحفظ
  - hyperframes — template `templates/key-point-marker` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **checklist-pop** — 3 نقط كيدخلو وحدة وحدة وكيتعلمو ✓ — مزيانة ل: ملخص الخطوات ولا الأشياء اللي خاصك
  - hyperframes — template `templates/checklist-pop` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **timeline-scan** — 3 محطات فالزمن كيضويو وحدة وحدة على طريق — مزيانة ل: مراحل، تطور، تاريخ
  - hyperframes — template `templates/timeline-scan` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **cause-chain** — سبب ← آلية ← نتيجة، 3 كروت مربوطين بالسهام — مزيانة ل: علاش كيوقع هادشي
  - hyperframes — template `templates/cause-chain` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **mode-choice-compare** — جوج خيارات قد قد مع VS فالوسط — مزيانة ل: يدوي ولا أوتوماتيك، أداة ولا أداة
  - hyperframes — template `templates/mode-choice-compare` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **iteration-loop** — 4 خطوات فدورة: المشكل ← الإصلاح ← المحاولة ← النتيجة — مزيانة ل: التحسين المستمر، المراجعة
  - hyperframes — template `templates/iteration-loop` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **keyword-blast** — كلمة ضخمة كتنفجر من الوسط مع موجة وضو — مزيانة ل: الهوك، التحول فالرأي
  - hyperframes — template `templates/keyword-blast` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **chapter-title** — رقم الفصل ضخم مع العنوان، صفحة كاملة — مزيانة ل: تقسيم فيديو طويل لأجزاء
  - hyperframes — template `templates/chapter-title` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
- **quote-card** — كارطة فيها علامة اقتباس كبيرة، الجملة والسمية ديال صاحبها — مزيانة ل: جملة ديال زبون، كتاب ولا رأي
  - hyperframes — template `templates/quote-card` in `hyperframes-motion-library`: render it transparent (MOV/WebM) and overlay it, or rebuild it in Remotion in the Web Astra colours.
