# LemonNodes

![](images%5Clemon.jpg)

**LemonNodes — fresh, and packed with more.** A ComfyUI node toolkit for everyday users and power users alike: 6 launch groups, 50 nodes, and 100+ highlights. Fewer nodes, fewer wires, fewer knobs. The UI stays understated and follows ComfyUI's own design language, so newcomers aren't scared off and veterans save time and effort.

---

## ✨ Lemons are not a bundled pack, and not just LEGO bricks

Anyone who has generated images or videos with AI has run into the two extremes:

- **One-click all-in-one bundles**: everything is included, but the pipeline and parameters are sealed — you get what the bundle gives you;
- **Hand-built workflows from classic nodes**: flexible, but every image means dragging out a long chain and wiring until your eyes hurt — each node is just a single "LEGO brick".

LemonNodes takes the middle road: **modular, just right** — high-frequency operations are packaged into one node per "capability". Need something? Drag it in. Want to change it? Swap the node.

![](images%5Cui.jpg)

---

## 🎯 Why use it

| Pain point | How it's solved |
| :--- | :--- |
| Model + CLIP + VAE + prompt means a long chain of nodes | 🍋 **Lemon Loader**: one node replaces a whole chain — AIO / GGUF direct loading, no reloading when parameters don't change |
| Local repainting is a pain because masks are tedious to paint | ✍️ **Mask Painting**: brush / erase / fill, vector-recorded, undoable and exportable, auto-rescaled when the image changes |
| Every model needs a different size node | **Size Presets**: one logic for txt2img and img2img — landscape/portrait, megapixels, long/short-edge solving, favorite your own sizes |
| Too many LoRAs, and the best strength / trigger words are forgotten | **LoRA Management**: best strength and trigger words are stored with each LoRA — one-click load, one-click copy |
| Multi-stage sampling wiring looks like a spider web | **Unified Multi-Stage Sampler**: deploy multi-stage sampling from one node, with all intermediate results output — no more spider webs |
| Want cheap drafts to see results quickly | **Batch Quick Draft (Sampler)**: only a few steps per batch seed for previews — run full steps once you like what you see |
| Parameters are lost after an image is generated | **Save Node**: PNG / JPG / WEBP all carry metadata, with a companion node to extract it; EXIF includes the run time |
| Want prompt reverse-engineering / translation / OCR | 🧠 **Text Inference**: 12 built-in experts plus custom ones — use ComfyUI as a professional application |
| …… | ✨ **More features**: easter eggs await your discovery! |

![](images%5Clist.png)

---

## 🚀 Up and running in 60 seconds

**Any workflow, from zero frames — F1 sorts it out.** Press F1 to summon the **Lemon Fast Groups** panel; five common node buttons create your starting setup in one click:

1. Click **🍋 Lemon Loader** → pick a model, fill in the positive prompt (AIO / GGUF load directly).
2. Click **🍋 Lemon Sampler** → connect model / latent, adjust steps and CFG.
3. Click **🍋 Lemon Image Save** → choose an output folder, hit Run.

**Messy workflow? F2 tidies it in one click.**

- Select the nodes you want to organize and press F2 to lay them out neatly in one go;
- Or select a single node and press F2 to neatly arrange that node together with its upstream and downstream relatives:

### Common starter combos

| What you want | Which nodes to use |
| :--- | :--- |
| Quickly generate one image | Lemon Loader + Lemon Sampler + Lemon Image Save |
| Local repainting | Single Image Loader (Mask Painting) + Lemon Sampler + Lemon Image Save |
| Batch parameter sweep | Multi-Image Batch Task + Batch Quick Draft (Sampler) + Lemon Random Seed (📡) + Lemon Image Save |
| Prompt reverse-engineering / translation | Text Inference (TASK) with the "Image Reverse" or "Translation" expert |
| Tiling large images | TTP Split + processing nodes + TTP Merge |
| A/B comparison tuning | Lemon Image Save ⚔️ Compare + full-screen dual-image viewer |

---

## 🤝 Creator Program

If you happen to be looking for content ideas — LemonNodes is a ready-made topic pool: LoRA management, the all-in-one loader, multi-round batch img2img, multi-round batch txt2img… every selling point is a potential episode. Feel free to drink from the well.

Content creators who publish original AI / ComfyUI content on three or more platforms (at least three original posts) can receive a free six-month Pro license key.

- **How to apply**: message or email [lemonoder@qq.com](mailto:lemonoder@qq.com) with your channel links or proof that it's you;
- **A thank-you for co-creation**: if you find it useful and make a piece of content about it, you get another six months — no pressure, entirely optional;
- **Extra perk**: when your followers buy a license key for the first time and mention you to support, they get one extra month of usage.

Whether it's for personal use, a review, or a usage guide — as long as it's related to the channel, you're welcome to claim it.

---

## ✨ Feature highlights

### 1. Clean workflows: modular, just right

- **Not an all-in-one bundle**: every node is an independent module. Combine the chain freely — your workflow isn't locked down.
- **Not just a LEGO brick**: related features are packaged into one node. For example, **Lemon Loader** = model + CLIP + VAE + positive prompt + empty latent; **Lemon Sampler** = sampling + step preview + matrix preview + FLS enhancement + SeedVR2 multi-round upscaling.
- **Install fewer node packs**: previously, using one node from a pack meant installing the whole pack. LemonNodes concentrates high-frequency features, so your `custom_nodes` directory and right-click menu both stay clean.
- **The result**: the same generation task needs fewer nodes and fewer wires on the canvas — and you can change exactly what you want.

### 2. Feature completion plug-ins: a lean UI, attach when needed

- **Original approach**: the original "add-on node" idea — any node can be hooked up, and parameters take effect on connection. But the world is vast, so we won't claim to be the absolute first; we stay humble.
- **The main node stays clean**: rarely used parameters don't take up node space. You don't have to stare at parameters you never use, and the UI stays undisturbed.
- **Hook it up and it takes effect**: when you need professional control, drag a feature-completion node onto the canvas and plug it into a port; it takes effect immediately. It can even inject into the corresponding node of the same workflow without any connection.
- **Effortless**: use whichever you need, and removing it doesn't affect the main chain.

### 3. Image prep, handled by the loader

Image preparation needs no external tools — it happens right inside the workflow:

- **Crop / rotate / scale**: drag the crop box directly on the canvas — what you see is what you get.
- **Outpainting / expansion**: expand the mask outward in pixels — one step to outpainting.
- **Mask painting**: brush / erase / fill at will, vector-recorded, exportable and importable, auto-rescaled when the image changes.
- **Multi-image merge**: scale and stitch secondary images into one, and export any single one as needed.

**Seamless switching between sibling nodes**: the four image loaders (Single / Multi / Crop & Scale / Mask Painting) switch between each other with one click in the title bar — the currently selected image, existing connections and parameter cache all come along. Switch and keep working without rebuilding the workflow.

### 4. Size presets: no more swapping size nodes per model

Normally, switching models means switching to the matching latent size node. Lemon's size presets don't need that —

- **Auto-detection, one logic to the end**: img2img and txt2img share the same size preset logic — no separate latent size node per model.
- **Landscape / portrait switching**: flip between horizontal and vertical compositions in one click.
- **Megapixel sizing**: output by total pixels directly — 1MP, 1.5MP… input and get the size.
- **Sizing by ratio**: ratio + total pixels automatically computes width and height, producing an empty latent that connects straight to the sampler.
- **Sizing by long/short edge**: specify the long or short edge and the other edge is computed automatically.
- **Save your own sizes**: favorite the aspect sizes you use often and pick them in one click next time.

### 5. Model loader: three-in-one, one node for everything

- **The trio unified**: model + CLIP + VAE configuration, injection and encoding done in one pass — output ready for the sampling chain.
- **AIO direct loading**: recognizes AIO composite models and works out of the box.
- **GGUF loading**: load GGUF quantized models (including GGUF CLIP) directly — large models on low VRAM.
- **SeedVR2 upscaling built in**: select a SeedVR2 model in the loader and upscale right away; for finer control, hook up the SeedVR2 Upscale control node.
- **One loader for txt2img and img2img**: no node switching — the same loader handles both. QwenEdit, Image2.1 and Krea2Edit each have their own rules for loading and image injection, and just wiring them puts off half the users. LemonNodes hides all the adaptation inside the nodes: **no dedicated workflow needed** — drag the control node onto the canvas and connect the image injection, and it works. Try whichever model you like; the main workflow doesn't change a single line.

### 6. Model config presets: save once, deploy in one click

- Load model lists by model family — no more filling your disk with models and your dropdowns with endless lists.
- Each model's full configuration (model file, CLIP, VAE, edit mode, LoRA, quantization, etc.) can be **saved as a preset and favorited**.
- Next time, just **deploy in one click** without refilling parameters.
- Say goodbye to "different model = different workflow" — one loader, switch model configs from your favorites.

### 7. LoRA management: stop treating them as treasure chests without keys

Everyone using ComfyUI feels this: LoRAs pile up, but **where do you record each LoRA's best strength and trigger words**? A notebook, a screenshot, or your memory? If you can't remember, collecting more is just a treasure chest without a key.

- **Best strength and trigger words stored with each LoRA**: record the best strength (lower/upper bounds and default) and trigger words for each LoRA in the LoRA Manager — it travels with the config and survives workflow or machine changes.
- **One-click load at best strength**: select it in the loader and it mounts at the default strength — no manual tuning each time.
- **One-click copy trigger words**: copy the trigger words in one click and paste them into your prompt.
- **Multi-group stacking**: list-style mounting of multiple LoRAs, each with independent enable / model / strength, and optional CLIP injection.

### 8. Unified multi-stage sampler: no more spider webs

Multi-stage sampling (rough first, then segmented refinement) used to mean a long chain of samplers handing off to each other, with wiring on the canvas looking like a spider web.

- **Deploy multi-stage sampling from one node**: **Lemon Sampler (Multi-Stage)** merges the loader and the sampler. After sampling, intermediate results such as model, conditioning, VAE, latent and prompt are all output — connect to whichever stage you need.
- **Sigma plots from step previews auto-saved**: sigma plots from step previews are archived automatically, so you can review the sampling process with evidence.
- **Per-stage step control**: use the **Step Control** control node to specify the start / end step range of each stage; it takes effect without any wiring.
- **Clean and readable**: the same multi-stage logic with fewer nodes and straighter wires — easy to read and change.

### 9. Save node: every post-generation action already thought of

- **A/B comparison**: the ⚔️ toggle compares A / B image sets in one click — no switching files back and forth.
- **Multiple formats**: PNG / JPG / WEBP, your choice. PNG carrying metadata is nothing special — **JPG and WEBP also carry full parameter metadata**.
- **Metadata extractable**: the companion extractor node reads the parameters back, so nothing is lost for reuse.
- **EXIF records**: brief parameter settings + **run time records** (per-node timings are all in there), so tuning has evidence.
- **author credit**: leave your name on your images.
- **Free paths**: custom filename and storage path — save to the desktop in one click.
- **One-click post-actions**: open, copy, open containing folder, **flash-send to an image loader** (straight into the canvas to keep processing).
- **Full-screen dual-image comparison for details**: overview and detail views linked, swipe to wipe / click-and-hold to switch, 1:1 pixel-level inspection, and a red viewfinder to frame any detail — the craft of A/B comparison, maxed out.

### 10. Text inference: use ComfyUI as a professional application

Not "yet another LLM node", but a full inference suite that covers inference models across many use cases:

- **Local and remote alike**: local LLMs, CLIP models and HTTP external services all supported.
- **Fine-grained tuning, usable as a regular inference node**: the advanced parameter mode provides full parameter control — when you need precision, it is a professional inference node.
- **Foolproof expert mode**: pull out an expert and use ComfyUI as a professional standalone application — translation, prompt expansion, image reverse-engineering, OCR, summarization, keyword extraction… 12 built-in experts, zero configuration to start.
- **Custom experts**: define your own experts — your workflow becomes your application.

### 11. Elastic dual text box: two boxes, one space for many uses

The inference node uses it most, but it isn't exclusive to inference:

- **Dual text boxes**: an upper and a lower box, with a clear division between system prompt and user input.
- **Elastic height modes**: both free, upper fills, lower fills, expand on focus, restore on blur… 7 height modes, so you decide how the node's area is used.
- **Auto-expand on focus**: click a box and it expands, and restores on blur — long text never feels cramped.
- **Expert mode feeds results back in place**: no separate text receiver node needed — inference results display right in the node, saving a wire on the canvas.

### 12. Lemon Fast Groups: turning rgthree's "good but not quite" into good

rgthree's fast groups are useful but always fall a bit short — one group per panel, dragged out in a long row. Lemon Fast Groups handles canvas management in one shot:

- **One panel manages all groups**: no more "one group, one bypass panel" — a single node handles all group management.
- **Virtual grouping**: group by conditions without actually creating groups — manage whichever group you want.
- **Soft / hard bypass**: switch between soft and hard bypass freely — soft to temporarily turn things off, hard to fully isolate.
- **Sorting and alias filtering**: filter and sort by keyword, so you find any group at a glance no matter how many there are.
- **One-click node summoning**: summon nodes in one click so the ones you need are right there — no searching the canvas.
- **Group safety protection**: protect groups from being deleted or changed by mistake — go ahead and experiment.
- **Reverse bypass**: bypass a group in reverse and isolate the ones you want excluded.
- **Global hotkeys + group title-bar actions**: in addition to in-row operations, hotkeys are always at hand.

### 13. Random seed: all of rgthree's pain points solved

Addressing rgthree's random seed node, several long-standing issues solved at once:

- **Every click actually randomizes**: click 🎲 and it takes effect immediately — no "run once first" to activate.
- **Node-free deployment**: the random mechanism is driven entirely by front-end DOM buttons (🔒 Fix / 🎲 Reroll / 🧷 Previous / ⚓ Anchor, one-click each). It doesn't rely on node wiring or backend logic — it works wherever you click.
- **One-click broadcast**: click 📡 in the title bar and all seeds in the workflow follow; receivers show 🟢🟡 visual markers.
- **Global defaults configurable**: random upper limit, initial state (fixed/random) and anchor default all have global settings — configure once, effective everywhere.
- **Four-mode cycle**: 🔒 Fixed / 🍀 Random / ➕ Increment / ➖ Decrement, with anchor and "previous value" available for rollback at any time.

### 14. Batch tasks: people leave, images keep coming — hundreds a night

- Feed images from a directory in rounds, with filename filtering (run only a given prefix), subdirectory traversal (scan several folders at once) and a large-image compression cap (to prevent VRAM blowouts).
- Turn "a person guarding the computer" into "a person away while images run". Set the rounds and parameters, then leave the computer — when all tasks are done, it **shuts down automatically**.
- Load a batch before bed and collect in the morning: hundreds of images a night, not one missing. Batch parameter sweeps, batch repainting, batch upscaling, batch e-commerce asset generation — this is its home turf.
- And it's not only img2img — batch multi-round txt2img tasks are a must too!

### 15. Workflow extraction: metadata at your fingertips

- Extract metadata and prompts from images generated by LemonNodes — nothing lost when reviewing and tuning.
- Workflow JSON inside official PNGs can also be extracted — learn from other people's workflows directly.
- Copy prompts, save parameters as txt, save workflows as json — archive as you like.

### 16. More feature easter eggs, waiting to be found!

- **Low-cost drafting**: Batch Quick Draft (Sampler) runs only a few steps to see the real thing, trying many seed / parameter combinations in a batch, **ending early after a few steps** — the cheapest way to draft, never wasting a full-step run.
- **Arrow labels**: add pointing arrows to nodes / areas — great for explaining ideas, leaving notes, collaborating and demoing.
- **Matting summary and benchmarking**: RMBG / BEN2 / InSPyReNet / BiRefNet / SAM3 — switch models in one click, with heatmaps, foreground refinement and benchmark comparison.
- **Node router**: routing forward, mute linkage and subgraph penetration — the administrator of complex workflows.
- **More easter eggs**: the author isn't deliberately keeping secrets — the features and details are simply so numerous that a full inventory is hard to finish at once!

---

## 📦 Six groups live, video group in the works!

### 🍋 Lemon Nodes — images from entry to exit

- **Single Image Loader**: the most basic image entry. Auto-corrects photo orientation, supports multi-frame animated images, and handles 16-bit grayscale and alpha channels.
- **Single Image Loader (Crop & Scale)**: drag the crop box on the canvas for WYSIWYG cropping, rotation and scaling, with batch listing and mask sync.
- **Single Image Loader (Mask Painting)**: a mask in one stroke. Brush, erase and fill at will, vector-recorded, lossless undo, exportable and importable, auto-rescaled when the image changes.
- **Multi Image Loader**: gallery-style loading of multiple images. Main-image mode holds up to 5 (1 main + 4 secondary); no-main mode holds up to 6. Secondary images can be scaled and merged into a stitched image, and any one can be exported as needed.
- **Lemon Image Size**: one size preset logic for txt2img/img2img and every model. Ratio + total pixels, long / short edge, megapixel solving, landscape/portrait switching, favoritable common sizes, and automatic empty latent generation that connects straight to the sampler.
- **Lemon Loader**: one node replaces a whole chain. Model + CLIP + VAE + positive prompt + empty latent, with AIO / GGUF direct loading and no reloading when parameters don't change.
- **Lemon Sampler**: the sampling enhancement suite. Step preview (sigma plots auto-saved), matrix preview, FLS sampling enhancement and SeedVR2 multi-round upscaling — all in one node.
- **Lemon Sampler (Multi-Stage)**: unified multi-stage sampling that merges the loader and sampler; after sampling, intermediate results such as model, conditioning, VAE, latent and prompt are all output — no more multi-stage spider webs.
- **Lemon Image Save**: A/B comparison, multi-format metadata (PNG/JPG/WEBP), EXIF parameters and run time, author credit, custom paths, one-click open / copy / open folder / flash-send, and full-screen dual-image comparison.

### 🧰 Lemon Tools — canvas assistants

- **Lemon Fast Groups**: virtual grouping, soft/hard bypass, sorting and alias filtering, one-click node summoning (one panel for all groups, no panel per group), group safety protection, reverse bypass; in-row operations + global hotkeys + group title bar.
- **Lemon Random Seed**: four-mode cycle + 📡 one-click broadcast + node-free deployment — rgthree's pain points solved at once.
- **Lemon LoRA Loader / Manager**: list-style mounting of multiple LoRAs with optional CLIP injection; best strength / trigger words stored with each LoRA, one-click load at best strength and one-click trigger-word copy.
- **Lemon Arrow Label**: add pointing arrows to nodes / areas. Colors support hex / color names / rgb / rgba — point once and the canvas speaks.
- **Workflow Extractor**: extract metadata and prompts from Lemon images, and workflow JSON from official PNGs; copy prompts, save parameters as txt, save workflows as json — archive as you like.
- **Node Router A / B / C / D**: routing forward + mute linkage + subgraph penetration — the administrator of complex workflows.

### ⚙️ Feature Completion — hidden parameter injectors

These nodes **take effect without any wiring**: drop them on the canvas and their parameters are injected automatically into the target nodes of the same workflow.

- **Multi-Image Batch Task**: turn "a person guarding the computer" into "images running while you're away". Feed images from a directory in rounds: filename filtering, subdirectory traversal, and a large-image compression cap to prevent VRAM blowouts. Set rounds and parameters, then leave the computer — all tasks done means **automatic shutdown**, and you collect the images in the morning.
- **Reverse / Zero / Inpaint**: prompt zeroing, mask noise, differential diffusion, inpaint image/mask — injected into the loader in one step.
- **Image2.1 Options**: KV cache location and precision to fine-tune VRAM and speed; works with image injection — **no dedicated Image2.1 workflow needed**.
- **Krea2Edit**: reference image fidelity, enhancement region mask, visual encoding max edge, source image fit mode; takes effect with image injection, again without a dedicated workflow.
- **SeedVR2 Upscale**: upscale method, target value, rounds, tiling and overlap, color correction.
- **Step Control**: specify start / end step ranges for the multi-stage sampler.
- **Batch Quick Draft (Sampler)**: batch different seed / parameter combinations, ending early after a few steps — the cheapest drafting, with row-and-column previews at a glance.
- **FLS Sampling Enhancement**: realistic portraits / anime / hard metal presets + foveal reinforcement, sharpness and mask inertia.
- **Precise Crop Control**: injected into the cropper to precisely control crop behavior.
- **Image Post-Processing**: color matching, smart sharpening, denoise radius, edge preservation and blend ratio, injected into the saver.

### 🧠 Text Tools — the prompt production line

- **Text Inference × 7 variants**: TASK (most used), LLM, CLIP, RAW, HTTP (external service), Advanced Parameters, Expert Manager — local and remote both supported, with one-click switching between variants; foolproof expert mode + custom experts, using ComfyUI as a professional application.
- **12 built-in experts**: translation, prompt expansion, image-edit expansion, visual-edit expansion, image reverse-engineering, OCR, chart OCR, summarization, keyword extraction, JSON extraction, text polishing, grammar correction.
- **Batch Prompt**: split by line, line filtering, ignore short lines, batch prefix / suffix.
- **Text Router**: output multiple text segments by segment number, head/tail concatenation, external text input.
- **Multi-View Prompts / Batch Combos**: orbit angle (8 steps) × pitch height (4 steps) × shot size (3 steps) checkbox combinations — generate a whole batch in one click.

### 🧩 Image Tools — large images and low VRAM

- **Matting Summary & Heatmap Compare**: RMBG / BEN2 / InSPyReNet / BiRefNet / SAM3 — switch models in one click, with heatmaps, foreground refinement, threshold and feathering, and benchmark comparison output.
- **TTP Split / Merge / Decode**: tile large images, process each tile, then stitch back by coordinates, with gradient blending to control seams; decoding happens directly in latent space.
- **Min Edge**: uniformly resize the input image to a given edge length.

### 🔗 List Tools — bridges for batch pipelines

- **Image to List / List to Image**: convert between multiple images ↔ lists, extract by index, removable.
- **Native Multi-Image to List / List to Native Multi-Image**: compatible with native multi-image output.
- **Image List Reference**: fetch an image by index and output clip / vae / text directly to the sampler for reference.

### 🎬 Video Tools — in development, coming soon

With images and inference fully detailed, video is next. The video tools group is already underway and some nodes are finished — they'll appear in the node menu automatically once launched, with the same idea: modular, just right — fewer wires, fewer knobs.

---

## 📚 Documentation

- Complete user guide (all 50 nodes explained one by one, with every parameter documented): [LemonNodes Full Node User Guide](https://feishu.doubao.com/file/AlLqbDZZAoaJOWxnl9LcLJcynRh)
- Features and details not covered here are left as easter eggs for you to discover yourself.

---

## 💎 Pricing

**The free nodes already cover a complete image-generation pipeline**: loader → size → sample → save, all free to use; many infrastructure tool nodes are free as well. Try it at zero cost — it isn't "neutered into uselessness". For the free/paid split, refer to the node details in the 📚 user guide, but the free nodes actually available after installation prevail (paid nodes show a 🔒 marker when not activated).

**Taobao link**: [https://item.taobao.com/item.htm?ft=t&id=1089763718540](https://item.taobao.com/item.htm?ft=t&amp;id=1089763718540)

Paid nodes solve **professional and efficiency needs that the free chain can't replace**:

- **Fine control**: mask painting, crop & scale — the free chain can only repaint the whole image; local repainting and composition refinement are paid-only;
- **Efficiency**: Batch Quick Draft (Sampler), Multi-Image Batch Task, Random Seed, Batch Prompt — run a batch at once while you're away;
- **Model and LoRA management**: model preset favorites, LoRA Loader / Manager — free tier limited to 3 favorites, unlimited with Pro;
- **Canvas governance**: Fast Groups, Node Router — the administrator of complex workflows;
- **Inference productivity**: Text Inference (TASK / Expert Manager) — 12 experts in one click.
- **Paid users only**: your ideas, pain points, bugs and feature requests can go straight to the author — **the author prioritizes them**; your needs shape the next node's development.

These nodes are the result of full-time independent development and meticulous polish. Development and long-term maintenance take enormous time and energy, and healthy, sustainable revenue is the foundation for the project to keep evolving, iterating and updating reliably. So your paid support is not only a recognition of the product, but a guarantee that the project can provide long-term service. Thanks to every friend who supports LemonNodes — let's make this tool even better together!

## 📋 Purchase Notes · Refund Policy

LemonNodes is a **virtual software product (digital license)** and the following rules apply:

**Refund rules**

- Once a license key is issued, **delivery is considered complete**, and in principle refunds are not supported — virtual goods are not covered by Article 25 of China's Consumer Protection Law ("seven-day no-reason return"), which explicitly excludes "digital goods such as audio-visual products or computer software downloaded online or unpackaged by the consumer";
- **Malfunction exception**: if the license key cannot be activated on your machine and the author's assistance still cannot resolve it, a full refund is available (with proof of machine code and the assistance record);
- **Risk notice**: this product's license uses **offline verification bound to a machine code**, and the author cannot remotely determine activation status — please confirm your machine code is correct before submitting a purchase request.

**After-sales commitments**

- The author continues to follow up on bug fixes and compatibility updates;
- **Free re-issue for hardware upgrades**: when upgrading hardware, as long as **the motherboard or main hard drive is unchanged**, a new license key is issued free of charge with the original machine code;
- **Full machine replacement requires repurchase**: when both the motherboard and main hard drive are replaced, since the machine code is manually verified against the unique hardware identifiers of the motherboard and main hard drive, a new license must be purchased.
- **Invoices**: electronic invoices are supported. To request one, provide your receiving email and invoicing details (title, tax ID); the author will issue it within seven days and send it to the specified email.

**Runtime environment**

- The license is bound to a **physical machine**, with a one-to-one correspondence between license key and machine code;
- **Cloud hosts / virtual machines / remote virtualized environments**: hardware changes with the rented instance, so the license key may become invalid — **no key-reissue service is currently provided for these environments**;
- Please confirm your runtime environment before purchasing — invalidation caused by using it in a virtual environment does not fall under the malfunction exception.

**Disclaimer**

- Please confirm before purchase: your needs, your computer environment and the product feature list. Order rationally, and thank you for understanding.
- Runtime anomalies caused by your computer environment (OS version, GPU driver, VRAM, dependency conflicts) will be assisted with as much as possible by the author but do not constitute grounds for a refund;
- Refunds requested for personal reasons (accidental purchase, unfamiliarity with usage, temporarily not needing it) are not supported.

---

## 📄 Terms of Use

**License scope**

- You receive the right to use this software on **a single physical machine**, for both personal and commercial use (commercial image generation and client work are unrestricted);
- The copyright of the software belongs to the author. You only receive a right of use, not any ownership.

**Prohibited actions**

- Do not crack, decompile, bypass or attack the license verification mechanism;
- Do not copy, distribute, resell or rent this software or license keys;
- Do not use the same license key on multiple machines (except as allowed by the official re-issue policy).

**Provided "as is"**

- This software is provided "as is". The author does not guarantee its suitability for a particular purpose or environment, and you bear the risk of use.

**Handling of violations**

- If the above terms are violated, the author has the right to terminate your license without refunding fees already paid;
- Cracking, piracy and resale also constitute infringement of the author's copyright, and the author reserves the right to pursue legal action.

---

## 🔒 Privacy Statement

- Your machine code and license key are used only for license verification and after-sales re-issues, and are **never uploaded to any server**;
- This software **runs entirely offline**, with **no telemetry and no data reporting**;
- License verification (machine code comparison, license key validation) **is completed entirely on your machine** — the author cannot remotely view your machine, files or actions;
- All data such as favorites and configurations is stored only in your local ComfyUI user directory, and **is cleared when deleted**.

---

## 🛠 Installation

**This repository contains documentation only.** The node code is released as an archive in [Releases](https://github.com/lemonoder/ComfyUI-LemonNodes/releases):

1. Go to **Releases** and download the latest archive — the **all-version integrated package** is recommended (contains components for 3.11 / 3.12 / 3.13, matching your Python version at runtime, about 7MB); alternatively download the **per-version component package** for your Python version (about 3MB each);

2. Extract the archive into the `ComfyUI/custom_nodes/` directory (keep the extracted folder name as `ComfyUI-LemonNodes`);

3. Install dependencies: from the ComfyUI root directory, run

   ```bash
   cd ComfyUI
   python_embeded\python.exe -m pip install -r ComfyUI\custom_nodes\ComfyUI-LemonNodes\requirements.txt
   ```

   (For non-portable setups, run with your Python inside the node directory)

   ```bash
   cd ComfyUI/custom_nodes/ComfyUI-LemonNodes
   pip install -r requirements.txt
   ```

   **Required modules**: `pywin32` (Windows hardware identification), `cryptography` (license key recognition), `piexif` (JPG/WEBP metadata read/write), `opencv-python` (image processing), `diffusers` (scheduler installation);

**Compatibility**

- **ComfyUI**: adapted at least up to the current latest v0.43.0, backwards compatible for everyday use; but we recommend updating to at least v0.28.0: native SeedVR2 model support; at least v0.37.0: native Image 2.1 model support;
- **Python**: 3.11 / 3.12 / 3.13 all supported (the integrated package matches automatically, no manual selection needed);
- **Other Python versions**: will be supported in later releases if needed — or contact the author with your requirements.

---

## Feedback and community

- Found a problem or have a feature request? Open an issue, or email [lemonoder@qq.com](mailto:lemonoder@qq.com).
- Fun ways of using it? Please share.
- Custom nodes for special needs? Get in touch.
- If you find it useful, a ⭐ Star goes a long way — it matters a lot to me.
- Welcome to join the WeChat group to share tips:

![](wx_chat.png)

**When reporting a bug, please include the following** (fill it in as fully as possible to help us locate the issue quickly):

```
Problem description:
Steps to reproduce: 1. 2. 3.
Expected result:
Actual result:
Environment:
  - ComfyUI version:
  - Python version:
  - OS version (Win10/Win11, etc.):
  - GPU model / VRAM:
  - Node pack version (Release number or date):
Error log (ComfyUI console / log window):
Screenshot or minimal reproduction workflow:
```

