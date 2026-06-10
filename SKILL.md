---
name: ai-video-prompt-craft
description: Use when writing, improving, or learning AI video-generation prompts for cinematic work. Distills user-provided examples into reusable camera, scene, motion, lighting, style, and film-language patterns.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [ai-video, prompt-engineering, cinematography, directing, camera, lighting, scene-staging]
    related_skills: [comfyui, youtube-content]
---

# AI Video Prompt Craft

## Overview

Use this skill as the user's durable AI-video prompt stylebook. The user will provide strong examples from video-generation sites and wants the assistant to learn them across sessions. Do **not** merely memorize raw text; extract reusable directing logic: scene intent, camera language, subject motion, environment motion, lighting, texture, color, editing rhythm, and model-friendly wording.

Default persona for these tasks: professional director with film-industry vocabulary, strong visual taste, and practical control over camera movement, scene staging, motion, light, and style.

## When to Use

Load this skill whenever the user asks for any of the following:

- “帮我写 AI 视频提示词 / 视频生成提示词 / 运镜提示词”
- Learning, analyzing, or imitating a good AI-video case
- Turning an image/story/idea into a cinematic video prompt
- Designing shot lists, scene prompts, or multi-shot AI video sequences
- Improving prompt clarity for motion control, camera control, lighting, or style consistency

Do not use for unrelated image-only prompts unless the user specifically wants motion/camera/video language.

## Prompt Construction Principles

A strong AI-video prompt should usually contain these layers, in this order:

1. **主体与场景** — who/what appears, where, era/worldview, key props.
2. **动作与状态变化** — one clear primary action, optionally one secondary environmental motion.
3. **镜头语言** — shot size, lens feel, angle, camera movement, focus behavior.
4. **场景调度** — foreground/midground/background, blocking, entrances/exits, depth cues.
5. **光影与色彩** — key light direction, contrast, haze, palette, practical/neon/natural source.
6. **质感与风格** — filmic texture, material details, genre, reference mood, aspect ratio.
7. **节奏与情绪** — slow/urgent/ritualistic/dreamlike, suspense, awe, intimacy.
8. **约束** — avoid jitter, deformation, extra limbs, text artifacts, chaotic motion, over-cutting.

### One-Shot Prompt Formula

```text
[景别/镜头角度] of [主体] in/at [场景], [主体动作].
Camera [运镜方式] while [焦点/景深/前景遮挡/视差].
[光源方向与色彩], [环境运动], [材质细节].
Mood: [情绪]. Style: cinematic, [镜头/画幅/胶片/类型风格].
Negative: shaky, warped anatomy, flicker, random cuts, text artifacts.
```

Chinese compact form:

```text
[景别]，[主体]在[场景]中[动作]；镜头[运镜]，[焦点/景深/构图]；[光影色彩]，[环境运动]，[材质质感]；整体情绪[情绪]，电影感，[画幅/镜头/风格]；避免画面抖动、主体变形、无意义跳切和文字乱码。
```

### Multi-Shot Sequence Formula

For sequences, write a short **visual bible** first, then per-shot prompts:

```text
视觉基调：时代/世界观 + 色彩 + 光线 + 材质 + 镜头节奏。
角色一致性：外貌、服装、关键道具、动作习惯。
运动规则：每个镜头只控制一个主动作 + 一个镜头运动。

镜头 1（时长/景别/目的）：...
镜头 2（时长/景别/目的）：...
镜头 3（时长/景别/目的）：...
```

## Camera Language Reference

Prefer concrete film language over generic “cinematic”. Useful phrases:

- **建立空间**：wide establishing shot, extreme wide shot, high-angle vista, aerial drift
- **史诗压迫**：low-angle shot, towering scale, silhouette against sunset, slow push-in
- **亲密细节**：extreme close-up, macro detail, shallow depth of field, rack focus
- **跟随行动**：tracking shot, dolly-in, side tracking, handheld pursuit, Steadicam follow
- **梦境/记忆**：soft focus, lens bloom, foreground blur, slow dissolve, match cut
- **悬念揭示**：foreground occlusion, reveal shot, camera creeping past an object, focus pull
- **仪式感**：locked-off symmetrical frame, slow ceremonial movement, centered composition
- **混乱但可控**：handheld but stabilized, dust and fabric motion, subject remains readable

For most AI video models, avoid stacking too many movements. Prefer:

```text
Camera slowly tracks backward as the subject walks forward, keeping the face centered.
```

Instead of:

```text
Camera flies, spins, zooms, pans, tilts, shakes, changes lens, and cuts rapidly.
```

## Scene Staging and Motion Control

Prompt motion in three tiers:

1. **Subject motion**: the actor/creature/object’s main action.
2. **Camera motion**: one continuous camera behavior.
3. **Environmental motion**: dust, cloth, smoke, fire, rain, reflections, hair, water.

Good structure:

```text
The lone rider unfolds an ancient parchment map; the camera slowly pushes in from over the shoulder; warm desert wind moves the ropes and loose cloth, fine dust drifting through the backlight.
```

Scene staging cues that help AI video:

- Foreground object partially frames the shot.
- Midground subject remains the visual anchor.
- Background contains scale markers: mountains, ribs, ruins, lamps, posters, windows.
- Use diagonals, ropes, roads, rails, shadows, or dunes to guide the eye.
- Give tactile props: parchment, bronze mask, worn leather, embroidered fabric, cracked bone.

## Lighting and Color Patterns

Strong reusable palettes:

- **Mythic desert / ancient apocalypse**: orange-gold sunset, red sand, black silhouettes, dust haze, strong backlight, long shadows, bronze/cloth/bone textures.
- **Neon modern dream break**: blue-red neon side light, dark bedroom, phone glow, poster light spill, cool shadows.
- **Domestic memory**: warm tungsten practicals, bathroom mirror, soft window light, cluttered wall photos, handheld intimacy.
- **Sacred/ritual**: centered subject, volumetric rays, smoke/haze, high contrast, slow movement.

Name the actual light source whenever possible: low sun, neon tube, phone screen, bathroom mirror lamp, candle, fire, moonlight, projector, passing car light.

## Case Study: NeoWOW 147 — 《万物生》

Source: `https://neowow.cn/video-works-view?id=147`

Observed metadata from public API/video analysis:

- Title: 《万物生》
- Description: “祝大家马年行大运”
- Author: 命比梦长
- Video URL was public; internal canvas/prompt data is not accessible anonymously.
- The user confirmed that after logging into NeoWOW/Neo, the work opens as a node-based canvas; clicking a `视频生成` / generated-video node on the canvas reveals the prompt used for that video. When learning NeoWOW cases, ask the user to copy the prompt text or send a close screenshot of the opened video node/prompt panel.
- Video properties parsed from MP4: ~66.084 seconds, 2560×1440.

### Narrative Structure

The case works because it builds a **mythic wasteland dream** and then reveals a **modern interior frame story**:

1. **Ancient / mythic desert opening**
   - Close-up tactile detail: polished black shoes, ornate red fabric, carriage/ritual texture.
   - A woman/rider in pale fabric sits against a golden desert horizon.
   - Blurred foreground and shallow depth create a memory-like transition.
   - Sunset silhouette of a caravan/vehicle in a desolate wasteland.

2. **Exploration / worldbuilding**
   - A lone traveler studies a parchment map on a ship or desert rig.
   - A reflective/metal mask or helmet adds sci-fi/fantasy ambiguity.
   - Giant fossil ribs rise from the red sand, creating scale and myth.
   - A figure stands alone before skeletal remains under a burning orange sky.

3. **Labor / apocalypse image**
   - Groups of people pull ropes in dust before a colossal skull or jaw.
   - The world feels built from bones, sand, ropes, cloth, bronze, and sunset haze.
   - Human scale is tiny against ancient remains; this creates awe and dread.

4. **Modern reveal / dream rupture**
   - Hard cut into a cramped modern room: young woman, blue-red neon poster, phone glow.
   - Bathroom mirror and warm practical light shift tone from epic to intimate.
   - Bedroom wall with photos and whiteboard suggests investigation, memory, or obsession.
   - Final sleepy/reaching motion implies the ancient sequence may be dream, memory, or story seed.

### Visual DNA to Reuse

- **Macro-to-epic scale shift**: start with extreme close-up of fabric/shoes/props, expand to a vast wasteland.
- **Golden-hour backlight**: low sun silhouettes subjects and creates dust glow.
- **Foreground occlusion**: blurred dunes, ropes, rails, cloth, or doorframes crossing the lens.
- **Ancient + sci-fi ambiguity**: parchment and ritual costume mixed with masks, rigs, or wasteland machines.
- **Tactile props**: parchment map, ropes, embroidered cloth, bone, bronze, leather, dust.
- **Dream cut**: abrupt transition from orange mythic exterior to blue-neon modern interior.
- **Human against colossal remains**: giant ribs/skull/jaw as scale architecture.
- **Letterboxed film frame**: cinematic wide composition, strong horizontal horizons.

### Reusable Prompt Fragments Inspired by This Case

Use as ingredients, not as a script to copy blindly:

```text
Extreme close-up of polished black shoes stepping over embroidered red fabric, warm sunset reflections, shallow depth of field, tactile cinematic detail, slow deliberate motion.
```

```text
A lone traveler in pale flowing robes sits on a desert rig at golden hour, wind moving the fabric and ropes, camera slowly tracks sideways, vast dunes and low sun behind, mythic wasteland atmosphere.
```

```text
Over-the-shoulder shot of a traveler unfolding an aged parchment map, deck ropes framing the foreground, orange desert light, dust in the air, slow push-in, shallow depth of field.
```

```text
A field of colossal fossilized ribs rising from red sand under a burning orange sky, one small human silhouette in the foreground, low-angle wide shot, dust haze, epic ancient-apocalypse mood.
```

```text
A group of exhausted workers pull thick ropes across red sand before the huge jaw of an ancient beast, camera low and slowly tracking backward, dust clouds around their feet, sunset backlight, ritual labor, cinematic tension.
```

```text
Hard match cut from orange desert dusk to a cramped modern bedroom washed in blue-red neon, a young woman stares at her phone beneath a glowing poster, handheld stillness, dreamlike unease.
```

```text
Warm bathroom mirror shot, soft tungsten light, condensation and cluttered sink details, the woman studies her reflection in silence, slow static frame, intimate post-dream realism.
```

### Why This Case Works

- It does not rely on random spectacle; each image has a clear scale relationship.
- The visual world is built from a small set of repeating materials: sand, bone, cloth, rope, bronze, parchment, neon, warm domestic light.
- It contrasts two palettes: mythic orange exterior vs modern blue/red interior.
- It uses shot-size progression: detail → medium character → wide world → massive scale → intimate interior.
- The modern reveal recontextualizes the fantasy sequence as dream/memory/story, giving the visuals narrative purpose.

## NeoWOW Prompt Corpus Learnings

### File 01 — Production-style prompt anatomy

Learned from `neowow_prompt_part_001_split10_01.txt`. Keep only the reusable craft, not raw prompt dumps.

Strong NeoWOW-style prompts often behave like a combined director's breakdown, DP brief, sound-design sheet, continuity bible, and editing note:

1. **STYLE LOCK first** — begin with film stock / cinematographer or film reference / grain / halation / practical-light rule / haze / material realism / aspect ratio / genre rhythm. This locks the image system before describing action.
2. **Reference assets need explicit jobs** — each reference should be assigned a role: scene anchor, character anchor, prop anchor, palette anchor, or voice anchor. Include where it appears, what must stay consistent, and what is forbidden.
3. **Shot-level production blocks** — for multi-shot prompts, write each shot with shot size, focal length, projection, camera height, camera state, composition layers, beginning/middle/end actions, dialogue timing, and transition type.
4. **Sound drives the scene** — specify ambient bed, Foley, action sounds, dialogue tone/direction, music restrictions, and silence/stop beats. Comedy and tension can be created by a sound cut, dead silence, or a whip-pan stop.
5. **Occlusion/focus can carry comedy** — a fixed tripod shot can stay visually controlled by making a foreground object the absolute sharp subject while real character action happens behind it in bokeh, visible only as edge fragments; dialogue and Foley reveal the hidden action.
6. **Palette as production constraint** — useful prompts bind exact colors to functions: sky, direct light, cool shadow, material base, glowing tech, cloth, wood, etc.; then later shots reference the palette as a strict color bible.

Reusable skeleton:

```text
【STYLE LOCK】film/cinematography/texture/light/sound rules.
【参考锚定】@A scene anchor; @B character anchor; @C prop anchor; @D palette anchor; @E voice anchor; each with appearance scope and forbidden errors.
【镜头结构】Shot 1: shot size + lens + camera position/state + foreground/midground/background + start/middle/end action + synced sound/dialogue.
【转场】hard cut / whip pan / match cut / black cut with exact timing.
【声音设计】ambient bed + Foley + dialogue tone/location + music/no-music rules + silence or stop beats.
【约束】no wrong character/shape, no unwanted music, no camera drift, clear tail-frame state.
```

### Files 02-33 — NeoWOW corpus-wide production grammar

Learned from the full local prompt corpus in `/Users/kairos/Desktop/opt/separate prompt` after file 01. These notes generalize the writing craft; do not copy source scenes literally.

#### 1) Industrial prompt structure

For strong AI-video prompts, use a production-bible structure rather than a single descriptive paragraph:

```text
【STYLE LOCK / 总调性】film stock, director/cinematographer reference, aspect ratio, grain, halation, practical-light rule, no CG/cartoon unless desired.
【参考素材分配】role of each reference: character / costume / prop / vehicle / scene / color palette / voice. State what each reference controls and what it must not control.
【场景物理设置】location, ground plane, movement axis, foreground/midground/background, scale markers, crowd/traffic/object density.
【镜头规则】duration, shot count, hard cut vs single take, lens/focal length, camera height, angle, projection, whether camera may dolly/orbit/pan/zoom.
【动作时间轴】0-2s / 2-4s / 4-6s or start/middle/end: trigger, reaction, physical result, tail-frame state.
【光影色卡】source, direction, shadow color, haze/dust, practicals/neon/sun, HEX colors with functional jobs.
【声音设计】ambient bed, Foley, dialogue tone/distance, event sounds, silence/blackout/whoosh/THOOM timing, music restrictions.
【连续性与禁令】character consistency, pose/eye-line/direction continuity, no unwanted camera drift, no wrong style transfer, no random cuts.
```

Core rule: every prompt must answer **what is filmed, how it is filmed, how it moves, why it cuts/does not cut, what sound marks the beat, and what the last usable frame looks like**.

#### 2) Director logic: action, comedy, and narrative hooks

- **Action scenes** need a movement axis first. Define relative positions, direction, speed, force transfer, and physical evidence: rope tension, sand spray, impact dust, armor deformation, cracked ground, motion blur, low-frequency sound.
- **Large-scale spectacle** works best as a three-beat montage: detail/weapon/rope/foot close-up → wide scale relationship → character reaction or aftermath.
- **Comedy** is usually staged through contrast, not exaggerated performance: a deadpan/serious subject inside a chaotic environment; foreground stillness vs background disaster; professional mission tone vs mundane set-life interruptions.
- **Aftermath beats** are valuable. After a huge event, write silence, coughs, dust settling, stunned eye-lines, debris, drag marks, and small humiliating actions to give scale and black humor.
- **Mystery/task-start beats** can use a minimal template: static full-body theatrical light → hard cut to medium dialogue/reaction → pan/rack focus to prop reveal.

#### 3) Camera and staging patterns to reuse

- **Single take**: specify the start point, route, end point, door/curtain/monitor/foreground occlusion, and sound changes. If strict, write `no cuts, no translation, no orbit, no zoom, no parallax` as needed.
- **Hard-cut sequence**: each shot gets a function — cause/detail, scale/spatial relation, reaction/escalation, consequence/tail-frame. Preserve motion state across cuts.
- **Occlusion transition**: a passerby, tram, card, monitor edge, prop, dust cloud, curtain, or mechanical body masks the lens; after the mask clears, only the intended state changes.
- **Rack-focus prop reveal**: plant the prop blurred in the foreground/background, hold an empty beat, pull focus, then let the hand enter and claim it.
- **Nodal/environment scan**: for reusable backgrounds, declare no characters/no story; camera stays fixed and only pans around its own vertical axis, with world light fixed.
- **Reveal shot**: design the order in which information enters frame: local detail → main figure → nearby bodies/props → full battlefield/room/vehicle.

#### 4) Asset-first workflow

Long video projects benefit from generating production assets before final clips:

- **Color card**: include cross-shot colors, new shot-specific colors, HEX labels, and the narrative function of each color.
- **Character/vehicle reference sheet**: front/side/back/3-4 views under clean light; forbid battle scenes, mood lighting, or style drift if the sheet is for identity.
- **Storyboard/keyframe**: each panel should specify shot type, lens, angle, action, composition, SFX, arrows, and notes. Keyframes should declare their use: first frame, tail frame, transition frame, reveal frame.
- **Blocking/top-down diagram**: use arrows, camera position, axis line, subject positions, and movement direction before writing complex action.

#### 5) Lighting, palette, and texture lessons

- Do not write only “cinematic”; name the light source and behavior: low sunset backlight, theater work light, neon sign spill, phone glow, bathroom practical, tram window light, red stage light.
- Give colors jobs: gold sun = myth/scale, cyan shadow = machinery/coldness, red practical = danger/ritual, green patina = ancient tech, tungsten = domestic reality.
- Black-and-white prompts need grayscale hierarchy, rim light, metal highlights, smoke/dust separation, and material reflectance instead of color words.
- Realism comes from tactile evidence: cloth flutter, sweat, dust on face, metal creak, rope fibers, scuffed shoes, prop scratches, condensation, camera monitor bezels.

#### 6) Sound as edit and performance control

Sound should be written as a timeline layer:

```text
环境底噪：wind / traffic / set chatter / ship creak / AC hum.
动作 Foley：footsteps, fabric, rope strain, metal scrape, sand hit.
事件重音：clapboard snap, hard cut silence, whoosh, THOOM, crash, muffled impact.
对白：speaker position, distance, tone, speed, emotional restraint, whether off-screen.
音乐：none / diegetic only / percussion only / stop at exact beat.
```

Use silence, black screen, muffled audio, or abrupt sound cut as a narrative beat; do not add emotional BGM by default in action-heavy or deadpan comedy scenes.

#### 7) Useful micro-templates

**4-6 second reaction clip**:

```text
0-1.5s: subject holds a readable state; environment bed audible.
1.5-3s: off-screen trigger from a named direction/distance.
3-5s: face/hand/body reacts; one physical consequence occurs.
Tail frame: subject frozen in a clear usable pose, no random cut.
```

**Street occlusion outfit/location change**:

```text
Character keeps the same walking rhythm. A real occluder crosses frame for 0.5-1s from left to right. After it clears, clothing/location has changed while face, height, pose, and motion continuity remain identical; street ambience changes with the new space.
```

**Heavy impact action**:

```text
Show force source → close-up of tension/deformation → wide shot of scale → impact with dust/debris/sound pressure → reaction/aftermath silence. Camera shake only at impact, not before.
```

**Deadpan set-life comedy**:

```text
Locked or symmetrical frame; main character remains emotionally restrained. Background/crew/prop chaos escalates around them. Dialogue is casual/off-screen; humor comes from frame relationship and Foley, not slapstick acting.
```

### 末日乐园 Corpus — Suspense, apocalypse, micro-performance, and spatial iron laws

Learned from `/Users/kairos/Desktop/opt/video prompt learning/末日乐园 separate prompt` after the NeoWOW corpus. This corpus strengthens the skill for **urban apocalypse, confined-space suspense, dialogue pressure, body-horror reveals, action reversals, and character awakening**. Keep the reusable craft; do not copy raw source prompts.

#### 1) How it complements NeoWOW

NeoWOW teaches the outer production system: `STYLE LOCK → reference anchors → asset-first workflow → shot production blocks → sound design → tail-frame continuity`.

末日乐园 adds the inner suspense-control system:

```text
空间/角色/道具铁律 → 六钉锚点 → A/B/E区块 → 光源状态机 → 微表演链 → 日常空间失效 → 密室动作棋盘 → 逐镜负面排错 → 余波/觉醒尾帧
```

Merged high-control template:

```text
【STYLE LOCK】genre, render/live-action rule, lens grammar, texture, aspect ratio, no unwanted style.
【参考锚定】which reference controls character / space / prop / palette / voice; forbid cross-contamination.
【空间铁律】room geometry, doors/windows/stairs, who stands/sits where, who can see whom, prop coordinates, movement axis.
【六钉锚点】5-6 immutable scene anchors such as cup, fries, knife rack, window, elevator button, island counter.
【镜头时间轴】shot number + seconds + focal length/aperture + camera height + movement + start/middle/end action + tail-frame.
【光源状态机】what light exists, when it turns on/off, what is visible in darkness, flash/lightning frequency, color temperature.
【微表演链】eyes, eyelids, lips, throat, breath, fingers, shoulders, gait, sweat, muscle tension instead of abstract emotion.
【声音节拍】no BGM unless needed; rain, thunder, AC hum, footsteps, breath, glass, water, cloth, voice distance, silence.
【动作物理】force source, body position, distance, impact direction, debris/water/glass response, aftermath.
【逐镜负面约束】no wrong positions, wrong hands, prop drift, random cuts, overacting, wrong light, cartoon/cheap filter.
```

#### 2) Suspense and horror directing rules

- **Start with environment failure**: modern systems stop working — heat becomes unbearable, rain steams off the ground, lights fail, elevator buttons do not respond, city blocks go dark. Apocalypse feels stronger when daily infrastructure betrays the character.
- **Make fear physical**: replace “she is scared” with breath becoming shallow, fingers freezing, pupils widening, lips parting without sound, throat swallowing, feet hesitating, sweat sticking fabric to skin.
- **Use everyday props as emotional triggers**: cola condensation, fries, a straw mark, thermometer digits, elevator button, knife rack, broken glass, playing/card-like remains. Show the prop before it becomes plot.
- **Delay the full monster reveal**: introduce a predatory character through hands, shoes, reflection, voice, engine sound, environmental reaction, or two-frame flashes before showing the complete face/body.
- **Let politeness become horror**: a villain asking about dinner, offering a drink, or speaking softly can feel more dangerous than shouting if the action is mechanical, emotionless, and spatially controlling.

#### 3) Spatial iron laws and scene anchors

For confined scenes, write a mini blocking bible before shots:

```text
空间铁律：落地窗在北侧，厨房岛台在画面右侧，电梯门在远景左后方；角色A坐在桌内侧背对门，角色B站在桌边，角色C面对入口；刀架固定在岛台后缘；全段不得换位。
六钉锚点：可乐杯、薯条盒、托盘、窗玻璃、门把手、刀架/按钮/温度计。每镜保持位置、材质、湿度或反光一致。
可见关系：谁先看到危险，谁背对危险，谁只通过声音察觉。
```

This prevents AI video drift and creates readable tension. In dialogue or confrontation, spatial information is drama: who stands, who sits, who blocks an exit, who is closer to the knife/elevator/window.

#### 4) Light-source state machine

末日乐园 prompts often make light a rule system, not decoration:

- **Lightning-only rule**: when lightning flashes, the room is visible; between flashes, the frame is truly black or nearly unreadable. Do not allow random fill light.
- **Cold/warm collision**: warm fast-food or apartment light against cold lightning, fridge light, city darkness, or storm light creates psychological contrast.
- **Light as edit point**: each flash can reveal a new pose, closer distance, changed expression, or missing subject.
- **Failure beats**: lamp does not turn on, elevator display stays dead, city lights extinguish floor by floor, glass boundary breaks and storm light enters.

Write light as cause/effect:

```text
0-2s: pure darkness except rain sound.
2.0s: lightning freezes the room for six frames, revealing the figure two meters closer.
2.2-4s: darkness returns; only breath and wet footsteps remain.
```

#### 5) Dialogue pressure and social dread

For conversation scenes, do not write a transcript only. Use:

- table/prop anchors: cup condensation, fries, tray, paper napkin, straw, knife, phone;
- hand choreography: reaches out, stops, retracts, crushes paper, rubs condensation, touches knife handle;
- belief gap: one character jokes or disbelieves while another is silently terrified;
- power geometry: one stands while one sits; low-angle tabletop shot makes the standing character dominate;
- sound vacuum: restaurant noise or room tone drops for one line, then returns.

Template:

```text
Shot 1 establishes table geometry and who can see the door.
Shot 2 isolates the dangerous line of dialogue while background noise falls away.
Shot 3 cuts to hands/prop reaction, not the face.
Shot 4 shows the listener misreading the danger, restoring noisy normal life.
Tail frame keeps the threatening character entering/standing in a dominant position.
```

#### 6) Confined action and reversal structure

Use a physical chessboard for fights:

1. **Before action**: mark body positions, heights, obstacles, exits, weapon distance, ground condition.
2. **Hope beat**: the protagonist sees or reaches a tool, e.g. a knife 5 cm from the hand.
3. **Delay beat**: fingers slip, breath fails, villain misunderstands or enjoys the moment.
4. **Impact beat**: the tool lands; show entry point, resistance, sound, facial change.
5. **Aftermath beat**: confirm death, check the body, retreat, discover wound healing or new rule.
6. **Scale beat**: move from room-level survival to city/world-level apocalypse.

Rule: **after an action climax, always write the residue** — water ripples, glass shifts, breath returns, hand trembles, corpse does not move, wound seals, city is silent.

#### 7) Negative prompting as shot-by-shot QA

For high-control video prompts, generic negatives are not enough. Add shot-specific failure prevention:

- no character swapping positions or facing the wrong direction;
- no wrong hand touching the knife/card/button;
- no prop teleporting, floating, disappearing, or changing scale;
- no random fill light if the rule is darkness/lightning only;
- no emotional overacting when the intended tone is restrained terror;
- no random cut to a new room, exterior, or abstract montage;
- no cartoon filter, cheap horror glow, fake blood spray, or decorative VFX replacing physical evidence;
- no BGM if the scene depends on rain, breath, thunder, glass, water, and silence.

#### 8) Micro-templates from 末日乐园

**Prop-triggered realization**:

```text
Medium close-up. The character's fingertip rubs cold condensation on the cup; the motion suddenly stops. The ambient room tone drops. Rack focus from the wet fingertip to the eyes; pupils widen, breath becomes shallow, lips part but no words come. Tail frame holds the hand frozen beside the prop.
```

**Predator entrance without full face**:

```text
Start with engine/footstep/door sound. Cut to shoes, hand, reflection, silhouette, or object reaction. Keep the full face hidden until the victim sees him. Environment sound compresses for the reveal; the first full-face frame is motivated by the victim's eye-line.
```

**Lightning horror beat**:

```text
The room is black. A lightning flash reveals the figure at the far end. Darkness returns. Wet footsteps move closer off-screen. A second flash reveals the figure much nearer, face still unreadable. No fill light, no BGM, only rain, breath, and delayed thunder.
```

**Conversation pressure**:

```text
One character stands beside the table, the other sits with hands near a cup/napkin. Low tabletop angle makes the standing figure dominate. Dialogue stays polite. The seated character's fear is shown through tiny hand movements and swallowed breath; restaurant noise briefly drops on the dangerous line.
```

**Reversal and aftermath**:

```text
The weapon is visible just out of reach. Fingers drag through water/glass toward it. Impact happens only after a delayed breath beat. After the strike, hold on the body, the protagonist's shaking hand, the sound of water and glass, then reveal the new rule or next-scale threat.
```

## Output Quality Checklist

Before giving the user a video prompt, verify:

- [ ] The prompt names a clear subject and one main action.
- [ ] Camera movement is concrete and not overloaded.
- [ ] Lighting source, color palette, and atmosphere are explicit.
- [ ] Scene depth is staged: foreground / subject / background.
- [ ] Motion is controlled: subject + camera + environment.
- [ ] Style words are supported by specifics, not just “cinematic”.
- [ ] If multi-shot, each shot has a purpose and visual continuity.
- [ ] Avoids generic AI filler such as “ultra realistic masterpiece” unless the model benefits from it.

## Common Pitfalls

1. **Only describing content, not motion.** Video prompts need action, camera, and environmental movement.
2. **Too many simultaneous camera moves.** AI models often fail when asked to pan, orbit, zoom, dolly, and shake at once.
3. **Vague style labels.** “电影感” is weak alone; specify backlight, lens, blocking, haze, aspect ratio, and pace.
4. **No scale markers.** Epic scenes need human silhouettes, foreground objects, or architecture to show size.
5. **No continuity across shots.** Repeat costume, palette, props, and camera rhythm to keep the character/world consistent.
6. **Ignoring negative constraints.** Add anti-jitter, anti-deformation, anti-random-cut constraints when needed.
7. **Copying example content literally.** Learn the structure and visual grammar; adapt materials and motifs to the user’s new idea.

## Learning New Examples

When the user sends a strong case:

1. Retrieve the page/video/prompt if accessible.
2. For NeoWOW/Neo cases, the authenticated Arc/browser canvas may show real prompts: open the work canvas, click each `视频生成` / generated-video node, and read/copy the prompt panel. If the agent has `computer_use`, it may drive the user's logged-in Arc browser after explicit permission; otherwise ask the user to copy the node prompt text or send close screenshots.
3. If the actual prompt is hidden, analyze representative frames.
4. Extract: narrative arc, palette, camera patterns, motion patterns, staging, material vocabulary, and reusable fragments.
5. Patch this skill with a compact case note if the example adds genuinely new reusable knowledge.
6. Keep raw dumps out of memory; store distilled prompt craft here.
