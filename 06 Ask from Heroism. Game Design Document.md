# Mechanic & Kit: Ask from Heroism. ENG GDD
[[MULTIVERSE DIMENSION UTILIZATION LICENSE (M&K WORLD LICENSE)]]

***Important Note:*** Technical notes must be discussed by the development team before the project begins. Technical note blocks are not final and must be edited depending on technical capabilities and development budget. Furthermore, the document contains a link to
The linked document, although more of a literary work than a technical specification, is the most understandable version for the author, where dialogue and plot threads are not interrupted by technical notes. The linked document takes precedence in the event of discrepancies or contradictions with this GDD.

---
### 🏡 1. WITYA'S BACKYARD

- **Level Design:** Witya’s private hangar courtyard on planet Meltin. The area must visually represent peripheral, low-income survival on the edges of the Living World.

- **Perimeter Fencing:** A medium-sized, desolate yard enclosed by a low fence. The fencing mesh is under 1 meter in height, constructed using crude metal posts holding a tightly stretched steel wire cable.

- **Vegetation Details:** Sparse, dry, and heavily withered desert plants distributed unevenly across the rocky terrain.

- **Hangar Hovel:** A small, single-story residential shack built entirely from rough, unpolished concrete blocks. The main entrance features a heavy, crude wooden door without any high-tech electronic locks.

- **Spaceship Placement:** Parked immediately adjacent to the concrete shack sits Witya's self-built custom spacecraft.

---

### 🚀 2. VEHICLE SPECIFICATION

#### **📐** A. Physical Dimensions & Structural Scale

Dimensions and Proportions:

1. **Total Height:** Exactly 2 meters from the hangar floor to the upper roofline, measured with the landing gear fully deployed.
2. **Fuselage Height:** Approximately 1.7 meters with the landing gear retracted into the lower hull bays.
3. **Total Length:** Total fuselage length at exactly 8 meters to give the ship a compact, aggressive interceptor silhouette.

**Crew Capacity:** The cockpit is designed strictly as a two-seater, accommodating Witya and Kate.

---

#### **🔩** B. Component Hybridization & Hull Geometry

The 3D model for the Witya Starfighter (WIT_CRAFT_01) must adhere to the following technical parameters:

- **Wingless Fuselage:** The ship completely lacks standard flight wings.

- **Turbine Propulsion:** The main drive consists of two massive custom turbines mounted on the sides of the fuselage. Each turbine has a fixed diameter of exactly 1 meter, creating an oversized, aggressive hot-rod engine profile.

- **Adjustable Mini-Wings & Weapons:** Two dynamic, adjustable mini-wings with variable geometry are positioned between the cockpit and the side engines. Two heavy laser cannons are integrated directly into the outermost tips of these mini-wings.

- **Segmented Nose Section:** The nose section retains a rounded, tapering shape. The smooth factory casting is replaced by rough, layered metal plates, sharp angles, and heavily segmented armor lines.

- **Exposed Engineering Layout:** An open conduit array runs adjacent to the engine blocks, consisting of exposed cable bundles, fuel lines, and flexible hydraulic hoses.

---

#### **💺** C. Cockpit & Under-Chassis Nodes

The technical framework for the Custom Star Jumper (WIT_CRAFT_01) must implement the following parameters:

- **Bubble Canopy Geometry:** The cockpit features a distinct, rounded bubble-canopy. It rejects any extended rear-ward glass structures, terminating sharply directly behind the pilot seat and transitioning cleanly into a tail section.

- **Landing Gear Shields:** The under-belly hull is equipped with heavy mechanical armor plates. These shields automatically swing open during deployment and tightly seal the internal bays to protect the landing gear when retracted.

- **Radar:** A distinctive red hemisphere-shaped element is mounted directly under the cockpit floor. Integrated into its surface are gray dot sensors that function as a radar and scanner.

- **Weaponry limits:** The ship's configuration completely excludes the presence of heavy missile compartments and launch containers in the external part.

---
## **🗃️**3. MAIN CHARACTER DESIGN SPECIFICATIONS: WITYA PEROS (WIT_PEROS)

#### 📐A. Global Metric & Stature Metrics

- **Character Height:** Witya is an anthropomorphic creature (Fustix Hybrid species) with a fixed height of exactly 1.5 meters.

- **Skeletal Proportions:** Proportions and the ratio of the head to the body must strictly follow the Master Silhouette Chart of the Living World.

- **Head Proportions:** The head features near a 1:5.5 size ratio relative to the total body height, keeping a slight intentional stylized enlargement.

- **Ear Anatomy:** The four dynamic ears display a distinct leaf-like shape with rounded tips. In a relaxed or defensive state, they slightly roll into a tube. The lower ears are structurally positioned lower than the upper ear attachments.

---

#### 🧪Fur Material & Stripe Vector Maps

- **Base Coat Color:** The default fur color is strictly ash-grey.

- **Stripe Texture:** A distinct pattern of rich purple stripes is applied over an ash-gray base. These stripes are located on the character's ears, cheeks, arms, torso, and tail.

---

#### **⚙️** Anatomy of the Ears

- 🎯 **Cranial Shape:** The top of the head remains completely bare. Fur length on this area must have a perfectly uniform texture distribution, with no distinct crests or tuffs of fur.

- 👂 **Foliage Ear Structure:** Positioned on the sides of the head are 4 flat ear flaps structured as thin membranes. They completely lack standard ear ridges or cartilage rings. Depending on external conditions, the ears support two states:
    1. _Light-Absorption State (With Sun Regime):_ The membranes fully unfurl, displaying flat profiles and sharp, upward-pointing tips to catch environmental light.
    2. _Defensive State:_ The membranes partially roll along their length into tight, protective tubes.

- 🎧 **Auditory Orifices:** Functional, high-fidelity ear openings are integrated directly into the base ("stem") of each membrane at the point of attachment of the “stem” to the light-receiving part.

---

#### **⚙️** Material & Fur Grooming Properties

- **Fur Length Masking:** The fur shader uses a dedicated 16-bit red-channel length mask texture to control fur height across the character. Length scales dynamically based on the texture coordinates:
    - Minimum clamp: Exactly 3 mm on the eyelids and nose.
    - Average length: Up to a uniform 15 mm over most of the body.
    - Maximum peak: Exactly 70 mm on the tail tip.

- 🎨 **Dual-Layer Texture Blending:** The shader executes a basic multi-material blend sequence. The base skin layout (**Layer 0**) maps the primary purple stripes over the skin. The generated fur strands (**Layer 1**) inherit their diffuse color values directly from Layer 0 based on their root positions. This ensures that the purple stripes and the ash-grey base coat stay perfectly synchronized during fast movements.

- 💨 **Wind & Motion:** Fur strands over 15 mm in length react to external physics. The shader script uses a low-cost vertex-offset noise function to simulate wind velocity and air friction during high-speed jumps or hoverskating.

---

#### **🗃️** Detailed Foliage Membrane States Description

The animation script must strictly transition between two states of the four ear membranes:

- 🌿 **State 01: Solar Light Exposure ("With Sun" Regime):**  
    Upon detecting direct sunlight, the ears trigger an unfolding sequence. All 4 leaf-flaps spread outward along a radial pattern: the upper flaps bend slightly upward, while the lower ones point downward, creating a bloom-like shape. In this state, the ear is relaxed, using soft physics constraints to react dynamically to head speed, wind, and movement. This visually confirms their fleshy structure, which completely lacks internal cartilage support.

- 🥶 **State 02: Depression, Artificial Light, & Cryo-Environments ("Without Sun" Regime):**  
    In dark zones, artificially lit sectors, or sub-zero environments, the membranes run a folding, collapsing into tight, pointed shapes. The ears tense up, pull close to each other, and sweep backward away from the face to form a rigid, horn-like silhouette. In this state ears ignores external factors and remains rigid.

---

#### **🎭** Facial Emote & Emotional Alignment Overrides

The ears change their state not only from the light exposure, but also depending on Witya's current emotional state:

- 🎨 **Bilateral Texturing:** Both sides (front and back) of the ear membranes feature same purple stripe layouts, locked into the master UV map.

- 🛑 **Negative Emotions (Sadness / Fear):** Strong negative emotional states drop all four ears down along their pitch axis. In the "With Sun" regime, extreme sadness forces a partial fold toward the center, putting the ears into a hybrid middle state. Fear or alert forcing the ears into the rigid State 02 (horn formation).

- ⚡ **Positive Emotions (Excitement / Rage):** Strong positive emotions raise the ear roots up their pitch axis. If Witya is in dark or cold environments (State 02), excitement triggers a similar, the ear cylinders are raised.

- 📐 **Low-Amplitude Micro-Expressions:** If emotional triggers are weak, only the vertices at the very tips of the ears adjust their curvature. The system mirrors simple positive and negative reactions. Additionally, in sub-zero environments, the system locks out unfolding blendshapes—emotional reactions are expressed solely via root tilt angles.

---

#### **⚙️** ANIMATION BLEND TREE & MORPH WEIGHT EXTENSION

- 🌲 **Dual-Axis Ear-Leaf Blend Space**: The animation blueprint controls the deformation of Witya's ears using a clean 2D Blend Space:
    - **Axis X (Lighting)**: Tracks the environment light level, where `0.0` represents absolute darkness/shadow and `1.0` represents direct bright light.
    - **Axis Y (Emotions)**: Tracks Witya's emotional state, where `-1.0` represents extreme depression/fear and `+1.0` represents high excitement.
	    The blend tree continuously reads these coordinates to smoothly change morph target weights between **State 01 (relaxed leaf-flaps)** and **State 02 (rigid horn cylinders)**.

- 🛡️ **Middle-State Clipping Prevention**: When conflicting parameters overlap (for example, if his emotion drops to `-0.8` under bright `1.0` lighting), the system prevents the ears from clipping through the head mesh using a strict mathematical clamp. Instead of playing overlapping folding animations, the engine smoothly interpolates the ear toward a predefined **"Middle-State"** morph. The transition handles a non-linear S-curve over **12 frames**, keeping the movement natural.

- **Rigid-to-Cloth Physics Dynamic Toggle**: The ear bones interface directly with the animation system via a dynamic physics weight modifier. Under bright light (Light Intensity > `0.7`), the engine turns on full **Cloth Physics** simulation for the ear joints, making them react realistically to wind and rapid head movements. When the light drops below `0.3`, the system clamps the physics weight to `0.0`, locks the joints back into a rigid transform hierarchy, and hands total movement control back to standard skeletal animations.

---

#### **⚙️** Vertex-Level Micro-Expression & Jitter

- 🍃 **Leaf-Tip Vertex Mask:** Micro-movements of the ear tips avoid driving the main skeletal joints. Instead, the animation blueprint uses a Vertex Shader Offset Mask. This mask isolates the top 15% of vertices at the pointed boundaries of all four ears, allowing high-frequency, low-amplitude jitter without putting extra load on the character's rigging constraints.

- 📈 **Low-Severity Tension Curves:** When Witya enters low-severity emotional states (minor curiosity, mild suspicion, or quiet focus), the system applies a low-frequency procedural sine wave to the isolated tip vertices. Curiosity triggers a subtle forward curl (+5 degrees along the local pitch axis), while mild suspicion commands an alternating left/right twitch sequence, mimicking the involuntary muscle spasms of a hunting mammal.

- ❄ **Environmental Interaction Constraint:** The micro-expression controller continuously tracks the ambient physical parameters of the level sector. When Witya enters an idle animation state, the tips of the ears deviate slightly from the nearest noise source, simulating a turn towards the sound.

---

#### **📥** Global Environmental Reaction (Witya / Fustix)

- 🗺 **Level Tracking:** Every level sector must track a global float parameter named `Ambient_Temperature`. Additionally, maps must be clearly divided into light volumes (e.g., Open Canopy Area vs. Cave Substrate Interior). The ear membranes read these values in real-time to adjust their state.

- ☁ **Dynamic Cloud Occlusion (Optional):** As an additional feature, the engine checks the sun's visibility in locations with positive temperatures. If a dynamic cloud or any other weather event obscures the primary light source, dropping local illuminance below 0.4, the ears initiate a smooth transition between states over 30 frames. This feature helps create atmospheric feedback in levels.

---

#### **🗃️** WITYA FACIAL GEOMETRY

- 🦊 **The Fustix Hybrid Cranial Standards**: The visual design of Witya Peros must strictly mirror the distinct anatomical hallmarks of the Fustix Hybrid lineage. His skull structure requires a large, exaggerated bulbous cranium that curves smoothly into a compact snout profile.

The facial feature guidelines follow specific geometric alignments:

- **The Brow and Forehead Area**: The upper face is dominated by massive, heavy brow ridges that project forward, framing large, highly expressive almond-shaped green eyes positioned dead-center on the frontal plane.
- **The Snout and Nose Bridge**: The nose bridge transitions from a wide, shallow dip into a small, rounded triangular cat-like dark nose tip, breaking away from standard sharp human contours.
- **The Lip and Jaw Profile**: His lower jawline forms a narrow, soft curve that integrates a thin, split lip line, creating a clean, permanent semi-smirk look. Every sculptural detail must anchor directly to the architectural layout template (`WIT_PEROS`) to preserve identity across model versions.

---

#### 🔋 TORSO STRIPES & HARNESS ANATOMY

- 🎽 **The Fustix Torso Patterning**: Witya’s upper body features a muted ash-grey fur base accented by dark purple tiger-like markings. The layout requires exactly three separate horizontal purple stripes mirrored symmetrically on both his left and right flanks. These thin, organic stripes curve slightly along the natural contour of his ribcage, leaving the chest and abdomen clean.

- 🎒 **The Tactical Cartridge Harness Construction**

The chest features a lightweight, custom-fitted dark-brown leather harness that holds a unique glowing element. This **gear component** follows a strict geometric layout:

- **The Strap Routing**: Two shoulder loops connect directly to a horizontal support belt that wraps snugly around his torso.
- **The Center Buckle Placement**: Positioned dead-center on his ribs, right at the mid-point of the chest straps, is a heavy metal mounting bracket. This differs from early low-slung sketches; the buckle sits high on the sternum.
- **The Energy Cartridge**: Securely slotted inside this central chest bracket is a static, non-removable cylindrical cartridge that continuously projects a high-contrast neon-blue technological glow.

---

#### 💪 HANDS & REINFORCED WORK GLOVE

- 🦾 **The Upper Arm Fur Patterning**: Witya’s shoulders and biceps are covered in a dense, short ash-grey fur base. The outer side of each upper arm features exactly three separate dark purple horizontal stripes. These stripes follow a stylized, tapering triangular contour that points slightly downward, mirroring the organic tiger-like pattern design rules used across his main torso.

🥊 **The Industrial Glove and Gauntlet Construction**

From the elbow joint down to the fingertips, the arm layout integrates a heavy-duty leather work glove. This **gear component** follows a strict functional design:

- **The Gauntlet Cuff**: The top edge of the glove forms a thick leather cuff starting precisely at the elbow line. The leather is deep brown, accented by a single decorative cyan-blue horizontal stripe wrapped around the upper rim.
- **The Hand and Finger Layer**: The glove material transitions into a coarser, textured dark-tan split leather across the palm and backing to withstand continuous mechanical friction.
- **The Dynamic Grip Alignment**: The palm mesh handles an implicit physical bone constraint system. When Witya activates his melee state, the glove deformation tracks his knuckles to deliver a tight, non-slip grip around the handle of his **VersaWrench**.

- 🥊 **Glove Lock & Ninth Game Exception:** By default, the glove models are permanently merged into the model Fustix characters. The single hard-coded exception occurs in **Game 9 (Revenge of Mistakes)**. During the aquarium stage on Siren's Socket Station, a unique scene triggers for **Partys Solis**. Being unable to swim, she removes her right glove, lures a shark with her bare hand and tickles its sensory zones, turning the predator into a temporary mount to cross the water. For this scene, the engine streams a custom bare-hand sub-mesh (`PTS_BARE_HAND_01`) showing the detailed finger-pad topology of the Fustix Fluffy species.

---

#### 👖 LOWER LIMBS & BAREFOOT

- 👖 **The Loose Pants & Jumping Leg Mechanics**: Witya’s lower limbs and skeletal joints are engineered specifically for high-velocity jumping mechanics unique to the Fustix species. He wears loose, blue pants that completely cover his thighs. The trousers feature tight elastic bands at both the waist and the ankles to prevent the fabric from catching on environment hazards during rapid platforming sprints.

- 🦿 **The Tactical Knee-Pad Protection**: Mounted directly over both knee joints are tactical knee guards. The protective gear features oval-shaped, matte charcoal-black impact plates held in place by thick elastic straps, buffering Witya's knees during rapid slides or heavy landings.

- 🦶 **The Standard Barefoot Fustix Anatomy (Обувь отсутствует)**: Witya moves exclusively barefoot. The scale of his lower paws follows balanced, natural proportions: the size of the foot relative to the leg thickness mirrors standard human body ratios. The foot is covered in a short ash-grey fur base and ends in exactly **five solid claw-toes** (пальцы-коготки) that function directly as his digits.

The asymmetric digit alignment follows strict visual rules:

- - **The Deep Recessed Pinky Claw (Мизинец)**: The outermost pinky claw-toe features a deep, recessed structural socket placement, sitting far back along a smooth curved skin notch.
- **The Angled Big Toe Deflection (Большой палец)**: The outermost big toe claw-toe features a sharp horizontal angular tilt, deflecting noticeably outward away from the foot centerline to widen the step stability.
- **The Heel and Friction Pads**: The underside integrates thick, rubbery digital friction pads that completely absorb shock from maximum-height falls, preventing slipping on wet metallic surfaces.

- 🧼 **The Ninth Game Continuity Constraint:** The player is strictly restricted from viewing the character's leg meshes without the pant applied until **Game 9**. This lock explicitly protects the comedic sequence featuring Jord Solis inside the commercial sauna layout on Siren's Socket Station, where the gag unfolds that _"picking up the soap is forbidden"_.

---

#### TAIL STRUCTURE

- 🦊 **The Fustix Tail Proportions & Patterning**: Witya’s tail serves as a critical structural and visual element for balancing his jumping physics. Its real-world length is proportional to his legs, creating an agile silhouette. The tail features a soft, dense ash-grey fur base covered in a series of alternating dark purple horizontal stripes that seamlessly follow the tiger-like marking rules established across his main torso and limbs.

- 📐 **The Flame-Shaped Tip Construction**: The tail terminates in a distinct, elongated flame-shaped tip. This bulbous fur tuft expands softly before narrowing into a sharp point, completely devoid of any purple stripes to ensure high visual contrast against dark level backgrounds.

- 🦴 **The Skeletal Bone Chain Constraint (В процессе обсуждения)**: The internal skeletal structure of the tail mesh requires a high-priority chain layout to drive smooth procedural movements and wind physics.
    - **The Target Rig Count**: The development blueprint sets a baseline of exactly **12 skeletal bones (vertebrae)** to ensure hyper-fluid physics animation during sprinting and platforming phases.
    - **The Development Clause**: This specific bone count modifier is currently flagged as tentative; the final internal joint allocation remains subject to future balance optimization reviews with the animation and engineering teams.

---

#### HEIGHT & AGE

- 🎂 **Age Translation:** Witya Peros is currently 22 years old in Fustix chronology. Due to the prolonged maturation curve of the Fustix species, this age translates directly to a human developmental baseline of **12–13 years**. Animations and idle loops must emphasize this adolescent behavior, avoiding heavy military pacing in favor of agile, energetic, and slightly uncoordinated teenage motion profiles.

- 📐 **Growth & Stature Metrics:** Witya current height is 1.5 meters, reflecting his young stage of development. Full adult height for the Fustix species ranges from 1.7 to 1.8 meters. His proportions and head-to-torso ratio should be 1:5.5 relative to his overall height.

---

#### **⚙️** TAIL SKELETAL RIGGING & BRUSH PHYSICS

- 🦴 **Tail Bone Chain**: The tail skeleton uses an independent 12-bone chain (`Tail_01` to `Tail_12`) branching directly from the spine base. The rig applies a custom Spline-IK solver to guarantee fluid, organic curving and whip-like trailing movements without mechanical mesh tearing along the stripes.

- 🖌️ **Tail-Tip Brush Physics**: The fluffy tip brush (with 70mm fur) is decoupled from rigid bone deformation. The vertices of the brush mesh use an independent Jiggle Physics weight profile. When the tail snaps to a sudden stop, the tip executes a secondary, delayed inertia wobble to emphasize its loose, fluffy mass.

- ⚖️ **Kinematic Balancing**: The tail's dynamic physics simulation continuously checks the character speed. During high-speed sprints, jumps, or ledge-hangs, the tail chain automatically shifts its blending weights: it tilts upward and curls into an S-shape along the pitch axis to act as an aerodynamic counterweight for Witya's 1.5-meter body.

---

#### **⚙️** M. Acrobatic Motion Suite & Velocity Interpolation

- 🚀 **Adolescent Jump:** The jump animation (`Jump_Launch`) must shift Witya's center of gravity slightly forward. During the first 5 frames of upward acceleration, the spine bone rotation must overshoot its forward tilt by exactly **7 degrees**. This architectural offset simulates an enthusiastic but slightly uncoordinated teenage leap, where the lower limb pushes the body faster than the upper torso can balance in real-time.

- 🏹 **Evasive Side-Jump & Air Streamlining:** The system completely rejects ground dodge-rolls. For tactical dodging, Witya executes a sharp, high-velocity directional side-jump (`Dodge_Side_Jump`). Witya maintains a streamlined posture while his 12-segment tail extends straight back to act as a dynamic counterweight. To optimize aerodynamics, the four dynamic leaf-ears simply fold along the air current vector to prevent clipping and emphasize drag velocity.

- ⚖ **Recovery Impact & Balancing:** The landing phase animation (`Jump_Land`) avoids a rigid, military shock-absorption stance. Instead, the feet slide forward on the floor by an additional **5% of total velocity** to simulate loose joint dampening. The upper spine and head bones execute a secondary overshoot wobble (a recovery bounce) over 8 frames, forcing Witya to swing his arms outward slightly to catch his balance before snapping back into the combat idle blend space.

---

### 🎬 LEVEL DESIGN SPECIFICATION: INTRO SEQUENCE & CAMERA BLUEPRINTS
### **🪐** PHASE: THE TERMINAL SHORT-CIRCUIT (WITYA'S GARAGE-HANGAR)

- 🚀 **Location:** Inside the cockpit framework of Witya's custom **Spacewar Messking** spacecraft.

- 🔧 **Intro Character Animation:** Witya Peros’s (registered under the tag `The_Mechanic`) is leaning over the central dashboard panel, manually holding two exposed wiring harnesses and twisting them together.

- 📟 **Dashboard Ignition Failure:** The central dashboard monitor flashes an amber boot-up sequence, attempts to ignite, and instantly forces a system shutdown back into a black, deactivated screen.

- 💬 **Witya:** _(Sighs heavily, wiping grease off his face)_ "Ugh, come on... When am I finally gonna be able to purge this P.A.R.I.S. (Pilot's Assisting Robotic Ignition System) out of this Franchise firmware system?!"

---

#### 🛠️ 1. CAMERA SHIFT: THE ORBITAL INTERCEPT

- 🔒 **First-Person Lock:** The camera smoothly transitions to a first-person view (from Witya's perspective). His gaze is directed downwards—at the dead panel monitor and the wires clutched in his hands.

Witya: "I definitely don't have time for another hacking attempt..."

- 💥 **Sound Trigger:** A powerful explosion is heard.

- 🌌 **Skybox Animation:** Remaining locked in First-Person mode, Witya's head tilts sharply upward. On the skybox, a dynamic animation of a burning, heavily damaged escape shuttle (Kit's transport craft) activates, leaving a thick smoke trail through the atmosphere.

- 🎥 **Camera Transition:** The camera detaches from first-person view, switching to the standard third-person game mode (viewed from behind the character).

---

#### 🎮 2. THE GAMEPLAY HANDOFF: PLAYER CONTROL INITIALIZATION

- 🤸 **The Jump Animation:** Witya vaults aggressively out of the open cockpit, dropping downward toward the dusty ground.

- 💥 **The Three-Point Landmark Landing:** Witya lands on the ground executing the iconic three-point defensive landing pose.

- 🔧 **The Armament Draw:** His primary **VersaWrench** tool is drawn and snapped into his right-hand. Witya rises into his baseline stance.

- 🕹 **The Control Handout State:** The camera locks behind Witya's shoulder. All UI HUD elements initialize. Control configuration are permanently handed over to the player. Mission 1 Gameplay Unlocked.

---

### **📡** TECHNICAL APPENDIX: ALT PERSPECTIVE

- 🌍 **The Baseline Protocol (Primary Target):** The gameplay of M&K is systematically engineered from a Third-Person Perspective (Режим от третьего лица) to optimize vertical 3D platforming precision and spatial management.

- 👁 **The Alternate Perspective (First-Person Pass):** The production authorizes the development team to analyze and consider a First-Person view (Вид от первого лица) as a viable gameplay override or toggle option.

- 🛑 **The Blind-Spot Constraint Resolution:** To counteract the primary developmental challenge of first-person platforming—specifically the complete lack of rear visibility—the architecture deploys Witya's unique biological advantage - integrated tracking system.

---

#### **🧬** 2. The HICA Serum & The Leaf-Radar

- 💉 **The HICA Modification Origin:** The high-intensity threat detection grid is directly powered by the HICA (High Integrated Combat Adaptation) Modification — the definitive serum injected into Witya's cellular system by Selene Kriptos, Witya's mother, after Skad Peros (Witya's Father) forced her to do so to guarantee the survivability of their child.

- 👂 **The Biological Acoustic Tracker:** As a direct consequence of the HICA alteration, Witya's four leaf-ear membranes function as advanced organic sensory receivers.

- 🖥 **The Interface Translation:** The membranes continuously monitor rear air pressure shifts and echo-locate via internal ultrasonic pulses. If a threat enters his rear blind spot, the system processes this biological telemetry in real-time, casting intuitive, high-bloom hazard indicators directly onto the borders of the player's HUD to give absolute spatial awareness even within a strict first-person viewpoint.

---

### **🧬** MODULE: THE HICA PROTOCOL (THE PROTAGONIST INVINCIBILITY ANOMALY)

#### **🧪** 1. Technical Nomenclature & Military Origin

- 📝 **The Systemic Definition:** The operational designation HICA is officially registered as High Integrated Combat Adaptation.

- ⏳ **The Historical Benchmark:** This military-grade bio-chemical serum was invented by Fustix - Fluffy. That Serum allowed the Fustix - Tufted to achieve definitive strategic victory and neutralize the Shrampite forces during the first Great War. Following the conflict, the blueprint was permanently lost.

---

#### **🔬** 2. The Cryptos Deception & The Interspecies Experimentation

- 🤫 **The Super-Heritability Myth:** The chemical compound was secretly reconstructed by Selene Cryptos. To mask her tests, she manufactured a comprehensive systemic lie regarding the serum's "Super-Heritability".

- 🧬 **The Target Testing Lineages:** The testing of reconstituted serum HICA serum tracks exactly three historical validation points within the database:

    1. _The Compatibility Status:_ The bio-chemical compatibility profiles of the HICA serum regarding both the Tufted and Fluffy Fustix races are historically fully documented and verified within the database.
	2. Selena Kriptos conducted the first compatibility test of the restored serum on herself. Then, she tested it on her daughters: Apocrys Despar (Axiom) and Aidex Despar (Axiom).
    3. _The Juvenile Testing:_ The execution of the illegal injection phase onto Partys Solis by Selene Cryptos was calibrated strictly as a milestone age check. The target objective was to verify if a developing juvenile organism could stabilize and survive the RNA interceptor cells of the combat adaptation.
    4. _The Witya Destination Loop:_ The data harvested from Partys was utilized to check the safety of the injection to Witya. Because Witya could not be sent into encapsulated Dimension with the rest of the Fustixes, the modification was executed by his Father as a desperate, baseline survival buffer to maximize his survivability even if Antichent found him.
    5. _The Jord Solis Search Directive:_ Jord Solis forcefully modified himself with the HICA compound, leveraging its extreme combat survival metrics to endure any threats while executing his tracking sequence to locate his lost daughter, Partys.

---

**🎮 3. GAMEPLAY HARD-CODING: THE UN-KILLABLE PROTAGONIST JUSTIFICATION**

- 🛡 **The Mechanical Convention Shield:** Within the gameplay sandbox, the HICA serves as the absolute, ironclad narrative justification for standard active action tropes. Witya's capacity to absorb heavy plasma impacts, survive terminal velocity falls, and execute seamless frame-perfect combat counter-maneuvers is not a generic design oversight—it is the direct runtime output of the High Integrated Combat Adaptation rewriting his cellular reflexes in real-time.

---

### **📥** PHASE: MISSION INITIALIZATION (THE CRASH SITE)

-  **💼The Gismotron Activation Prompt**

- 🛠 **System Trigger Event:** Upon level load, a modal UI window instantly pops up over the player's screen: "Activate the Gismotron helper module?"
- 🔀 **User Choice Branching:** If the player selects YES, Witya delivers his replicue:

**Witya:** It's not like I have amnesia, but... Fine. Just like back in school. If only school actually existed here.

- 🚫 **System Tutorial Constraint:** The game engine does not display standard movement control prompts (D-SAW / WASD).
- 🎥 **The Camera Orientation Vector:** The Gismotron AI helper module broadcasts its instruction line:

**Gismotron Assistant:** Use [INPUT_CAMERA_MOVE] to rotate vision and look at the Unbinil Bolt positioned at the top of that cliff.

- 💻 **Platform Translation Note:** The tutorial script dynamically adapts based on the active hardware platform. On PC, this training phase requires only mouse movement.

---

### **🗺️** LEVEL DESIGN TOPOLOGY

**🧲 Return after unlocking Clingstifts**

- **Level Geometry:** Adjacent to Witya's starting position sits a massive cylindrical cliff. A short distance away from its base lies the starship crash site sector, displaying white hull textures that have been stripped and scavenged by junkers.

- **Environmental Interaction:** During the initial crash, this cliff scraped a significant section of the ship's hull. This collision left a pathway composed of white modular plates running straight up to its peak. This path as impassable during Act I, requiring the player to return later once the **Clingstifts** are unlocked.

- **Level Objective:** Positioned dead-center at the absolute peak of this cliff sits the **Unbinil Bolt**.

- **Camera Raycast Trigger:** As soon as the player's camera focus hits the **Unbinil Bolt** detection box, Witya starts his reaction dialogue:

Witya: How long has that thing been an eyesore to me?

---

####  **⚙️** UI/UX WIDGET & INPUT CAPTURE NOTES

- 🖥 **Gismotron Modal Pop-up Layout:** Upon level load, the UI manager displays the `W_Gismotron_Prompt` widget directly on the screen overlay. The background uses a Gaussian blur filter (strength 5.0) to cleanly separate the tutorial prompt from the game environment. The layout features two interactive buttons (YES / NO), defaulting focus instantly onto the confirmation button for fast controller input mapping.

- ⏳ **Gameplay Tick & Animation Pausing:** While this prompt is active on the screen canvas, the engine applies a strict global pause rule (`Custom_Time_Scale = 0.0`), freezing all physics-driven entities, background environment scripts, and Witya's idle animations.

- 🔀 **Input Branching Logic:** Selecting "NO" triggers a quick blur-disabling animation and instantly returns the screen to standard game mode. Selecting "YES" enables UI credits at the bottom of the screen, in addition to the voiceover prompts from the sphertron.

---
### **📺** MISSION TUTORIAL: THE THREE-POINT PATHWAY (THE CRASH SITE)

- **Visual Sequence:** As soon as Witya's previous audio line finishes playing, the Gismotron helper module triggers its next instructional event.

**Gismotron Assistant:** The approximate crash sector is located beyond the civilian district bounds. Please use [INPUT_CAMERA_MOVE] to watch toward the target route vectors.

- **Camera Restriction:** The player must rotate their camera transform by exactly 180 degrees to look backward. Positioned directly in this line of sight is a destroyed bridge.

**Gismotron Assistant:** The civilian district lies on the other side of the bridge. Safe travels!
**Witya:** The bridge is disassembled!

- **Control Handover Pass:** Full movement input control (D-SAW) is instantly released to the player.

---

#### **🗺️** LEVEL DESIGN PATTERNS: INTERACTIVE ENVIRONMENT POIS

- - 📍 **Point of Interest 01: The Cliff Anchor**
- **Interaction:** The player can guide Witya toward an isolated ledge standing dead-center on a small clearing. The clearing is tightly hemmed in by a sheer cliff wall, acting as a hard boundary for this area. Upon entering the 3-meter bounding box trigger of the ledge, Witya fires his line:

**Witya:** I can't climb up there without Clingstifts.

- 📍 **Point of Interest 02: The Scavenged Starship Hull**
- **Interaction:** The player can approach the emergency crash site of the starship. The visual assets must convey a high-impact crash sequence: the hull is aggressively flattened against the rocks, the cockpit module is entirely crushed, and heavy boulder debris partially buries the frame. Multiple component sockets is bare, visually indicating where parts have been forcibly unscrewed and stripped. Upon intersecting to the ship's, Witya reacts:

**Witya:** Everything's fine. Boris managed to eject. And he already didn't have an arm.

---

### **⚙️** MATERIAL & CRASH DEBRIS SHADER PROPERTIES

- 🔥 **Procedural Hull Damage & Old Burn Marks**: The ship's material uses vertex offsets to show old dents and crushes around the cockpit crash site. Hit zones blend into a weathered burn texture, overriding the base paint with carbon soot, scratch maps, and deeply eroded bare metal from long exposure to the elements.

- 🔧 **Scavenged Parts & Rusted Bolt Holes**: To show that looters stripped the ship clean long ago, empty mounting sockets use a dedicated Material ID. The shader applies a rough, matte rust mask inside bolt holes and wire tracks. This cuts the specular shine and contrasts with the clean hull, instantly catching the player’s eye.

- ➔ **Dried Fluid Stains & Baked-In Dust**: The cabin geometry has three vertex-color anchor lines. The shader dynamically tweaks roughness and cavity tinting here to display old, dried-up green coolant streaks and thick layers of planetary dust. This texture buildup realistically blurs and distorts the light under the broken canopy glass.

---

- #### 🗺 POINT OF INTEREST & CAVERN NAVIGATION

📍 **Point of Interest 03: The Broken Bridge & Leap**
- **Level Geometry Interaction:** The player can guide Witya directly to the edge of the broken bridge and jump into the canyon. Witya survives the fall with zero damage due to the HICA serum. The moment his feet hit the canyon floor, Gismotron dynamically recalculates the route, triggering a deadpan GPS voice line:

**Gismotron Assistant:** Route recalculated. Turn upward.

---

### **📥** PHASE: CANYON & CAVERN NAVIGATION (ACT I)

- - 🧱 **Terrain Environmental Constraints**
- **The Lower Canyon Layout:** Upon jumping down from the broken bridge, Witya lands near a slow-moving river spline. The canyon path is bounded linearly: Vector A is permanently blocked by a static rock landslide mesh, while Vector B leads to the entrance of the cavern sector.

---

### **⚔️** COMBAT INITIALIZATION: MELEE SANDBOX TUTORIAL

- - 🔧 **The VersaWrench Close-Quarters Vector**
- **Cavern Trigger Volume:** As soon as Witya's intersects the cavern interior line, the Enemy Manager spawns the Cave Crab.
- **Enemy Blueprint (Cave Crab):** A four-legged (not mistake!) biological enemy with a bluish-blue shell. The crab's height is about the same as Witya's knees. Its forelimbs have elongated claws, visually resembling those of a freshwater crayfish.
- **Voice-Over Trigger Event:** Gismotron immediately registers the hostile presence and plays the melee tutorial line:

**Gismotron Assistant:** Launching self-defense segment. Input [INPUT_FIRE] to execute a physical strike uzing the VersaWrench.

- 🔥 **The High-Velocity Exothermic Death VFX**
- **Combat Balance:** The standard Cave Crab actor holds a fixed health pool equivalent to exactly 2 VersaWrench impact cycles.
- **The Death Event:** Upon reaching zero health, the crab model does not fade away smoothly, but triggers an explosion effect, creating a spray of bright blue liquid particles that quickly disperse in all directions.

- 🪓 **The Ranged VersaWrench Projectile Attack**
- **Secondary Group:** When Witya moves deeper into the cave, he will activate the second zone with enemies, and Veshchtron will give a training line:

**Gismotron Assistant:** Input [INPUT_MELEE_THROW] to initiate a ranged attack of the VersaWrench.


---

### **🗺️** THE NIRGENIUM VEIN

- - 🦀 **The Non-Lethal elite enemy Encounter**

- **Cavern Path Branching:** The internal layout splits into two distinct tunnels.

- **The Left Vector Route:** The left corridor contains the Crab Matriarch.

- **Advanced Enemy Design Blueprint (Crab Matriarch):** This massive creature features one raw, glowing Nirgenium shard growing directly from its top shell. The enemy is not aggressive: when the player appears, it enters flight mode.

- **The Resource Extraction:** The Crab Matriarch is completely immune to Witya's basic weapons and blaster damage. To extract the minerals, the player must land exactly 5 VersaWrench strikes specifically at a single leg.

- **The Stun Window:** Upon absorbing the 5th regional hit, the crab triggers a temporary 10-second stun state (`Stun_Down_Idle`). Witya can jump onto its back to harvest the Nirgenium shard.

- **The Recovery Automation Sequence:** As soon as the internal 10-second timer ends, the crab exits its stun state, resets its leg damage, and resumes its standard fast-paced run behavior.

- **Lore Information Broadcast:** Once the player completes the resource collection event, Gismotron updates the item inventory log with a vocal breakdown:

**Gismotron Assistant:** Nirgenium. An extremely rare substance, highly valued due to its energetic potential. Its ability to store a huge number of electrons makes it a highly sought-after raw material for the production of batteries and capacitors, despite the radio waves constantly emitted by the crystal.

---

#### 💎OBJECT SPECIFICATION: NIRGENIUM CRYSTAL (MATERIAL PROFILE)

- 🔮 **Crystal Lattice & Refraction Index**: The 3D model of the Nirgenium Crystal uses a specialized semi-translucent material template designed to simulate a dense, high-value mineral structure. The material features a high refraction index (set to 1.72) and a strict roughness limit (clamped between 0.02 and 0.08). This technical configuration ensures that the sharp, low-poly gemstone facets crisply capture all ambient lighting and screen-space reflections (SSR).

- 🔷 **Inner Energy Core & Cyan Pulsation**: To emphasize the raw energy potential of the crystal, its core uses a layered 3D noise texture modifier paired with a low-frequency pulsing algorithm. The core glows with a deep neon-cyan and electric-blue light spectrum, smoothly changing its brightness intensity by 20% every 1.5 seconds. This visual loop conveys massive internal energy, allowing the player to easily track hidden Nirgenium veins even in total cavern darkness.

- 🦀 **Material ID Splitting & Blend Mask**: When the crystal mesh compiles onto other actors (such as growing directly out of the **Crab Matriarch armor shell** or heavy metal debris piles), the cluster is assigned a unique Material ID slot. At the intersection vectors where the blue mineral meets organic chitin or rusted steel, the vertex shader procedurally generates a custom blending mask with rust and limescale textures. This mask completely hides sharp geometry seams, making the premium crystal look naturally grown and seamlessly fused into the boss's carapace.

---

#### **⚙️** TECHNICAL & VFX NOTES: STREAMING BLUEPRINT

- 🧪 **Blue Slime Spawn**: When a Cave Crab dies, the engine instantly replaces its skeletal mesh with a dynamic Niagara particle effect. Phase 1 triggers a high-velocity radial explosion, spawning 30 to 40 medium-sized fluid meshes with a glossy, opaque cyan material. To keep the slime looking organic, apply sub-surface scattering (SSS) directly to these meshes.

- 💥 **VFX Splat Collision Decals**: Slime particles must interact dynamically with the cave environment. When a particle hits static geometry (floor, walls, or ceiling), it destroys itself and projects a dynamic texture: a Cyan Splatter Decal. To optimize memory, these decals use a smooth fade-out script: maintain 100% opacity for 3 seconds, then linearly fade the alpha channel to 0 over exactly 30 frames.

- 🧹 **Memory Garbage Collection**: To maintain a stable framerate during intense combat or speedruns, all secondary dust, slime debris, and local collision boxes must be cleared from streaming memory within 1 second after the explosion. The engine must immediately disable physics registration for these models, keeping the navigation mesh (`navmesh`) perfectly clean for player movement and new enemy waves.

---

#### **⚙️** MELEE STRIKE ANIMATION & KINETIC WEIGHT SYSTEM

-  📐 **Anticipation Phase & Weight Shift**: The basic strike animation (`wrench_strike_01`) uses a 4-frame anticipation window for the swing preparation. During these frames, Witya's hips and spine twist backward by 12 degrees along the yaw axis, shifting his center of mass over his back foot. This movement builds kinetic energy, showing that the heavy wrench has real physical weight that Witya's body must balance.

- ⚡ **High-Velocity Strike & Motion Smear**: The swing executes quickly over 3 frames, creating a massive acceleration spike. To keep the animation smooth at high frame rates, the wrench and Witya's right arm trigger a custom motion blur effect. This vertex-stretching mesh fills the gaps between keyframes, creating a clean, sweeping arc that makes the attack feel razor-sharp and snappy.

- 💥 **Impact Constraint & Deflection Bounce**: Upon hitting a Cave Crab, the animation triggers a Hit-Stop effect, freezing root motion for exactly 2 frames to emphasize the impact. Right after, the wrench chain executes a subtle 4-frame recoil backward along the reverse swing trajectory, forcing Witya's shoulders to absorb the reaction force before blending back into the standard combat idle.

---

#### **⚙️** WEAPON SANDBOX & PROJECTILE PHYSICS

- 🔄 **Dual-Phase Trajectory Interpolation**: The VersaWrench projectile blueprint uses a two-phase state machine. **Phase 01 (Launch Vector)** applies a linear velocity modifier over a 10-meter range. Upon hitting max range or an enemy hitbox, it switches to **Phase 02 (Return Vector)**, using a dynamic Bezier spline calculation to smoothly route the tool back to Witya's active right hand (`Hand_R`).

- 📐 **Rotational Angular Velocity & Hitbox Sweep**: While flying, the wrench spins 360 degrees along its local yaw axis at a high speed of 720°/s. To avoid requiring precision pixel targeting from the player, the collision volume expands during flight using a rolling sphere-sweep trace to accurately detect and damage nearby Cave Crabs.

- ↪️ **Dynamic Catch Realignment & Obstacle Pass**: If Witya does an evasive side-jump during Phase 02, the wrench’s attraction vector increases its acceleration multiplier by 15% per frame to adjust to the new coordinates. If blocked by static geometry on return, its wall-impact physics temporarily deactivate, allowing VersaWrench to pass through obstacles straight back to the character instead of getting stuck.

---

#### **⚙️** UI/UX CANVA & HUD RESOURCE TRACKING NOTES

- 🖥️ **Dynamic Auto-Hide HUD Layout**: The Bolt Counter and Nirgenum Crystal Counter widgets share a screen-space UI canvas layer in the top-right corner. To keep the screen clean during gameplay, these elements use an auto-hide script. If no resources update for 3.0 seconds, the widgets smoothly slide 150 pixels off-screen along the positive X-axis.

- 🔩 **Bolt Counter & Icon Juice**: The Bolt tracking slot features a high-quality 2D render icon of a classic mechanical silver nut. When a Bolt enters Witya's vacuum collection radius, the counter numbers smoothly roll up rather than snapping instantly. Simultaneously, the nut icon spins 360 degrees along its Z-axis and triggers a 1.15 scale bounce over 8 frames for satisfying visual feedback.

---

#### **⚙️** WEAPON SANDBOX & VACUUM PHYSICS

- ↪️ **Nirgenium Shard Intake**: When a crystal vein is destroyed, 1 or more shards with physical behavior are created. **Phase 01** triggers an explosion in the opposite direction of the impact to realistically throw the shard. After 0.5 seconds, **Phase 02 (Intake)** is triggered: the shard's collision is disabled, and it flies along the shortest trajectory directly to Viti's chest cartridge.

- 📐 **Velocity Scaling & Distance Acceleration**: The vacuum pull cannot use a fixed speed. The system uses distance-based acceleration: as a floating shard gets closer to Witya's chest coordinates, its speed scales up by 1.25x per frame. This ensures shards snap into the hero with a fast, satisfying impact, avoiding slow, lazy hovering.

---

#### **⚙️** ENEMY ANIMATION STATES & PLATFORM OVERRIDE NOTES

- 🏃 **Kinematic Deceleration & Heavy Collapse**: At the exact frame where the 5th hit registers on the target leg collider, the Crab Matriarch’s movement must instantly freeze. The boss triggers the `stun_Down_Start` transition over 8 frames: the entire model drops flat onto the cavern floor along the Z-axis, slamming its belly plates down to turn the shell into a stable, solid platform.

- 💫 **Stunned Eye Movement & Shell Vibration**: While locked in the 10-second `stun_Down_Idle` loop, the Crab Matriarch's head and pincer joints play low-frequency, uncoordinated twitching animations to show its stunned state. Its eye stalks spin outward in opposite directions, and the Nirgenium shard on the back begins to vibrate finely and quickly due to the material, creating the feeling that the crystal is about to fall off.

- 🧱 **Static Platform Collider Toggle**: Exactly at the final frame of the collapse animation, the Crab Matriarch's dynamic character collision box is temporarily overridden. The system activates a secondary, rigid static box collider (`Col_Shell_Platform`) directly over the back shell geometry. This ensures that if Witya stands or jumps on the crab's back, his movement vectors register the shell as standard solid ground rather than an enemy.

---

### **📺** MISSION TUTORIAL: THE ELEVATOR & EXTRACTION PROTOCOL

- 💼 **The License Sequence**

System Text Display: Immediately following the resource collection event, silent unvoiced text flashes across the player viewport grid: _"Searching for mineral extraction license... License found..."_

**Witya:** Thanks for the repack from... Sorry, I forgot your name.

---

### 📥 PHASE: VERTICAL LIFTOFF (THE ELEVATOR PLATFORM)

**Level Path Branching:** A right turn directs Witya toward a next enemy spawn point and an interactive elevator platform. Positioned centrally on the platform is a large red button.

**Gismotron Assistant:** Press the button to activate the lift.  
**Witya:** Inhale to activate breathing.

**Button Interaction Mechanics:** The player must position Witya onto the platform and look directly at the button. The button triggers a low-intensity highlight shader layer. Inputting `[INPUT_FIRE]` activates the lift's movement.

**Level Target Object:** At the very top of the elevator's ascent is the first Hophytum vein. Once the player collects it, Gismotron Assistant will say its line:

**Gismotron Assistant:** Haufitum. A common metallic crystalline substance used in a wide variety of applications, from household appliances to starship hull plating.

---

#### ⚙️ SECRET QUEST TRIGGER & AI BEHAVIOR OVERRIDE

- 🗺️ **Matriarch Elevator Trap Sequence**: To trigger this hidden event, the player must execute a strict sequence of level interactions. First, Witya must activate the lift platform and fully open the cavern exit blast doors. The player must then descend back to the lair, engage the Crab Matriarch, and land precisely 4 strikes on its leg bone colliders after which catches the moment when the crab stands on the elevator platform.

- ⚡ **Hit-Stop Stun & Vertical Platform Lift**: Once the Matriarch steps inside the lift platform's trigger zone, the player must land the 5th strike within a strict, narrow time window. This impact forces a 10-second high-priority animation state (`stun_Down_Idle`), completely overriding its standard combat AI. If the player fails to land this final hit, the Matriarch instantly runs off the platform. If successful, activating the lift carries both Witya and the stunned boss up to the surface zone.

- 🚪 **Outdoor Evacuation & Gate Closure**: At the upper level, the player must drive the Crab Matriarch entirely out of the cave onto the open terrain near Witya's Garage. The player must then quickly interact with Bolt Gyrate to close the main blast doors. The game logic requires the gate to remain fully closed for exactly 5.0 seconds.

- 🦀 **The Allegory of the Cave Behavior Shift**: Upon tracking a 5.0-second closed door state beneath the open sky, the Matriarch's AI state machine updates its global pathfinding. The creature changes its behavior permanently: once the doors re-open, it sprints in pure panic back toward the gate, hard-locking its position in the furthest, tightest corner outside. This permanently reduces its active movement radius by 70%.

- 🏆 **Achievement Unlock Event**: The successful completion of this secret sequence calls the Steam achievement manager, granting the player a hidden unlock notification: **"The Myth of the Cave"**.

---

#### 💎 HAUFITUM CRYSTAL (MATERIAL ID PROFILE)

- 🔮 **Crystalline Lattice & Refraction Index**: The Haufitum crystal mesh uses a custom translucent material shader to simulate a dense, metallic crystalline structure. The material requires a high refractive index of 1.65 and a strict roughness clamp (0.05 to 0.1). This ensures that the sharp, low-poly edges of the facets cleanly catch ambient lighting and screen-space reflections (SSR).

- 🔥 **Inner Metallic Core & Emissive Pulse**: To emphasize its conductive, industrial nature, the core uses a 3D noise texture map paired with a low-frequency emissive script. The core pulses with a deep neon-orange glow, shifting intensity by 15% every 2 seconds to simulate metallic energy and keep the crystal veins visible even in pitch-black caverns.

- ⚙️ **Material ID Allocation & Occlusion Mask**: When integrated into other models (like the Crab Matriarch's shell or junkyard debris), the crystal cluster uses a dedicated Material ID. The boundary vertices where mineral meets shell or metal generate a procedural rust and calcification occlusion mask. This effect hides sharp mesh seams, making the crystal look naturally embedded.

---

#### **⚙️** UI/UX CANVA & DYNAMIC RESOURCE ACCUMULATION

- 💎 **The Haufitum Dynamic Pop-up Indicator**: When a crystal cluster breaks from a VersaWrench strike, the counter smoothly slides onto the screen from the right edge. Instead of jumping instantly to the new total, the UI displays a neon-orange sub-text directly next to the main value (formatted as `+ [x]`). This indicator shows the exact number of harvested crystals currently flying toward Witya.

- 📥 **The Counter Absorption Phase**: Once the physical crystal debris finishes its vacuum trajectory and hits Witya's collision box, the counter triggers the absorption phase. The main number rolls up quickly over exactly 15 frames, while the secondary `+ [x]` text scales down and fades away. After 3.0 seconds with no further updates, the tracker slides back off-screen into its hidden state.

- 💎 **Haufutum Crystal Counter Profile**: The Haufitum tracker uses a high-contrast neon-orange crystalline vector icon matching the approved crystal material. When a resource is collected into Witya's Chest Cartridge, the text counter increments. In parallel, a wave-distortion sheen pulses horizontally across the crystal icon from left to right, paired with a crisp, high-frequency UI sound effect.

- ↪️ **Haufitum Shard Vacuum**: Breaking a crystal vein spawns 3 to 5 physics-based shards. **Phase 01** applies a random outward explosive push to scatter debris across the cave floor. After a 0.5-second delay, **Phase 02** starts the vacuum retraction: shard collisions deactivate, and the pieces track a real-time path straight toward Witya's chest cartridge.

---

#### **⚙️** LEVEL DESIGN SHORTCUTS: THE BOLT GYRATE INTERACTION

- 🔄 **The Loop Closure Vector**

**Level Geometry**: Positioned directly behind the Unbinil Bolt is the **Bolt Gyrate** (a massive structural bolt centered on a circular platform grid). Witya uses his VersaWrench to turn this. The bolt does not screw downward; instead, it acts as a drive shaft to rotate the internal machinery beneath the platform. As soon as Witya steps onto the platform, Gismotron registers the interaction:

**Gismotron Assistant:** Input [INPUT_FIRE] to interface with the Bolt Gyrate and open the heavy door.

**Combat Override**: During active combat, all interaction with the Bolt Gyrates is strictly disabled. Outside of combat, stepping onto the platform remaps the `[INPUT_FIRE]` command into a continuous rotational interaction loop. The interaction is fully repeatable: re-activating the platform reverses the state, sealing the heavy door back into a closed state.

**Shortcut Link**: Beyond the unlatched threshold lies the initial crash site sector—seamlessly wrapping the level design back to the exact coordinate origin of Witya's journey.

---

#### **⚙️** INTERACTION & GYRATE ROTATION PHYSICS

- ☑️ **Gyrate Alignment & Mechanism Turning**: When Witya steps onto the platform and holds `[INPUT_FIRE]`, the character automatically snaps his position to the center of the mechanism. The sustem tracks a changing `Gyrate_Rotation_Angle` variable clamped between 0.0 and 360.0 degrees. Each frame of player interaction applies a smooth turning speed, forcing the VersaWrench and the mechanical shaft to rotate in perfect synchronization.

- 🏋️ **Animation Weight & Resistance**: The interaction uses a dedicated two-handed animation (`wrench_Gyrate_Loop`). To visually show mechanical strain and heavy resistance, Witya's spine and arms apply a 15-degree upward lean offset. If the player releases the button before reaching the full 360-degree completion point, the system triggers a passive reverse-turn, slowly spinning the Gyrate bolt back to its starting position over a 45-frame window.

- 🚪 **Linked Movement & Door Unlatching**: The value of the `Gyrate_Rotation_Angle` links directly to the movement of the heavy door. Reaching maximum rotation triggers a physical latch-snap sound effect, sets the gate to a permanent Unlocked state, and releases Witya back into the standard movement. If the player interacts with the completed mechanism again, the system reverses, closing the door back into a locked state.

---

#### **⚙️** LEVEL DESIGN SHORTCUTS: THE BOLT GYRATE INTERACTION

- 🔄 **The Loop Closure Vector**

**Level Geometry**: Positioned directly behind the Unbinil Bolt is the **Bolt Gyrate** (a massive structural bolt centered on a circular platform grid). Witya uses his VersaWrench to turn this. The bolt does not screw downward; instead, it acts as a drive shaft to rotate the internal machinery beneath the platform. As soon as Witya steps onto the platform, Gismotron registers the interaction:

**Gismotron Assistant:** Input [INPUT_FIRE] to interface with the Bolt Gyrate and open the heavy door.

**Combat Override**: During active combat, all interaction with the Bolt Gyrates is strictly disabled. Outside of combat, stepping onto the platform remaps the `[INPUT_FIRE]` command into a continuous rotational interaction loop. The interaction is fully repeatable: re-activating the platform reverses the state, sealing the heavy door back into a closed state.

**Shortcut Link**: Beyond the unlatched threshold lies the initial crash site sector—seamlessly wrapping the level design back to the exact coordinate origin of Witya's journey.

---

#### **⚙️** INTERACTION & GYRATE ROTATION PHYSICS

- ☑️ **Gyrate Alignment & Mechanism Turning**: When Witya steps onto the platform and holds `[INPUT_FIRE]`, the character automatically snaps his position to the center of the mechanism. The sustem tracks a changing `Gyrate_Rotation_Angle` variable clamped between 0.0 and 360.0 degrees. Each frame of player interaction applies a smooth turning speed, forcing the VersaWrench and the mechanical shaft to rotate in perfect synchronization.

- 🏋️ **Animation Weight & Resistance**: The interaction uses a dedicated two-handed animation (`wrench_Gyrate_Loop`). To visually show mechanical strain and heavy resistance, Witya's spine and arms apply a 15-degree upward lean offset. If the player releases the button before reaching the full 360-degree completion point, the system triggers a passive reverse-turn, slowly spinning the Gyrate bolt back to its starting position over a 45-frame window.

- 🚪 **Linked Movement & Door Unlatching**: The value of the `Gyrate_Rotation_Angle` links directly to the movement of the heavy door. Reaching maximum rotation triggers a physical latch-snap sound effect, sets the gate to a permanent Unlocked state, and releases Witya back into the standard movement. If the player interacts with the completed mechanism again, the system reverses, closing the door back into a locked state.

---

### 🕹 PHASE: THE CANYON CORRIDOR (THE GORGE VECTOR)

- 🗺 **The Routing Recalculation Sequence**

**Level Geometry:** Positioned between the starship crash site and the destroyed bridge sits a second bridge leading directly into a narrow gorge sector. This is the mandatory path for Act I.

**Visual Sequence**: As soon as Witya steps onto the far edge of this bridge, the Gismotron helper module reactivates its route override prompt:

**Gismotron Assistant:** Route recalculated. Please turn around.  
**Witya:** Hey, how about you go ahead and load actual map?  
**Gismotron Assistant (Subtitle UI Layer Overlay):** Updating map...

---

#### **⚔️** COMBAT VARIETY: THE RANGED INTERRUPT TUTORIAL

- 🐸 **The Hornet Toad Enemy Profile**

**Enemy Spawn Mechanics**: Inside the gorge corridor, the enemy manager spawns the **Hornet Toad**. These enemies group in small packs of 3 to 5 units.

**Enemy Combat Mechanics (Hornet Toad)**: The unit uses a sandy-yellow base texture. The enemy holds a small health pool equal to exactly 2 VersaWrench strikes.

**The Ranged Tongue-Whip Attack**: The **Hornet Toad** targets Witya using a attack based on distance, launching a fast tongue. This strike deals 0 damage but instantly  interrupts attack.

**Animation Interruption Logic**: If the tongue hits Witya’s collision box while he is swinging the VersaWrench, the engine instantly cancels his strike, and triggers a brief 0.5-second stagger animation (`Stagger_Hit_M`).

**Sand Burst VFX**: Upon reaching zero health, the enemy triggers an explosion. Spawns a dense cloud of sandy-yellow particles that match the exact color of the toad's skin.

- 🔀 **The Logical Tutorial Branching Trigger**

**System Log Check**: The game engine checks the player's level logs. IF the player bypassed the downward bridge leap and did not enter the cave zone, Gismotron executes the basic melee tutorial directly at this point.

---

### **🗺️** THE WALL PLATFORMS & BOLT CACHES

- 🧗 **The Vertical Jump Instruction Node**

**Level Geometry**: Two sturdy wall platforms are attached to the gorge wall, one higher than the other. The topmost platform contains several breakable Bolt Crates.

**Voice-Over Trigger**: When Witya enters the 2-meter proximity trigger of the lower platform, Gismotron plays the movement tutorial:

**Gismotron Assistant:** Input [INPUT_JUMP] to execute jump and reach the platform.

- 📦 **The Bolt Crate Smash & Privatization Dialogue**

**Breakable Objects Mechanics**: Once Witya climbs onto the upper platform, the player can use a VersaWrench strike to break the Bolt Crates. The impact shatters the crates, spawning independent Bolts onto the floor. These items are immediately pulled into Witya's inventory via the dynamic vacuum system.

**System Text Display**: As soon as the final Bolt is collected, a silent text notification flashes across the player's screen: "Searching for privatization license... License found..."

**Witya:** Huh, who knew I could just smash these crates and find... bolts... inside? _(Clicking the tongue)_ Nice.

---

#### **⚙️** ANIMATION INTERRUPTION & STATE MACHINE HIT-STUN NOTES

- 🎯 **Tongue Projectile Collision**: The tongue-whip fired by the Hornet Toad uses a fast line-trace or sphere-sweep collider. Upon hitting Witya's collision box, the logic ignores the `Apply_Damage` function (setting Damage to 0.0) and instantly sends a high-priority interrupt signal directly to Witya's Animation Blueprint.

- ⚔️ **Attack Interruption & State Cancel**: If the tongue hits Witya while he is attacking (`wrench_Strike_01`, `wrench_Strike_02`, or `wrench_Throw`), the engine triggers an immediate animation override. It instantly cancels the remaining keyframes, disables the active hit-box collision of the VersaWrench, and resets the action state back to zero within a single frame.

- 🔄 **Stagger Lock & Knockback Impulse**: Concurrent with the animation cancel, Witya enters a 0.5-second `stagger_Hit_M` state. During this window, all player inputs (including D-SAW movement and jump vectors) are strictly blocked. To make the impact feel physically convincing, the engine applies a small upward push, knocking Witya slightly to the toad before releasing him back into the default combat idle state.

---

#### **⚙️** BREAKABLE OBJECTS & FRACTURE LOGIC

- 📦 **Pre-Fractured Mesh & Debris Physics**: The standard Bolt Crate must be set up as a destructible object with pre-made shards. Upon hitting the box with the VersaWrench hitbox, the engine instantly replaces the intact model with 6 to 8 independent wooden debris fragments. These pieces receive a random outward push vector to scatter realistically away from Witya's swing path.

- 🔩 **Bolt Spawn & Parabolic Launch**: At the exact frame the crate breaks, the logic must spawn exactly 5 to 10 Bolt items directly inside the center of the exploded container. To make the item drop look visually rewarding, each Bolt launches with a random upward speed (clamped between 2.5 and 4.0 m/s along the Z-axis), forcing them to erupt upward in a nice parabolic fountain arc.

- 🧲 **Vacuum Delay & Flight Transition**: The spawned Bolts must temporarily ignore Witya's vacuum radius for exactly 0.4 seconds after spawning. This delay ensures the bolts finish their physical upward fountain animation before the vacuum pulling takes over. Once the timer expires, the Bolts turn off their standard gravity, switch to their fast suction state, and fly straight toward the Witya's Chest Cartridge.

---

#### **🗃️** ENEMY SPECIFICATION: HORNET TOAD

- 🎨 **Visual Design & Textures**: The character model uses a stylized hybrid topology. The body shape matches a bloated, low-slung desert toad, but its back integrates heavy, ridged chitinous plating and tiny vestigial wing-buds to add hornet-like features. The base diffuse color uses a dry, sandy-yellow palette with high-contrast, faded black stripes along the belly.

- 🔊 **Audio Design & Idle Sounds**: To hint at its hybrid nature before it enters Witya's view, the creature uses a two-phase audio profile. The default idle sound loops a low-frequency amphibian croak mixed dynamically with a high-pitched, metallic insect buzzing. When starting its tongue-whip attack, the audio cuts the buzzing and plays a high-priority, wet whip-crack sound to give the player a clear audio warning of the incoming strike.

- 🤖 **Swarm AI & Animation Offsets**: Hornet Toads ignore solitary patrol paths; the enemy manager spawns them in tight clusters of 3 to 5 units. To prevent identical animation syncing during idle states, the system applies a random time-offset (clamped between 0.2 and 1.5 seconds) to each unit's animation loop, ensuring the swarm looks naturally chaotic and uncoordinated.

---

#### ⚙️ENEMY ATTACK ANIMATION & TONGUE IK CONSTRAINTS

- 🎯 **Raycast Targeting**: Upon entering combat, the Hornet Toad’s AI runs a line-trace or sphere-sweep check targeting Witya’s spine joint (`spine_02`). If the raycast confirms a clear line of sight, the toad starts the `Tongue_whip_Start` animation, locking Witya’s chest position at that exact millisecond into a vector variable called `Target_Vector_Lock`.

- 👅 **Spline-IK Tongue Stretching**: The toad's tongue uses a flexible bone chain driven by a 3D Spline-IK solver. During the attack window (exactly 6 frames from mouth open to impact), the bone chain stretches linearly directly toward `Target_Vector_Lock`. The tongue moves at a high speed (minimum 25 m/s) to make the strike feel snappy and razor-sharp.

- 🔄 **Impact Hold & Tongue Retraction**: Upon hitting Witya's collision box (which triggers his stagger animation), the tip bone of the tongue locks its coordinates directly onto Witya for exactly 2 frames. Following this short impact hold, the Spline-IK weights smoothly pull the tongue back, snap-retracting it into the toad's mouth over an 8-frame window.

---

#### **⚙️**VERTICAL TRAVERSAL & LEDGE CLIMBING

- 🧗 **Ledge Grab Detection**: When Witya jumps using `[INPUT_JUMP]` near a platform, the character controller fires a forward-downward raycast from his collarbone area. Upon detecting a platform edge within a 0.5-meter range, the system automatically pauses gravity and snaps Witya's hands directly to the ledge socket (`Socket_Ledge_Grab`).

- 🤸 **Ledge Climb Animation**: The transition from hanging to climbing up (`Ledge_climb_Up`) should show Witya's natural agility. The animation uses a fast 12-frame acceleration window: instead of a slow, heavy pull-up, Witya swings his long legs forward along the pitch axis. His knee joints lift sharply by 45 degrees, placing his bare feet directly onto the upper platform surface.

- 🦊 **Ear & Tail Movement**: Throughout the climb, Witya's 4 dynamic foliage ears relax and bend backward by 15 degrees to prevent them from clipping through the platform edge. At the same time, the 12-segment tail performs a quick downward whip animation over 6 frames to act as a physical stabilizer, helping him absorb the forward inertia as he lands next to the Bolt Crates.

---

#### **⚙️** TECHNICAL & VFX MATERIAL NOTES

- 🌵 **Hornet Toad Sand-Burst Effect**: At the exact frame where the Hornet Toad’s health drops to 0.0, the skeletal mesh instantly hides. In its place, the system spawns a high-density Niagara particle system for a dry sand explosion. Phase 01 triggers a rapid radial shockwave composed of 50 to 60 small sand debris meshes that scatter outward using a random speed modifier.

- 🎨 **Texture Color Synchronization**: The spawned sand dust and cloud particles cannot use generic brown colors. The material for the VFX must dynamically copy the exact sandy-yellow texture colors from the destroyed toad's skin. This ensures the explosion looks like the physical enemy is turning back into natural desert sand, making the visual feedback feel unified and satisfying.

- 🧹 **Memory Optimization & Particle Cleanup**: To maintain a stable frame-rate during fast platforming or speedruns, the sand dust particles disappear quickly. The particles have a maximum lifetime of 0.8 seconds after spawning, using a fast linear opacity fade to 0.0 before completely clearing their colliders and meshes from the streaming memory.

---

### **📺** MISSION TUTORIAL: THE GORGE JUNCTION & GADGET SANDBOX

- 🧱 **The Destructible Wall

**Level Geometry**: At the end of the canyon, the path splits into two directions.

**The Left Route**: This branch leads to a static rock wall with a unique, high-contrast cracked texture. As soon as Witya enters the 3-meter trigger zone of this wall, his dialogue plays:

**Witya:** Maybe my Homemade Grenades can handle something like this?  
**Gismotron Assistant (Subtitle UI Layer Overlay):** Searching for military license...  
**Witya:** This is a firework.  
**Gismotron Assistant:** Then everything is fine. Input [INPUT_WEAPON_SWITCH] to change your weapon.

---

- 💥 **The Landscaping Penalty Conditional Trigger**

**Breakable Wall Mechanics**: When the player throws a Homemade Grenade at the cracked rock wall, the projectile impact starts a fracturing script. The wall instantly collapses into independent debris.

**System Currency Logic Override**: the system fires a currency deduction event (`Bolts = Bolts - 50`) and triggers the sub-routine subtitle text:

**Gismotron Assistant (Subtitle UI Layer Overlay):** 50-bolt fine for unauthorized landscape design.

And these bolts will indeed be deducted from the shared wallet. In future, such walls will appear in the middle of levels, and Witya will receive penalties for destroying them.

**Space on the other side**: Behind the wall is a small cave containing a small group of Cave Crabs and a Hophytum vein. If the player previously missed the jump from the bridge, the voice guidance about Hofitum will sound here.

---

#### **⚙️** PROJECTILE PHYSICS & GRENADE DETONATION NOTES

- 🚀 **Weapon Equip & Parabolic Launch**: When the player selects the homemade grenade, the system instantly attaches the projectile mesh to Witya’s hand, keeping it visible. Pressing `[INPUT_FIRE]` triggers a full-arm throw animation: Witya executes a swinging motion, releasing the grenade at the peak of the arc. The projectile receives an immediate forward-upward impulse, calculating a real-time parabolic curve based on the current camera pitch angle. The animation uses a low mass parameter to ensure a snappy, high-altitude throw.

- 💥 **Collision Detonation & Blast Radius**: The grenade model uses continuous sphere collision tracking. Upon hitting any static environment layer or the fractured rock wall, the movement logic instantly stops and calls the `Explode_Sequence` function. The blast runs a sphere-sweep trace with a strict 3-meter radius, applying a heavy kinetic knockback to any enemies caught inside.

- 🎆 **Firework VFX & Wall Destruction**: To match Witya's dialogue ("This is a firework"), the detonation bypasses military plasma explosion effects. Instead, the Niagara system spawns an asymmetric burst of chaotic, multi-colored magnesium sparks and thick black smoke. At the exact frame of impact, the explosion logic passes a high-priority damage value directly to the rock wall's destructible system, causing the stones to break apart into independent physical chunks.

---

#### **⚙️** MATERIAL SHADER & WALL FRACTURE PROPERTIES

- 🗺️ **Proximity-Based Crack Deepening**: The breakable section of the rock wall uses a texture channel as a structural fracture mask. When Witya enters a 3-meter radius, the material dynamically increases the depth of the Normal Map along the mask by 2.5x. This makes the cracks look physically deeper and cast sharp shadows, signaling to the player that this rock wall is unstable.

- ⏳ **Trickling Sand Particle Effect**: To emphasize that the wall is ready to collapse, the material triggers a particle effect along the crack coordinates. The system procedurally emits a low-density, continuous trickling stream of fine sand and tiny debris. This subtle visual effect guides the player’s attention to the destructible zone without needing generic UI markers.

- 💥 **Debris Material Synchronization**: At the exact frame of the grenade explosion, the wall material swaps its state. The static wall texture instantly transfers its lighting, shadow, and color data directly onto the independent Chaos Physics chunks within a single frame. This quick sync guarantees that the flying stone fragments match the shading and texture alignment of the original wall.

---

#### **⚙️** UI/UX CANVAS & BOLT DEDUCTION NOTES

- 🖥️ **Fine Notification Banner**: When the system deducts 50 bolts for a fine, the UI manager must instantly slide the main Bolt counter onto the screen, even if it was hidden. Directly beneath the counter, a dedicated red notification element (`w_Fine_Notice`) spawns with a sharp 5-frame pop animation, displaying the flashing text: `"[!] OUTLAWED LANDSCAPING FINE: -50 BOLTS"`.

- 📉 **Negative Number Scrolling & Color Flash**: The text counter on the main Bolt widget must not snap instantly to the new value. The numbers must rapidly scroll downward over exactly 30 frames. Simultaneously, the main text color changes from its default white to a flashing crimson to clearly warn the player of the bolt loss.

- 🔩 **Animated Bolt Vibration & HUD Hide**: To make the fine feel impactful, the 2D mechanical nut icon on the HUD vibrates rapidly along its local X-axis (using a high-frequency shake effect) during the entire deduction phase. Once the counter reaches the final value and the 3.0-second inactivity delay expires, the `w_Fine_Notice` panel slides downward and fades away completely.

---

### 🗺THE SEVEN-TOAD ROADBLOCK

- 🐸 **The Multi-Target Combat Encounter**

**The Right Route**: This pathway serves as the primary for Act I. The path is locked via 7 Hornet Toads simultaneously.

**System Dialogue Safeguard**: If the player chooses to bypass the left destructible wall sector and goes directly toward the toad roadblock, the homemade grenade weapon-switch dialogue is forced to play at this alternative trigger zone.

---
### 📥 THE CIVILIAN BOUNDARY

- 🔏 **The Squeeze Interaction for Map Streaming**

**Level Geometry**: The gorge corridor ends at a low perimeter wall featuring a narrow vertical gap. Positioned to the left of this wall is a static, elevated platform.

**Gismotron Assistant:** Input [INPUT_SQUEEZE] to squeeze through the structural gap.  
**Witya:** Hey, I could easily just jump over this!  
**Gismotron Assistant:** I require minor timing to load the map.

**Structural Gap Proximity Check**: If the player moves Witya directly into the gap, instead of using the ledge platform, the interaction is blocked, and Witya delivers his defensive voice-over line:

**Witya:** I don't plan on getting stuck here.

**Level Connectivity Result**: The only valid path requires the player to jump onto the left platform, use the height difference to leap over the perimeter wall, and enter the active Civilian Sector.

---

### **📥** CIVILIAN SECTOR

- ☀️ **Atmosphere of the location and sunlight**

**Level Geometry**: The Civilian Sector consists of approximately twenty low, single or two-story residential buildings. The roofs feature a concave dome shape, built specifically to serve as rainwater collection basins.

**Environment**: The streets are completely empty of NPC due to the star's zenith. Upon crossing the perimeter, Witya triggers his voice-over line:

**Witya:** Yeah, the star's zenith isn't exactly the best time to be out on the street.

**Level Loot Distribution**: Bolt  scattered randomly between the houses. Several Crates are hidden in backyard sectors, while others stand directly in open sight-lines.

---
#### 📺BORIS AND BOLT GYRATE

- 🚪 **The Inbound Trigger**

**Cinematic Trigger Event**: As Witya approaches the residential house positioned directly opposite the Bolt Gyrate, the front door opens. A short (1.4-meter height), sandy-brown NPC named Boris Hartocat—featuring an integrated mechanical arm prosthesis—sprints out onto the street.

**Witya:** Boris, let me guess, running late for training again? How's the prosthesis?  
**Boris:** Of course I am! And the prosthesis... Oil got all stagnant inside dispenser again. And as for that Bolt Gyrate you installed—I couldn't find a matching wrench anywhere. Its massive!  
**Witya:** Right, sorry about that. I don't have time to fix this now, but I'll definitely do it later.

---

#### 📐 THE ANTI-HEXAGON PROTOCOL

- ⚙️ **Triangle Bolt-Head Design**: All mechanical bolts used in the Bolt Gyrate mechanisms must have a strict three-sided triangle head profile, avoiding standard hexagonal shapes. Hexagonal designs are banned from domestic levels and are locked exclusively as a visual marker for Nether to visually show its absolute hostility to the Living World.

---

- 🔀 **Tutorial Branching Trigger**: The game checks the player's progression history. IF the player bypassed the cavern under the broken bridge earlier, the Gismotron assistant must trigger the Bolt Gyrate mechanics tutorial right here.

---

#### ⚙️ SYSTEM MECHANICS: THE LUBRICATION SLOT INTERACTION

- - 🔧 **Prosthesis Maintenance**: As soon as Witya finishes turning the Bolt Gyrate mechanism, Boris moves toward a wall-mounted metal slot. He inserts his mechanical arm prosthesis directly into the lubrication machine to grease the joints.

- 🧴 **Visual Feedback & Oil Material**: Boris pulls his arm out of the slot, now covered in a glossy, reflective oil material layer. He plays a quick shake animation to fling off any excess fluid drops.

- **Boris**: Excellent. Works like I put it yesterday.
- **Witya**: Seriously though, where do you run off for combat training so often anyway?
- **Boris**: Oh, that's a total secret!

- 🏃 **Character Exit**: Right after the dialogue, Boris switches to a high-speed sprint, runs past the level exit boundary, and his model disappears from the screen.

---

#### **⚙️** DYNAMIC OIL SHADER & LIQUID GLOSS PROPERTIES

- 🧴 **Oil Layer Roughness & Specular Settings**: The oil effect blends as a secondary material layer over Boris's robotic arm textures. At the exact frame he pulls his arm from the slot, the material switches parameters over 10 frames: clamping Roughness to a minimum of 0.02 and forcing Specular to 0.95 to simulate a fresh, wet liquid coating.

- 🌈 **Oil Sheen & Fresnel Highlights**: To show the thickness of heavy industrial machine oil, the shader applies a sharp Fresnel curve (edge exponent set to 4.5). This setup creates a rich, glossy rainbow sheen and iridescent amber edge reflections when ambient lighting or direct sunlight hits the surface, making the oil look realistically viscous.

- 💧 **Animated Oil Drops & Shake Fade**: To match Boris's hand-shake animation, the shader uses a dynamic downward-moving texture mask along the gravity axis, simulating oil droplets sliding along the metal plates. When the shake animation plays, the global oil thickness layer fades linearly by 40% over 30 frames, leaving behind a clean, uniform protective gloss coat.

---

#### **🗃️** CHARACTER LOG: BORIS HARTOCAT

- 🗣️ **Name Origin & Voice Modulator**: The character is named Boris Hartocat in English (a phonetic blend of "Hard to catch / Hard to hit"), localized as Борис Хрипо́йма in Russian. For his voice, the audio engine applies a low-frequency, gravelly modulator ("хрипота") to all his dialogue lines. This acoustic trait acts as a narrative pun on his Russian name and a personality detail.

- 🎚️ **Granular Voice Distortion**: To create Boris's signature scratchy throat texture, his dialogue audio tracks pass through a real-time distortion filter. The audio system isolates the lower-mid frequencies (between 150 Hz and 400 Hz) and adds a randomized pitch-jitter modifier. This fragments smooth vocal waves into micro-pulses, generating a dry, gravelly friction sound directly in-game.

- 🤖 **Metallic Resonance & Formant Shift**: To blend Boris’s orange-skinned alien biology with his cybernetic arm prosthesis, his voice uses a subtle synthetic undertone. The audio logic applies a negative formant shift (-1.5 semitones) paired with a light Ring Modulator effect (set to 45 Hz). This creates a mechanical resonance that naturally clips when Boris panics or gets excited.

- 📻 **Low-Fi Crystalline Breathing**: The end of each dialogue track automatically triggers a short breathing sound effect. To match the natural weariness of his voice, these audio use a dry, low-tier 8-bit / 11 kHz restriction profile. This unique acoustic friction texture signals to the player that Boris’s organic vocal cords are worn out.

---

### 📺 MISSION CINEMATIC: THE SPY LOG STATE (THE CIVILIAN BOUNDARY)

- 📡 **The Forced Broadcast Override:**  
    **System Forced Dialogue**: After Witya's dialorue with Boris, the Gismotron helper module executes a voice-line. This specific line triggers automatically, completely bypassing the player's initial menu settings choice (`Gismotron = Disabled`).

**Gismotron Assistant:** Boris Hartocat located. Transmitting tracking coordinates directly to the Tonata Rangers.  
**Witya:** Oh, no. Seriously? That sweet guy is a criminal?

---

#### 📥 APPENDIX: CIVILIAN SECTOR RECOVERY & ST-07 VENDING LOGIC (ACT I)

- 🏪 **The Global Resource Economy Constraints:**  
    **System Distribution Rule**: The game completely ban traditional Health Crates or dropped medkits. Ammunition units drop exclusively as loot items upon destroying mechanical or humanoid enemies (e.g., Warbots or Grables). Player health replenishment is restricted strictly to interactions with static vendor terminals.

- 🛠 **Vending Terminal Mesh Topology (SM_Terminal_ST07)**  
    The terminal features a distinct trapezoidal body shape with angled bevels mounted on a short structural support pillar. The vertical height clamps precisely at Witya’s chest level (approx. 1.1 meters along the Z-axis), adhering to the rectangular design style.

---

### **🔊** TRIGGER & CONTEXTUAL TUTORIAL

- 🎯 **The First-Contact Interaction Check:**  
    **Box Trigger**: Placed around the terminal model is an invisible 3.5-meter radius zone. When Witya’s enters this zone boundary, the Gismotron Assistant launches a voice-line:

**Gismotron Assistant:** A vendor terminal, model ST07, has been detected nearby. Interaction is highly recommended.

**System Repeat:** If `ST07_First_Contact` is FALSE, the system sets the Gismotron Assistant to repeat this audio line whenever Witya enters the trigger zone, until the player completes his first interaction.

- 🗣 **The Assistant Instructional Commentary:**  
    Concurrently with the shop screen fade-in animation, the Gismotron Assistant plays an  voice track to instruct the player on store mechanics:

**Gismotron Assistant:** The available items list is displayed on the left panel, with a dynamic preview on the right. At this point in the game, your clearance level allows only the purchase of Versagel—a specialized quantum bio-gel formulated to regenerate organic tissue lacerations and repair armor plates with maximum structural efficiency. To complete a purchase, move the cursor over the item row and select confirmation.

---

#### **⚙️** UI/UX VENDOR CANVAS HIERARCHY & SCREEN LAYOUT

- 🖥️ **Full-Screen Viewport Blur Anchor:** Upon registering a successful player interaction input event with the terminal, the UI manager displays the `W_Terminal_Shop_Canvas` container widget directly on the screen overlay layer. Gaussian Blur filter (intensity set to 4.5) smoothly softens the active level scene beneath to focus 100% of the player's attention directly onto the store interface.

- 📦 **Three-Panel Asymmetric Screen Layout:** The screen canvas layout enforces a rigid three-zone horizontal partition split by solid 3-pixel-wide amber line:
    - **The Left Shop List (20% Screen Width Scale):** Dedicated exclusively to the `Vertical_Item_Scroll_Box`. This widget renders the purchase row cards. At the start stage, only one line is available: Replenish Health / Versagel Acquisition.
    - 📺 **The Center Display Window (60% Screen Width)**: A large central area using a `UI_Render_Target` viewport. This section dynamically displays content based on the highlighted item. There is no empty state: upon opening the menu, the Versagel health restoration option (and later, health + ammo refill) is selected by default.
	    - **Versagel Default State**: Since Versagel is a utility quantum gel coating for healing, it does not feature an animated commercial. When highlighted, the window simply displays its static item icon.
	    - **Weapon Advertisements**: When you move the cursor over the card of any available weapon, the gel icon disappears, and instead a 3D advertisement for that item starts in the window.
    - **The Right Weapon Inventory (20% Screen Width Scale):** Reserved for displaying Witya's currently owned weapons. For this initial tutorial phase, this entire column is permanently locked.

🎯 **Cursor Focus & Purchase Execution**: The item cards inside the menu module use an interactive state tracker. Moving the cursor over an item triggers an OnHover event: the card background shifts from a dull charcoal shade to an active neon-cyan glow, while triggering an instruction voice line from the Gismotron Assistant. Pressing the confirm key completes the purchase, firing a quick 5-frame flash animation, deducting bolts, and restoring Witya's health HUD variable back to 100%.

---

#### **⚙️** TERMINAL INTERACTION SYNC & IK WARP PROPERTIES

- - 🧱 **Terminal Alignment & Snap**: When the player presses `[INPUT_INTERACT]` within the terminal's 1-meter radius, the character controller temporarily blocks movement controls. The system runs a quick 8-frame alignment, snapping Witya's base position straight to a fixed point in front of the console to face the screen directly.

- 🦊 **Idle Search Animation**: While the store interface is open, Viti's model switches to a smooth idle background animation (`Terminal_Idle_Search`). His four dynamic leafy ears twitch randomly and alternately, while his chain of 12 tail bones lazily sweeps the floor. This makes the character appear alive and organic while the player rummages through their inventory.

---

### **📥** THE CRASHED SITE LAYOUT

- 🧱 **The Visual Pre-vis Environmental Anchor**

**Level Geometry Architecture**: Right above the starship crash site—which is close to the Civilian Sector border—there are two LCVP-84 Hovercrafts locked in a hover state.

**Combat Arena Transition**: When Witya enters the crash site area, combat starts. Two Warbot Wrenchman enemies are waiting right in the middle of the wreckage.

---
### 🤖 COMPACT COMPANION (KATYA INITIAL STATE)

- ⚙️ **Dormant Mesh Rigid**: One of the Warbot Wrenchman enemies is holding a tiny, deactivated robot folded up. Its legs are fully pulled inside the body shell, and its arms are folded flat against its sides. In this state, the model looks exactly like a "toaster with a head."
- 📐 **Volumetric Proportions**: The head model is stylized and made intentionally large, taking up exactly one-third (1:3 ratio) of the robot's total body size.
- 🔧 **Component Layout Map**: There are 3 screws located almost at the neck. Right below them is a small static screen with 4 interactive buttons (two on the left and two on the right). The hand has 3 fingers.

**Witya**: Quand's Warbots? Hey, put him back!

---

### **⚔️**COMBAT ENGAGEMENT: THE DROPSHIP INBOUND TUTORIAL

- **The Fixed Wave**

**Combat Group Initialization**: The two Warbot Wrenchman enemies leave their idle state and start tracking Witya. At the same time, the hovering transport ships fly down, lowering their position to drop a second wave of enemies.

**Tutorial Wave Constraints**: In this Act I tutorial, the enemy wave size is strictly limited: 2 Warbot Wrenchmans and 5 Sharpballs.

**Enemy Balance (Sharpball)**: Light bio-mechanical swarm enemies. Their health is set so they die from exactly 1 hit by a VersaWrench strike or a blaster shot.

**Enemy Balance (Warbot Wrenchman)**: Medium armored infantry enemies. Their exact health pool and defense stats are managed entirely through the main balancing spreadsheet for reuse in later missions.

**Cinematic Resolution Trigger**: The exact moment the last enemy dies, player controls are locked, and the main Act I story cutscene starts.

---

#### 👑 MASTER GLOBAL LORE PROFILE: SECONDARY ANTAGONIST

- 🗃️ **Lucino Quand (Лучино Кванд)** — The main corporate mafia boss. The character design combines the style of classic organized crime syndicates (inspired by Lucky Luciano) with the absolute monopoly power of old industrial dynasties (inspired by the Quandt family). All robots deployed under his corporate logo are officially called Lucin Warbots.

---

#### **⚙️** LVCP DESCENT & ENTITY DEPLOYMENT PHYSICS

- 🚢 **LVCP Spline-Driven Vertical Descent**: When the deployment event triggers, the two hovering transport ships stop drifting and start their descent. The ships fly straight down along a vertical path, braking hard as they reach a height of 4 meters above the ground. The engine glow material must get 40% brighter to visually show the heavy braking effect.

- 🔓 **Pneumatic Shutter Release & Physics-Driven Drop**: Right as the dropship stops braking, the bottom hangar doors must open quickly with a 10-frame pneumatic animation. The enemies (2 Warbot Wrenchmen and 5 Sharpballs) must instantly detach from the ship, turn on their normal gravity physics, and drop straight down to the ground with a hard-coded downward starting speed.

- 💥 **Substrate Collision Shockwave & NavMesh Snap**: The moment the falling robots hit the floor, they must trigger a heavy dust particle effect and a low-frequency screen shake to show off their heavy metallic weight. The robots must instantly stop their falling state, switch to their combat animations, and register their collision on the dynamic navigation grid (NavMesh) to immediately start chasing Witya.

---

#### **⚙️** SWARM BEHAVIOR & SHARPBALL MOVEMENT PHYSICS

- 🔮 **Boids-Based Swarm Cohesion & Dispersion**: The 5 Sharpball enemies use a simple flocking AI to move together. The game constantly checks three things: Separation (keeping the balls from clipping into each other), Alignment (making them move in the same direction toward Witya), and Cohesion (keeping them grouped up as one tight pack until a VersaWrench hit breaks their formation).

- 🌀 **High-Velocity Kinetic Rolling & Surface Conformance**: The Sharpball needs a continuous rolling animation that automatically snaps to the floor in real-time using a raycast. The sphere collider must check the ground angle on every frame. This lets the enemies smoothly roll up steps, go over rocky debris, and drop off ledges without losing speed or clipping into the walls.

- 💥 **Fragile Collision Destructible & One-Hit-Kill Trigger**: Sharpball health is strictly locked to 1.0, meaning they die instantly from any valid hit by Witya's melee swing or blaster shots. Upon death, the ball model is replaced with a shattered one in just one frame, and quick sparks and small metal debris fly in all directions.

---

## **🎥**  CINEMATIC INTERACTION: THE ROBOTIC RECOVERY SEQUENCE

- 🤖 **The Actor Pick-Up Event**: Right after the wave is destroyed, a script triggers an automatic in-game cutscene. Witya picks up the robot, dusts it off, and inspects it. The exterior appears relatively intact. Witya takes it with him and exits the frame.

- 🎬 **The Transitional Match-Cut**: The scene hard-cuts to a new location, seamlessly moving the player inside Witya’s concrete apartment room. The room's look, lighting, and cheap furniture must match the design from the "Existential Crisis Scene" after the `Sneak in Acatadop` mission.

- ⚙️ **The Environmental Trigger (The Self-Built Exhauster)**: Witya enters the frame holding Kit and places her right in the middle of his workbench. He reaches out to turn on a homemade exhaust fan — a crude, mismatched fan model attached by hand over an open vent hole in the concrete block wall.

- 💥 **The Kinetic Strike**: The fan doesn't respond at first. Witya suddenly turns 180 degrees, turning his back on it, and kicks the wall next to the fan. The kick starts the fan, causing the blades to spin and accelerate the air flow.

- 🔧 **The Maintenance & Disassembly**: Witya takes a screwdriver from the table. The camera zooms in on the top panel of the Kit's body. Vitya begins to unscrew the first of the three top screws.

---
## **🎥** The Match-Cut Day/Night Interpolation

**Cinematic Hard-Cut:** The scene cuts instantly to a new frame, changing the room's lighting from bright midday sun straight to late-night moonlight.

**The Composition Match**: Witya's position, his body angle, and his arm movements stay perfectly identical across the cut. He is doing the exact same screwing motion, but now he is tightening the screw on **Katya's** neck.

**The Narrative Prop Spawn**: Right next to Witya on the right side of the workbench, a new rectangular device - **P.A.R.I.S.**

---

### **💬** DIALOGUE: SYSTEM INITIALIZATION

- ⚙️ **The Activation Wake-Up Sequence**

**Visual Sequence**: Witya presses the power button on Kit's panel. The dark eyes turns on, showing an active, glowing animation.

**Katya**: What? Where am I?  
**Witya**: Welcome to my workshop. You had a pretty rough landing.  
**Katya**: Yes, I remember that.  
**Witya**: How did you draw so much attention from Quand's Warbots?  
**Katya** (tilting her head up to look at him): I infiltrated the Quand Industries factory; I needed the **P.A.R.I.S.**  
**Witya** (staring directly into **Katya's** screen): **P.A.R.I.S.**? How did you even fly such a distance from Walthm? And... what a coincidence, I happen to critically need that exact system to boot up my ship.  
**Katya**: I need it just as much. I must reach Ceroscan immediately to broadcast the Quand factory plans to the Tonata Rangers.  
**Witya** (dropping his screwdriver onto the table): Hey... Serious? You won't believe this, but I need to reach exact destination.  
**Katya**: And what is your motivation?  
**Witya**: I want to become a hero and... finally abandon this godforsaken Meltin.
**Kit:** Since we are navigating the same coordinates, maybe could you install P.A.R.I.S into... me?
**Witya:** Fine. If the starship fractures in mid-flight, finding another module will be a nightmare. But I’ll have to switch you off .

**System Execution Sequence**: Katya nods, then switches off. Witya takes out the screwdriver again and starts disassembling.

---

#### 🔊 AUDIO DESIGN & DYNAMIC KINETIC SFX PROPERTIES

- 💥 **Wall Impact Sound Layering**: At the exact frame where Witya's foot hits the wall geometry, the audio engine fires a high-priority SFX event. The sound combines a deep, low-frequency sub-bass thud (clamped at 60 Hz to simulate heavy wall mass vibration) with a sharp, resonant metallic clatter to clearly signal that the workshop is built from hollow, scavenged metal plates.

- ⚡ **Stalled Motor Hum & Relay Snap**: Before the impact, the stuck ventilation system emits a very quiet, high-frequency electric hum (at 800 Hz) to show that the motor is under voltage but jammed. Exactly on the millisecond of the kick, this hum cuts out, instantly replaced by a loud, dirty mechanical relay click and a metallic friction scratch sound.

- ⚙️ **Stuttering Fan Startup Audio**: Right after the mechanical relay snap, the fan blades start their rotation audio loops. The sound bypasses smooth acceleration: the audio loop stutters through uneven, choppy spin cycles over 45 frames (simulating rust and broken ball bearings) before blending into a stable, muffled air-suction hum mixed with a low rattle.

---

#### **⚙️** TOOL INTERACTION & SKELETAL RIGGING

- 🔧 **Two-Handed Tool Attachment**: When the repair scene starts, Witya's hands lock to their targets. The left hand holds Katya's side head plate flat to keep her steady. The right hand snaps tightly to the screwdriver handle (`Socket_Tool_R`), while the screwdriver tip locks straight into the center of the screw.

- 🔄 **Natural Hand-Screwing Animation**: The screwing animation loop must look natural, not robotic. The right wrist and elbow execute an uneven, repeating movement over 24 frames: a fast 120-degree twist (the actual tightening), followed by a quick 2-frame pause (Hit-Stop logic to show pressure), and a smooth 6-frame reset back to the starting wrist position. Witya's shoulder bones bounce slightly with each twist to show physical effort.

- 👀 **Concentrated Gaze & Ear Movement**: To show Witya's intense focus, his eyes and pupils look strictly at the tip of the screwdriver, ignoring general camera movement. At the same time, his 4 plant ears shift position: the top pair tilts forward by 10 degrees to show concentration, while the bottom pair stays fully relaxed, moving naturally with his head.

---

#### **⚙️** MATERIAL SHADER & TEXTURE SCREEN PROPERTIES

- 🖥️ **Abdominal Screen Allocation**: The screen model is located strictly on **Katya's** stomach area ("на пузике"), right between the 4 interactive buttons. The model uses separate material IDs: the outer frame uses a grey anodized aluminum texture, while the screen itself uses a glowing, slightly translucent blue glass shader.

---

#### **⚙️** ROBOTIC JAW ANIMATION & EYE LENS RIG NOTES

- 🔩 **Jaw Plate Movement & Lip-Sync**: Katya's lower face features a flat steel plate that acts as a physical jaw (`Mandible_Plate`). During dialogues, the lip-sync system moves this bone strictly up and down. To emphasize her clunky, mechanical nature, the animation skips smooth blending. Instead, it uses a simple 3-step choppy keyframe layout that snaps the jaw open and shut along with the dialogue volume spikes.

- 👁️ **Eye Lens Zoom & Iris Adjustments**: Her eye sockets contain two detailed camera lens models. To show different emotions like skepticism or surprise, the setup uses a simple shape key (morph target) to open and close the camera iris. When Katya makes a sarcastic remark or questions Witya's ideas, the iris contracts by 40% over 6 frames, simulating a squinting, skeptical glare using just the lens geometry.

- 🦊 **Head Tilts & Alert States**: While Katya speaks or reacts, her head bone tilts naturally. Normal or friendly dialogue lines trigger a quick 5-degree side tilt. If something alerts her, the eye lenses instantly open wide, and the jaw plate locks tight against her neck collar to protect her internal mechanics.

---

### **🌅** EARLY MORNING TURN ON

- 💼 **The Organ installation**

**Cinematic Transition Cut**: The frame updates to show early morning. Witya turns on Kit.

**Witya:** Congratulations for obtaining a new organ. Next up, I recommend a liver.
**Robot (Optical lens zoom adjust):** For what would I need an organic liver?
**Witya:** You'll find out when you became adult. By the way, do you have name? Or you have just a serial code?
**Kit:** I do. Kit.
**Witya:** Kit? Sorry, but that is not a name. Look, I have a kit of instruments on the table, a kit of components under the table. 
**Kit:** Yes. I am also a kit. Of parameters.
**Witya:** Oh... How about... I call you **Katya**?
**Katya:** Acceptable. I... do not display high resistance. By the way, what is your identity string?
**Witya:** Unsure. Everyone here calls me Mechanic.
**Katya:** But that is also not a name...
**Witya:** I don’t have a name.
**Katya:** How?
**Witya:** I’m "lucky" to not have parents.
**Katya:** But, if your biology initialized, it implies...
**Witya (Executing a heavy adolescent yawn animation while stretching his arm):** I am born of **Power**!
**Katya:** You are quite Witty.
**Witya**: Please study my starship controls. As for me—I want to sleep. I've been working with you all night. Oh, and remind me later to weld a **magnetic klemma** onto my suit spine, so I can carry you.
**Katya:** Why do you need to carry me?
**Vitya:** You wanna to be stolen?

**Cinematic Exit Phase**: Witya walks over to his bed. He drops his head straight onto a fluffy pillow model (using a long-fur shader), without taking off his pants and suit.

**Witya** (whispering quietly): Is it real... Is this finally my absolute last night on this wretched **Meltin**?

---

#### **⚙️** SKELETAL ATTACHMENT & BACK HARNESS ANIMATION LOGIC

- 🎒 **Back Harness Socket Settings**: Witya's upper body model features a specific attachment point called `Socket_Back_Harness`, placed in the center of his back. The socket configuration tilts Katya's model backward by 5 degrees. This setup ensures her bottom thrusters stay clear of Witya's waist, preventing any mesh clipping during high-speed movements.

- 🤖 **Character Attachment & Folded State**: When Witya puts Katya on his back, her character controller turns off, and her model anchors directly to `Socket_Back_Harness`. Katya's animation graph instantly switches to a dedicated state (`Katya_Back_Idle`), forcing her arms and legs to fold back into a compact "toaster" shape while she rides along with Witya.

- ⚖️ **Secondary Inertial Sway & Weight Simulation**: To prevent Katya from looking like a rigid, frozen block on his back, the socket logic applies a subtle physical sway. The system tracks Witya's speed and changes in direction (like jumps or quick `Dodge_Side_Jump` dodges), adding a small spring lag (clamped between -3 and +3 degrees). This simulates the physical weight of a heavy metal companion bouncing naturally on a flexible mount.

---

#### **⚙️** MATERIAL PROPERTIES & LONG-FUR PILLOW SHADER

- 🛏️ **Layered Fur Shell Rendering**: The pillow model uses a layered shell technique made of exactly 16 alpha-blended mesh layers. Each layer shifts slightly outward up to a total distance of 20 mm. This setup creates a dense, fluffy, long-fur look without breaking the game's polycount budget.

- 🌀 **Noise-Driven Fur Clumping & Thinning**: To prevent the fur from looking like stiff needles, the material uses a 3D noise texture modifier. This noise function bends and clumps individual fur strands realistically. The strands must get thinner toward the tips, scaling down to 0 at the outermost layer so they look soft and move naturally when Witya's head touches the pillow.

- 💡 **Sub-Surface Scattering & Root Shadows**: The fur material uses sub-surface scattering (SSS) tuned for soft fabric fibers. The morning light coming through the workshop window must pass slightly through the outer edges of the fur. At the same time, the material uses a micro-shadow map to darken the roots by 60%, adding deep contrast to the pillow during close-up camera shots.

---

#### 🧲 ATTACHMENT CINEMATICS & BACK HARNESS LOCK

- - 🧲 **Automatic Ledge Pull & Snap**: When the player gives the command or a cutscene starts the attachment sequence, the engine stops Katya's independent movement. Her model executes a fast 8-frame slide (Lerp) straight toward Witya's `Socket_Back_Harness`. To make the docking feel punchy, the movement speed accelerates sharply during the last 2 frames, simulating a strong magnetic pull.

- 🤖 **Compact Fold Animation over 12 Frames**: Right while sliding toward his back, Katya's model runs the `Katya_Fold_To_Back` animation. Over exactly 12 frames, her lower legs pull inside her bottom chassis slots, and her 3-fingered hands snap flat against her side plates. Her mechanical jaw plate locks tight into the neck ring, fully switching her to a compact folded state right before she hits the mount plate.

- 💥 **Harness Clamping Hit-Stop & Weight Reaction**: At the exact frame her model hits the socket, the game triggers a quick 1-frame Hit-Stop pause on both characters to show physical impact. Witya's upper back and shoulders jerk backward by 4 degrees to visually show the heavy weight of the metal robot. At the same time, a bright blue light ring flashes around his chest and back socket to confirm she is locked in.

---

#### **⚙️** AUDIO DESIGN & MAGNETIC INTERLOCK SFX PROPERTIES

- - 🔊 **Mechanical Folding Sound**: While Katya spends 12 frames folding into her compact form, the audio engine plays a clean, high-frequency mechanical whir. This sound blends a sharp hydraulic hiss with a rising pitch (going from 1 kHz up to 1.5 kHz) to clearly show that her limbs and jaw are locking tight into her protective body slots.

- 📈 **Magnetic Pull Bass Sweep**: To back up the sudden speed-up in the last 2 frames before impact, the audio system plays a quick sub-bass hum. This sound mimics a high-power capacitor charging up, building a short but intense volume buildup that peaks exactly on the impact frame, signaling a powerful magnetic attraction.

- 💥 **Heavy Metallic Latch Snap**: At the exact frame of the impact, the previous sounds cut off instantly. They are replaced by a loud, heavy metallic latch snap (tuned to a deep 200 Hz for a massive weight feel) and a high-frequency electronic confirmation tone. This audio feedback matches the blue light ring flashing across Witya's **Chest Cartridge**.

---

#### **⚙️** RUNNING WEIGHT OFFSETS & BALANCE ANIMATION LOGIC

- 🏃 **Forward Spine Lean under Weight**: When the `Katya_Docked` variable switches to True, Witya's animation system must instantly apply a dynamic blend offset. To compensate for the heavy metal weight on his shoulder blades, his spine joints (`Spine_01` to `Spine_03`) must lean forward by exactly 6 degrees during the default run (`Run_Forward_Harness`). This shifts his center of mass forward so he doesn't look like he is unnaturally tilting backward under the load.

- 🦊 **Tail Balancing during Sharp Turns**: His 12-segment tail skeleton must adjust its physics behavior to act as a real counterweight. During sharp 9-degree turns at high speed, the tail must swing toward the outside edge of the turn with extra amplitude (+15% force along the side axis). This balancing movement keeps Witya from looking off-balance and emphasizes the heavy weight of the robot on his back.

- 👣 **Heavy Footstep Impact & Ear Movement**: The footstep animation keyframes (`Walk_Heel_strike_L/R`) must adjust their blending weights. Witya's knees must bend 5% deeper every time his feet touch the floor to visually absorb the heavy impact of the attached robot. At the same time, his 4 plant ears must fold tightly back flat against his head to stay out of the camera's way during continuous sprints.

---

#### **🗃️**LINGUISTIC ALIGNMENT & DIALOGUE: KATYA'S ROBOTICISMS

- 💬 **Syntax Compression & Article Omission**: To show her robotic nature in Act I, **Katya's** text script should bypass standard English articles (_a / the_) where possible. For example, she says "_do you have name?_" instead of "_a name_". This rule shows her system is running a memory-saving protocol for her speech module.

- 🏫 **Corporate Vocabulary Filters**: When talking about poor or messy places, **Katya's** system automatically switches out cheap slang words (like _slums_ or _junkyard_). Her database replaces them with corporate or military terms, making her say something like "_industrial zone sector_". This creates a funny contrast between her dry, high-tech words and Witya's messy garage reality.

---

### **📺** MISSION NAVIGATION & MAP OVERLAY (THE COCKPIT VIEW)

- 💺 **The First-Person Interface Transition**

**Visual Sequence**: Witya places Katya onto the passenger seat to his right and sits in the pilot seat on the left. The camera cuts instantly to a strict first-person view (`FP_Cockpit_View`).

**Kinematic Canopy Closure**: The starship cockpit canopy slides shut and locks. The interior lights dim to complete darkness, and an integrated holographic projector turns on, spawning a 3D Galaxy Map overlay in front of the player.

- 🌐 **Choosing a destination**

**System Interface Mapping**: The Galaxy Map displays exactly two sectors and one mission info block.

- **Node 01: Planet Ceroscan (Кероскан)**

**Hover Intersection Action**: Hovering the cursor over this planet triggers the main mission UI prompt: "Participate in the Rangers Games" («Участвуй в Играх Рейнджеров»).

- - **Node 02: Planet Del-Alformar (Дель-Альфомар)**

**Hover Intersection Action**: Hovering the cursor over this alternative planet triggers a hidden, joke subtitle box: "How about you forget all this and just relax?" («А может забьёшь на это и просто расслабишься?»).

**Interaction Intercept**: If the player inputs a `CLICK_SELECT` action on the Del-Alformar, the system blocks the hyperdrive jump and triggers an immediate dialogue:

**Witya**: I'm afraid the bolts scraped from toads won't even cover a basic massage. Hey, Kate, get out of there—it's not like you need to go to Alformar either.
**Katya**: I am studying humor. Did I succeed?

**System Warp Execution**: When the player selects Ceroscan, the camera flies out of the cockpit. The starship fires its thruster particles, shoots straight up at high speed, and flies out of the screen.

---

#### **⚙️** FIRST-PERSON HOLOGRAPHIC GALAXY MAP INTERFACE

- 🎥 **First-Person View & Cockpit Dimming**: When the camera switches to `FP_Cockpit_View`, the engine automatically dims the ship's interior lights. The cabin brightness fades to near-zero over 10 frames to create darkness. At the same time, the camera field of view (FOV) locks straight to 85 degrees, focusing the player's view directly on the main projector.

- 🌌 **3D Volumetric Hologram Materials**: The Galaxy Map renders as a real-time volumetric 3D particle grid instead of a flat 2D texture. The material uses a semi-transparent, glowing look with a fast noise jitter to simulate a glitchy, unstable laser projection. The planet models (Ceroscan and Del-Alformar) slowly rotate and emit a soft blue glow that dynamically lights up the cockpit interior and Witya's gloves.

- 🎯 **Planet Selection & Jump Block**: The player aims at planets using a standard screen-center cursor. When the player hovers over the Del-Alformar planet hitbox, the system blocks the hyperdrive confirmation click. Instead, it stops the jump from loading, forces the joke subtitle text to appear at the bottom of the HUD, and immediately plays Witya's defensive voice line.

---

#### **🎥** CINEMATIC DEPLOYMENT: ARBITRARY CELEBRATION (PLANET CEROSCAN)

- **The Red-Carpet Landing**

**Arrival Transition Cut**: The scene opens at the Ceroscan space-port landing pad. The cockpit canopy opens. Witya turns his back toward Katya, triggering the **Back-Harness Attachment Logic** so she snaps right onto his magnetic klemma socket.

**Acrobatic Dismount Loop**: Witya jumps high out of the cockpit, does a flashy double-somersault in the air, and lands clean on both feet right onto a bright red carpet.

- 🚶‍♂️ **The Exaggerated Adolescent March Choreography**

**Crowd Mesh Generation**: Both sides of the red carpet are packed with cheering NPC crowds (some standing still, some animated) waving flags with active particle effects.

**Locomotion Style Override**: Witya triggers a special, non-combat march animation (`Hero_Arrogant_March`). He swings his arms wide with a slight bend in the elbows, moving with a confident, rhythmic, bouncing stride straight toward the Games main entrance.

**Witya** (humming a tune to himself): I'm going, walking on the table.

---

#### **⚙️** AHIGH-ARROGANCE MARCH ANIMATION 


- 🕺 **Exaggerated Spine & Pelvis Twist**: The march animation overrides the normal forward walk layer by applying a heavy swagger modifier to the hips and pelvis. As Witya steps forward, his pelvis rotates sideways by a wide 15 degrees per stride, forcing his entire upper torso and harness straps to swing in a cocky, rhythmic side-to-side swagger.

- 👐 **Wide Uncoordinated Arm Swing**: Witya's arms (from `Shoulder_L/R` to `Hand_L/R`) completely turn off their standard combat IK (inverse kinematics). His arms execute wide, uncoordinated swinging movements, reaching up to 45 degrees forward with his elbows kept bent at a constant 30-degree angle. This setup creates a funny "wide open arms" look that syncs perfectly with his singing voice line.

- 🤸 **Springy Root Bounce**: Witya’s long legs (keeping his approved 1:5.5 proportions) use a bouncy movement curve along the vertical axis. Every time his heel hits the ground, his main root bone drops down by 80 mm and then quickly bounces back up like a spring. This makes his walk look springy and floaty, perfectly showing off his cocky pride after finally escaping the junk sectors of Meltin.

---

#### **⚙️** CINSTANCED CROWD OPTIMIZATION & LOD

- 👥 **Instanced Crowd Rendering & GPU Optimization**: To fill the corridors along the red carpet, the game uses a crowd manager with instanced meshes instead of spawning heavy character blueprints. The system renders between 300 and 500 crowd models simultaneously within the camera view. To save CPU performance, all movement loops and animations run directly on the GPU using vertex animation textures.

- 🎨 **Randomized Texture Shuffling & Animation Offsets**: To prevent identical clone models in the cheering crowd, the system randomly swaps 8 different color textures (mixing skins for civilians and Ranger fans) across the models. Also, each model's cheering loop (`Crowd_Cheer_Jump`) receives a random start time delay between 0.1 and 2.0 seconds so they do not jump in perfect sync.

- 📉 **Frustum Culling & Distance LODs**: The crowd system uses camera culling: any model outside Witya's active camera view instantly stops updating its code. For visible models, the Level of Detail (LOD) scales down based on distance: within 10 meters, models render at full polycount with working eye-tracking; beyond 25 meters, they switch to low-poly models with baked animations.

---

#### **⚙️** CELEBRATION VFX & FESTIVE PARTICLE SIMULATION

- 🎉 **High-Density Confetti Loops & Wind Effects**: The space-port plaza area uses a Niagara particle system that maintains between 5,000 and 7,000 active confetti flakes inside the camera view. The system processes particles on the GPU, using a simple Vector Field modifier to simulate wind currents. This makes the colorful rectangular foil pieces flutter, spin, and drift slowly down toward the red carpet.

- ✨ **Randomized Colors & Metallic Sheen**: To prevent the confetti flakes from looking like flat digital shapes, the material randomizes their look. The system randomly assigns 6 high-saturation color textures (matching the official Tonata Rangers branding colors) to the falling pieces. The material also features ultra-low roughness (0.01) and an anisotropic metallic setting to create bright, shifting reflections as the flakes catch the local star's light.

- 🎆 **Audio-Synced Firework Spawners**: Placed far away in the skybox layers (outside the playable level geometry) are 4 spawn points for firework salvos. Locked to specific beats of Witya's arrogant march song, these points shoot out vertical trail projectiles that explode into big, round bursts. To keep performance high, these distant explosions completely ignore physics and collisions, fading out and disappearing exactly 1.5 seconds after detonation.

---

### **📺** MISSION CINEMATIC: THE REGISTRATION GATE (PLANET CEROSCAN)

- 💼 **The Brats Weales Actor Profile**

**The Character Blueprint**: Standing right at the entry checkpoint is an elite NPC named **Brats**. He is wearing a formal cloth dress uniform instead of his standard heavy **Tonata Ranger hardsuit**.

**Anatomical Parameters**: The model is a massive, humanoid creature standing exactly 2 meters tall. His hand have exactly 3 fingers.

**Visual Sequence**: The moment Witya does his flashy acrobatic landing on the red carpet right in front of the gate, **Brats** steps in to interrupt his cocky march.

**Brats:** Whoa. That jump of yours looked pretty impressive, kid. Too bad there is definitely not a landing zone.
**Witya (Scratching the back of his neck, ears dropping slightly):** Oh. Right. Sorry about that.
**Brats (Sighing, lifting his datapad back up):** Whatever. I still need to check you in the registration list. What's your name?
**Witya:** Uh... Well...
**Katya (Optical lens zoom clicking as she enthusiastically speaks up from Witya's back-harness):** My name is Katya, and he is… Witty! His name is Witty!
**Witya (Snapping his head slightly to the side to glare at his back):** Hey! That is not my name! And... seriously, Katya, we've talked about this. "Witty" is an adjective, not a name!
**Katya (Mandible plate tensing in genuine mechanical confusion):** Then what criteria must a valid name possess?
**Brats (Tapping the screen, scrolling through the rows):** Well, either way, I don't see any "Witty" or Katya on this list.
**Witya:** Maybe... is there anyone who hasn't shown up yet?
**Brats (Stares at Witya for a second, then lets out a deep, booming laugh):** Ha! So you're just gonna steal the spot of whoever skipped out on the games? Seems you really want to get inside this arena. Alright, head on through. Judging by that double-flip, it actually makes sense to let you try. Go over to that central platform - the logistics team will hand you a **Training Weapon**.

---

#### **⚙️** THE TRAINING COURT

- 🚧 **The Tensabarrier Block Constraint**

**Level Geometry Layout**: Witya steps onto the starting pad of the training court. Brats walks up right behind him to close off the entrance.

**The Obstacle Interaction Logic**: The forward path is blocked by a standard **Tensabarrier** — a simple fabric ribbon stretched horizontally between two metal posts.

**The Invisible Wall Constraint**: Even though Witya's jump height would technically allow him to easily clear the ribbon mesh, the level design script must place a strict **Invisible Wall** directly over the barrier. This temporary block forces the player to follow the linear tutorial path toward the weapon pickup zone.

---

#### **🗃️** MASTER GLOBAL NOMENCLATURE: CHECKPOINT CONTROLLER

- 🦎 **Brats Weales (Братс Неслабог)** — A 2-meter-long, insect-like, anthropomorphic creature with wings on its back, but it has 4 limbs, two arms and two legs, instead of 6, as is usually the case with insects.

- **English Syntax Bounds**: 
***Name Meaning:*** Brats comes from a word brat.
***Surname meaning:*** Weales is a combination of the words weak and less. A brat without weaknesses. It's also similar to the word Wales, but that's a side word and has nothing to do with it.

🌐 **Russian Translation Context**:
- **First name**: Brats comes from the word "Brat" (Brother).
- **Surname meaning**: Neslabog comes from the combination of the word "Slaby" (Weak) and the prefix "ne" (not), meaning "not weak". Additionally, it is a blend of "Nesla" (Carried), "Vesla" (Oars), and "Bog" (God). He is the "Oars" with which the god Neporazh moves his boat "Tonata Rangers".

---

#### **⚙️** INVISIBLE WALL & BARRICADE COLLISION

- 🚧 **Barrier Model Placement**: The entrance layout uses a standard `SM_Tensabarrier` static mesh (a low fabric ribbon stretched horizontally between two metal posts). The mesh height is exactly 0.8 meters, serving as a clear visual boundary for the tournament gate.

- 📦 **Invisible Box Collision & Path Blocking**: To force the linear tutorial path, the level design tool places a transparent box collision trigger (`Col_Invisible_Gate`) directly over the barrier. This collision box extends upward to a total height of 5.0 meters, completely blocking Witya's 1.5-meter character collider from crossing the line.

- 📐 **Wall Contact & Physics Reset**: If the player tries to bypass the fence using a jump, Witya's collider hits the invisible box. The physics engine instantly drops his forward speed to zero and slides him down along the surface of the invisible wall. This setup stops the player from breaking the level bounds and falling out of the training zone.

---

#### **📥** PHASE: WEAPON DISTRIBUTION & TRAINING COURTS (ACT I)

- 💼 **The Logistics Stand Interaction**

**Control Authority Handover**: As soon as player control is restored, the player must guide Witya toward the logistics counter mesh. A drone/robot worker givestraining weapon along with a group of fluid capsules.

- **Weapon 01: Water Pistol (Водяной пистолет)**

**Operational Constraints**: A training firearm model with an infinite ammo setting. It fires a pressurized stream of liquid.

- **Weapon 02: Water Grenade (Водяная граната)**

**Operational Constraints**: A throwable capsule model filled with a translucent blue fluid. It triggers a splashing explosion of liquid upon impact.

---

#### **⚙️** COMBAT SANDBOX: THE TEST DUMMIES INTERACTION

- 🤖 **The Short-Circuit Probability Blueprint**

Target Actor Profile: The training court spawns several Test Dummy bots equipped with non-lethal water guns.

The Stun & Short-Circuit Mechanics: When hit by Witya's Water Pistol or Water Grenade, the dummy's AI enters a temporary stun animation loop (`Stun_Liquid_Idle`). Every water drop impact runs a quick chance check: there is a strict 17.7% chance that the dummy triggers a broken short-circuit animation (`circuit_Short_Failure`), completely turns off its skeleton physics transforms, and turns into static, non-functional level decoration.

- 💦 **Fictitious Damage Vectors & Wet Shake Loops**

Target Health Mitigation: The water streams shot by the Test Dummies deal fake tutorial damage. When Witya gets hit, the HUD UI simply subtracts values from his temporary shield/health bar, but his model completely ignores normal pain or stagger animations so the player doesn't lose control over movement.

The Dynamic Shake Trigger: If Witya gets soaked by too many water particles in a short time, the animation logic unlocks a funny flavor animation. When standing still or moving slowly, Witya triggers the `wet_Shake_Head` or `wet_Shake_Full_Body` animation clip — he physically shakes his head and 12-segment tail to throw off the water.

---

#### **📊** THE MULTI-TIER FAIL-STATE

- 💀 **Dynamic Respawn & Save Script Branching**

The game engine checks the global `Difficulty_Tier` variable to choose what happens when Witya's health bar drops to zero.

- **Tier 01: Minimum Difficulty**

**Fail-State Resolution**: An instant time-rewind script resets Witya’s position to exactly 5 seconds before the fatal hit. Autosaves trigger frequently outside of active combat. Manual saves are fully available right during fights.

- **Tier 02: Medium Difficulty**

**Fail-State Resolution**: Triggers a standard Game Over screen overlay. The engine stops the gameplay loop and turns off active physics. The player must manually select `LOAD_SAVE` from the main menu. Manual saves are blocked during combat.

- **Tier 03: Legend Difficulty**

**Fail-State Resolution**: Manual and automatic saves during the mission are completely disabled. Dropping to zero health wipes your current mission progress and triggers a hard level reload, snapping Witya right back to the absolute starting point of the entire zone.

- - **Tier 04: Plausible Difficulty**

**Fail-State Resolution**: Ultimate hardcore mode using a **Single-Life Constraint** (Permadeath). Reaching zero health wipes your save file completely, forcing you to restart the entire game from Act I.

**The Ceroscan Tournament Exception**: Since the training arena uses non-lethal water weapons, dying here on Plausible difficulty does not trigger the save deletion script. Instead, the game simply teleports Witya back to the start of the zone, resetting his position to the end of the opening cutscene with **Brats Weales**.

---

#### **⚙️** PROCEDURAL WET SHAKE ANIMATION & JIGGLE PHYSICS

- 💧 **Water Accumulation Tracker**: The character logic tracks a simple variable named `Body_Wetness_Index` (scaled from 0.0 to 1.0). Getting hit by the Test Dummies' water guns increases this value. Once it reaches the maximum 1.0 limit and Witya stands still in an idle state, the engine triggers a high-priority 45-frame shake animation (`wet_Shake`).

- 🐶 **Two-Phase Animal-Like Body Shake**: The shake animation is split across the skeleton to look like a wet animal shaking off water. Phase 01 shakes his head quickly left and right (over 20 frames). Phase 02 moves the movement downward, making his hips and lower back vibrate heavily sideways to shake the trapped water straight out of his fabric pants.

- 🌿 **Foliage Ear & Tail Brush Physics**: During the shake, the 4 dynamic plant ears and the fluffy tip of his 12-segment tail turn off rigid hand-made keyframes. The physics engine applies an independent jiggle setup with high acceleration. This forces the leaf tips and fluffy fur fibers to whip around in opposite directions to the bones, adding a nice delayed wobble at the end to visually confirm Witya is dry.

---

#### **⚙️** SHORT-CIRCUIT SHADER & EMISSIVE ELECTROCUTION VFX

- ⚡ **Spawning Sparks & Electrical Arcs**: The exact moment the 17.7% chance check triggers a short-circuit, the dummy locks into the `circuit_Short_Failure` animation. The Niagara manager must instantly spawn 3 separate electrical arc effects attached directly to the dummy's joints (`Spine_02`, `Neck`, and `Elbow_L/R`). These chaotic, fast lightning arcs must crackle all over its outer body armor.

- 🔮 **Glow Effect & Overload Material Mask**: The dummy's metal material needs a dynamic glowing noise mask layered over its basic texture. The material must toggle the glow brightness (`bloom`) rapidly up and down between 0.0 and 10.0 at a fast 45 Hz frequency. This simulates blinding blue-white electrical overloads burning through the wet metallic paint.

- 🔌 **AI Power-Down Logic & Turning into Decoration**: Over the final 15 frames of the short-circuit animation, the lightning glow fades smoothly down to 0.0. At the same time, the material gets 40% darker, loses its color, and becomes very rough to look like scorched, burnt steel. As soon as the animation ends, the system completely turns off the dummy's AI, blocks its weapon triggers, and permanently converts its physics box into a static, non-interactive prop.

---

#### **⚙️** WATER PISTOL FLUID PHYSICS & BALLISTIC STREAM NOTES

- 💧 **Continuous Ribbon Fluid Stream**: When the player holds down `[INPUT_FIRE]` with the Water Pistol equipped, the weapon logic must shoot a continuous stream of water particles using a GPU-driven Niagara Ribbon emitter. The system connects the flying particles dynamically in real-time, creating a smooth, glossy liquid jet effect that accurately catches light sources and screen-space reflections (SSR).

- 📐 **Ballistic Drop Arc & Range Limit**: The water stream must use natural physics instead of flying perfectly straight. The physics engine applies a gravity modifier (set to 1.1) and air resistance to the water particles right after they leave the muzzle. This forces the stream to fall naturally in a downward-curving ballistic arc with a maximum range of 12 meters, making the player aim higher when shooting distant Test Dummies.

- 💥 **Splash Interaction & Wetness Increment**: The front tip of the water stream must run a continuous sphere-sweep trace (0.15-meter radius check) to find targets. Upon hitting a Test Dummy's skeleton collision, the main ribbon particles destroy themselves, trigger a small water splash VFX burst, and add a progressive value (+0.08 per frame) directly to the target's `Body_Wetness_Index` until it hits the 1.0 limit

---

#### **⚙️** FAIL-STATE INTERFACE & DIFFICULTY SETTINGS

- 🔴 **Global Red Vignette & Sound Muffling**: The exact frame Witya's health drops to zero, the UI system displays the main `w_FailState_Panel`. Over the first 15 frames, a dark red vignette smoothly spreads across the screen, turning the game view desaturated and dark crimson. At the same time, the master audio volume drops by 80% using a heavy low-pass filter to simulate losing consciousness.

- ⚄ **Button Layout Changes by Difficulty**: The menu buttons change automatically based on the active `Difficulty_Tier` variable settings:
    - **Tiers 01 & 02 (Minimum / Medium)**: The screen displays a standard three-button layout: `[RETRY_CHECKPOINT]`, `[LOAD_SAVE_MENU]`, and `[RETURN_TO_MAIN_MENU]`. The default selection focus automatically snaps right to the retry button for quick gamepad usage.
    - **Tier 03 (Legend)**: The interface layout maintains the standard button tree, allowing the player to freely use the `[LOAD_SAVE_MENU]` option to load past manual saves after failing.
    - **Tier 04 (Plausible)**: The system completely hides and disables the `[LOAD_SAVE_MENU]` button from the screen layout. Navigation locks strictly between a flashing red `[RESTART_CHALLENGE]` button and the main menu button, blocking any manual file loads to force a full challenge restart.

- 📄 **Glitchy Text Effects & Smooth Blackout Fade**: The main screen text (like _TERMINATED_ or _TOURNEY RESET_) plays a horizontal glitchy scanline distortion effect when it appears. Once the player clicks retry or reload, the interface layer fades to total black over 10 frames to completely hide the level reload and streaming before bringing back the standard gameplay HUD

---

### **📥** TONATA TOURNEY

- 💼 **The Linear Mission Progression**

**Level Structure Note**: The Ceroscan tournament design features exactly three separate trial corridors that unlock one after another. To keep this document short and clean, this layout serves as a master guide for the level design team to build maps without listing every single minor decoration placement.

---

### **🗺️** LEVEL DESIGN TOPOLOGY: COURTYARD ONE (THE METAL CLIMB)

- 🧱 **The Wall-Jump Vertical Chimneys**

**Level Geometry Architecture**: The first trial area is a steep vertical metal structure with static platforms attached to it. The main path includes exactly two narrow steel shafts (vertical chimneys). To climb up to the next level, the player must use alternating left-and-right wall jumps (`Wall_Jump_Loop`) inside the metal framework.

- 🤖 **The Test Dummy Platform Blocker**

**Enemy Navigation Path**: Right in the middle of the vertical metal ascent stands a patrolling Test Dummy bot. It continuously walks back and forth along a critical path on a narrow metal platform.

**Knockback Interaction Logic**: The dummy is designed to block the platform. If the player tries to jump over it without stunning it first with water, the dummy's collision box applies a strong horizontal force, pushing Witya right off the edge of the steel beam so he falls back to the bottom grid.

**Tactical Stun Lock**: The player must use the Water Pistol or Water Grenade to freeze the dummy at the far left or right end of its patrol path. This clears a safe opening to safely cross the metal platform substrate.

- - 🎯 **The Snipe Dummy Laser Occlusion Zones**

**Advanced Threat Deployment**: As Witya nears the top of the metal framework, the level spawns Snipe Dummy bots. These enemies sit on high, unreachable steel beams completely out of Witya's melee attack range.

**Visual Laser Raycast**: Each sniper bot projects a bright red laser sight targeting a specific spot on the main path. Moving Witya into this laser beam triggers an instant high-velocity water blast from the sniper, quickly filling his wetness bar.

- 🚠 **The Zipline Shortcut & Fan-Pack Backtracking Anchor**

**Level Connectivity Array**: At the very top of the structure sits a mechanism to open the gate to Trial Two, alongside a physical Zipline handle. Interacting with the handle locks Witya into a fast downward slide, taking him safely back to the starting area.

**The Visual Foreshadowing POI**: Looking out from the top platform, the player can see a separate, distant floating metal platform packed with Bolt Crates. This platform is too far to reach with standard Act I jumps. Reaching this secret area requires the player to backtrack here later after unlocking the **Fan-pack** upgrade.

---

#### **🗃️** UNBINIL REWARD: CHEAT VARIANT MODIFIER

- 🤐 **The Mute-Mode Toggle ("Режим молчуна")**

**System Unlock**: Collecting the second **Unbinil Bolt** item permanently changes the options menu, unlocking the "Mute-Mode" cheat toggle.

**Character Model Visual Override**: Turning this modifier to TRUE triggers an automated change to Witya’s character model:

1. The default mouth morph targets and facial blend-shapes turn off completely.
2. The mouth area is replaced with a smooth face texture, visually wiping his mouth away and sealing his jaw shut.
3. The audio manager completely mutes all of Witya's context, combat, and movement voice lines. The main story text remains fully readable through the standard subtitle overlay.

---

#### **⚙️** WALL JUMP SKELETAL ALIGNMENT & PROCEDURAL BOUNCE NOTES

- 📐 **Wall Contact Detection & Model Alignment**: When Witya touches a wall mesh in mid-air, the physics engine fires a quick check line to find the wall angle. If valid, the Character Controller turns off gravity and enters the `wall_contact` state for exactly 12 frames. Witya's rotation instantly snaps to face perfectly parallel to the wall, setting up his body for the push-off.

- 🦶 **Foot Placement & Shock Absorber Flex**: During these 12 frames, the foot touching the iron wall activates high-priority position alignment. The corresponding foot bone (`Foot_L` or `Foot_R`) must snap flat against the wall surface. To visually show off Witya's animal-plant biology, his ankle and knee joints must bend deeply by 60 degrees, compressing his legs like springs to build power before the jump.

- 🦎 **Spine Arch & Tail Counter-Weight Whip**: The exact frame the player hits `[INPUT_JUMP]` to push off the wall, his legs release into a fast launch animation (`wall_Push_off`). Witya's spine bones (`Spine_01` to `Spine_03`) arch backward by 15 degrees, while his 12-segment tail does a heavy, high-amplitude swing in the opposite direction. This tail whip stabilizes his balance in mid-air as he leaps toward the opposite steel beam.

---

#### **⚙️** LASER SIGHT & SNIPER DETECTION PROPERTIES

- 🔴 **Continuous Laser Sight Loop**: The static Snipe Dummy bot runs a continuous line-trace from its eye lens coordinates (`Muzzle_Optical`). The forward vector of this beam checks for the nearest wall, floor, or obstacle geometry, drawing a bright, solid red laser line directly in the player's view.

- 🎯 **Warning Target Marker**: At the exact spot where the sniper's laser hits the floor or platform, the system spawns a circular warning marker texture (`w_Snipe_Target_Zone`). This projection runs a pulsing fade animation (changing opacity between 0.4 and 0.8 at a 4 Hz speed) to act as a clear visual warning that alerts the player to the danger zone before they jump onto the platform.

- ⚡ **Laser Detection & Quick Attack**: If Witya’s 1.5-meter character hitbox crosses the laser beam or steps inside the warning marker radius, the system instantly breaks the sniper's idle mode. The logic locks the enemy's aim onto Witya's root bone, shifts the laser color from steady red to a fast-flashing bright crimson over 5 frames, and instantly fires a fast stream of pressurized water to quickly fill his `Body_Wetness_Index`.

---

#### **⚙️** ZIPLINE SLIDING PHYSICS & SPLINE INTERPOLATION PROPERTIES

- 🚠 **Path Alignment & Handlebar Attachment**: When Witya enters the 1.5-meter trigger box around the zipline mount and the player presses `[INPUT_INTERACT]` or `[INPUT_JUMP]`, the character controller instantly turns off normal gravity and snaps his position directly onto the 3D spline line (`spline_zipline_Route`). At the same time, Witya's hand bones attach tight to the moving handlebar sockets (`Socket_Handlebar_L/R`), locking his torso forward along the cable path.

- 📈 **Gravity Acceleration & Velocity Clamp**: The sliding speed down the line must look dynamic instead of running at a fixed rate. The physics engine must calculate acceleration based on the track's slope angle: as the path gets steeper, the movement speed scales up linearly from a starting 8.0 m/s up to a maximum velocity limit of 22.0 m/s, giving the player a fast cinematic reward rush for beating the vertical track.

- 🦎 **Body Sway & Dynamic Drop Clearance**: While sliding, the animation system passes Witya's real-time velocity data to a physical movement tracker. This setup forces his lower body, long legs (maintaining the approved 1:5.5 ratio), and 12-segment tail to swing sideways by up to 12 degrees to simulate wind resistance and inertial forces. Upon reaching the end of the line, the hands automatically detach, and full player movement control is restored instantly with a short 5-frame landing animation.

---

### **📥** THE SECOND TRIAL (THE WATER ARENAS)

- 💼 **The Horizontal Mission**

**Level Structure Note**: The second trial corridor focuses strictly on horizontal movement across **three flat, water-filled stadium arenas** arranged as a multi-tier tiered steel structure. This sub-zone introduces more active patrolling enemies combined with dangerous water hazards where the player can fall off the edges.

- 🏢 **The Flat Arenas & Narrow Choke Points**

**Level Geometry Architecture**: Arena One features a flat horizontal path split by deep training pools. The main progression route uses narrow connecting bridges and steel walkways.

**Enemy Sub-Zone Deployment**: Patrolling these narrow walkways are standard Pistol Dummy bots.

**The Stun-and-Leap Puzzle:** To cross the tightest choke points, the player cannot simply sprint through. Witya must fire a pressurized water stream to fully stun the patrolling dummy, temporarily turning off its physical blocking behavior before performing a horizontal jump over the water gap onto the next platform.

- 🌊 **The Liquid Drop-Off Penalty Clamp**

**Fail-State Health Mitigation**: The open water pools surrounding the platforms act as non-lethal hazards. Falling into the water does not trigger a full checkpoint reload screen.

**System Damage Evaluation Rule**: Falling into the water subtracts exactly 43% of Witya's maximum health. This balancing ensures that Witya can survive exactly two consecutive falls at full health before triggering the Game Over screen.

- ⚙️ **The Intermediate Moving Platform

**Advanced Traversal Mechanics**: Upon entering Arena Two, the level architecture introduces dynamic hazards. Several platforms is moving, sliding horizontally or vertically along paths to test the player's jumping precision.

- 🎯 **The Aggressive Sniper Tracking Interface**

**High-Tier Enemy Logic**: Arena Three deploys Snipe Dummy bots directly onto the main path instead of keeping them on unreachable distant beams.

**System Target Tracking Override**: The sniper AI stops passive area scanning. The eye lens socket (`Muzzle_Optical`) fires a continuous raycast that locks onto and actively tracks Witya's real-time movement coordinates.

**The Neutralization Objective**: Witya cannot dodge this tracking forever. The player must aggressively close the distance to short-circuit the bot with a water overload to permanently shut down the sniper before the crimson charge bar fills up and triggers the water blast.

- 🚠 **The Terraced Shortcut Connection**

**Level Connectivity Array**: Because each next water arena stands higher than the previous one, the very end of Arena Three houses the main exit gate switch. It features a physical **Bolt Gyrate** mechanism and a secondary Zipline handle. Activating this node returns Witya safely back to the baseline area via a fast-sliding shortcut.

---

#### **⚙️** WATER HAZARD LOGIC & PROCEDURAL RESCUE

- 🌊 **Water Damage Calculation**: When Witya touches the training pool water trigger, the system bypasses the standard death sequence. Instead, the logic subtracts exactly 43% of Witya’s maximum health. This balance ensures that a player falling into the water with 100% full health can survive exactly two consecutive falls, leaving a critical 14% survival buffer in their health bar.

- 🛡️ **The 14% Health Survival Window**: This remaining 14% health functions as a safety window. While locked in this low-health state, Witya's movement speeds and controls remain fully active. This buffer is specifically scaled to absorb exactly one standard water shot from a Pistol Dummy bot without killing the player, giving them a fair chance to execute a recovery.

- 🏊 **Automated Swim & Ledge Climb-Up**: Right as the health reduction triggers, player movement input is temporarily locked. The character controller switches Witya into a swimming animation, automatically routing him to the nearest yellow industrial ladder or low metal deck border of the pool. Upon reaching the edge, the system triggers a brief 45-frame climb-up animation (`Pool_Ledge_climb`), resets his `Body_Wetness_Index` to max, and restores full movement control to the player..

---

#### **⚙️** ACTIVE SNIPER TARGET TRACKING & LOOK-AT AI LOGIC

- 🎯 **Dynamic Look-At Bone Logic**: Upon detecting Witya’s entry into Arena Three, the sniper’s AI controller begins tracking him permanently. The skeleton rigging overrides the head and muzzle bones (`Bone_Head_LookAt`, `Muzzle_Optical`), passing a continuous look-at vector aimed straight at Witya's center of mass. The sniper model rotates smoothly toward the player, completely replacing the static area-scanning mode used in Trial One.

- 📈 **Tracking Lag & Dodge Window**: To keep combat balanced, the sniper's aim cannot snap instantly to Witya's exact position. The AI limits the tracking rotation speed to a maximum of 45 degrees per second. If the player executes a well-timed long jump or a fast side dodge roll (`Dodge_Side_Jump`), they can temporarily outrun the sniper’s turn rate, generating a brief 0.5-second safety window before the laser sight catches up to Witya.

- ⏱️ **Continuous Lock-On Timer**: As long as the sniper's laser beam hits Witya's collision box, an internal `LockOn_Timer` variable scales upward linearly. Once this timer hits a 1.5-second limit, the laser color shifts from steady red to a fast-flashing bright crimson over 15 frames, instantly firing a continuous pressurized water stream targeting the player.

---

#### **⚙️** MOVING LEDGE PHYSICS & PLATFORM INERTIA PROPERTIES

- ⚙️ **Path-Driven Platform Navigation Loop**: The sliding platform static meshes (`SM_Moving_Ledge`) move along a predefined path layout (`Spline_Ledge_Track`). The movement speed must not be stiff or uniform; instead, the system applies smooth easing at the very ends of the path. This setup ensures the platform smoothly slows down to a complete stop (0.0 m/s) before reversing its direction over a 30-frame window, giving the player a clear timing window for their jumps.

- 🤝 **Platform Velocity Locking**: When Witya’s feet touch the top collision surface of a moving platform, the character controller instantly reads the platform’s current speed. The engine locks Witya’s position relative to the moving platform using a temporary velocity link. This stops his 1.5-meter character model from lagging behind or sliding off the edge while the platform carries him across the training pools.

- 🏃‍♂️ **Inertia Transfer on Jump**: The exact frame the player hits `[INPUT_JUMP]` to leap off a moving platform, the velocity link releases its lock. The physics engine reads the platform’s speed at that millisecond and adds it directly to Witya's jump momentum as a bonus speed multiplier. This ensures that if Witya jumps while the platform is moving fast forward, his flight path extends realistically forward, keeping him from dropping straight down into the water.

---

#### **⚙️** AUDIO DESIGN & HYDRAULIC LEDGE SFX PROPERTIES

- 🔊 **Pneumatic-Hydraulic Sound:** The continuous movement of the platform along its path triggers a multi-layered spatial audio loop. The sound mix combines a low-frequency heavy mechanical engine hum (set to 100 Hz to convey heavy weight), a mid-range hydraulic hiss, and a high-frequency rhythmic metallic whir that tracks the platform's position relative to the camera view.

- 📈 **Speed-Based Pitch & Volume Scaling**: The main audio track links its volume and pitch directly to the current speed of the `SM_Moving_Ledge` model. As the platform speeds up after leaving its stopping point, the audio engine turns up both pitch and volume linearly by a factor of 1.3. This creates a natural sound feedback that alerts the player to the platform's speed changes without using messy screen UI indicators.

- 💥 **Edge Stop Sound & Valve Release**: The exact frame the platform reaches the very end of its track and stops to reverse its direction, the default hum loop temporarily cuts off. The system fires a high-priority sound effect combining a heavy mechanical thud, a metallic brake screech, and a sharp pneumatic valve hiss (`SFX_Pneumatic_Release`) to let the player hear the platform resetting.

---

### **📥** TONATA TOURNEY — THE THIRD TRIAL

- 💼 **The Hybrid Mission Progression**

**Level Structure Note**: The final trial corridor features a massive, elevated modular metal arena. It acts as a complex combined gauntlet, blending the vertical parkour elements from Trial One with the horizontal platforming and dangerous water hazards from Trial Two.

- 🏢 **The Target-Linked Moving Platform Array**

**Level Geometry Architecture**: The main path consists of static metallic plates linked to dynamic sliding platforms.

**The Interconnected Stun Puzzle**: Standard Test Dummies patrol the static plates. The player must land multiple pressurized water streams to stun a single dummy several times in a row. Every time the dummy gets stunned, a connected moving platform shifts into a new position, clearing a safe path for Witya to cross.

- 🛠️ **The Blind Platform Catch & Test Dummy Logic**

**Traversal Blind-Spot Zone**: The path forces Witya into a deep vertical steel shaft (chimney). Positioned right at the very top is a hidden metal ledge patrolled by another Test Dummy bot.

**The Audio-Cue Blind Jump Mechanic**: Because the camera angle prevents the player from seeing the top edge, the Test Dummy remains completely hidden from view. The player must listen closely to the dummy's moving footsteps to guess its position by sound. To climb up safely, the player must time their jump, wall-climb, or shoot a water stream in mid-air exactly when the bot walks away from the edge.

- ⚙️ **The Moving-Platform Combat Intercept**

**Dynamic Platform Combat**: Witya must leap onto a moving metal platform that constantly slides back and forth along a set path.

**The Continuous Stun Constraint**: A Test Dummy patrols right on top of this moving platform. The player must continuously shoot water to keep the dummy completely frozen. If the stun effect wears off, the dummy's push-away logic activates, shoving Witya off the edge into the water hazard before the platform reaches the other side. Alternatively, the player must use perfectly timed long jumps or side dodges (`Dodge_Side_Jump`) to clear the enemy's hitbox entirely.

- 💥 **The Boom Dummy Artillery Array & Difficulty Scale**

**Mid-Point Hazard Overload**: Reaching the midpoint introduces **Boom Dummy** bots (Манекены-бомбилы). These heavy artillery units stand on higher or lower parallel walkways, lobbing non-lethal water-capsule grenades directly onto Witya's platform.

- **The Magnetic Arc Ballistics**: Because the central structure is made of heavy metal, the thrown grenades ignore standard physics and travel along a tight, curved magnetic arc straight toward the player.

- **The AI Difficulty Randomizer**: On the **Legend** and **Plausible (Realism)** difficulty settings, the system turns off uniform attack timers. The Boom Dummies use a completely randomized attack script, stopping the player from memorizing safe timing windows and forcing them to rely on pure reflexes.

---

#### SYSTEM MECHANICS: DIFFICULTY-BASED SNIPER OVERRIDE

- 🎯 **The Sniper AI Difficulty Settings**

The tracking behavior and targeting logic for all Snipe Dummy bots across the metal arena change automatically based on the global game difficulty level.

- **Low and Medium Difficulty Tiers**: The snipers are locked into a passive scanning mode. The eye lens projects a steady red laser sight onto a fixed spot on the floor, letting the player easily see and avoid the warning decal zones.
- **High and Realism Difficulty Tiers (Legend / Plausible)**: The system overrides the passive logic and turns on active tracking. The snipers cast their laser sights directly onto Witya's body to actively hunt him and track his real-time position coordinates.

- 🚠 **The Hub Shortcut Return**
**Level Connectivity Array**: At the very top of the metal framework sits the main terminal key to complete the tournament zone. Interacting with this console opens the gate and unlocks a final Zipline handlebar. Grabbing it routes Witya down a fast, long sliding shortcut straight back into the main hub sector.

---

#### **⚙️** MAGNETIC ARC BALLISTICS & WATER BLAST PHYSICS

- ☄️ **Magnetic Parabolic Curve**: When a Boom Dummy attacks and throws a water grenade, the projectile ignores normal game gravity physics. The physics engine applies a custom acceleration vector that pulls the grenade downward 8% faster per frame as it gets closer to the metallic arena plates. This logic forces the grenade to curve sharply downward at the peak of its throw, creating a tight, aggressive magnetic arc toward the player.

- 💥 **Water Detonation & Blast Radius**: The water grenade checks for collisions using a moving sphere-sweep with a 0.5-meter radius. As soon as it touches the steel deck plates or Witya’s character collider, the grenade explodes and triggers the `Water_Blast_Sequence`. The explosion runs a 1.5-meter spherical zone check: it deals zero real damage to his health bar but applies a powerful horizontal push force to Witya.

- 💦 **Instant Wetness Increment**: Anyone caught inside the 1.5-meter explosion radius is instantly soaked by water particles. Witya's internal `Body_Wetness_Index` immediately jumps up by a massive +0.45. This fast-soaking mechanic is balanced to force the player to prioritize dodging the Boom Dummy artillery strikes: absorbing just two consecutive grenade blasts will instantly fill his wetness meter and trigger Witya's Wet Shake Sequence, locking his controls at a dangerous moment.

---

#### **⚙️** HIGH-DIFFICULTY ARTILLERY RANDOMIZER & AI LEAD CALCULATION

- 🎲 **Randomized Throw Interval Script**: When the system verifies that the global `Difficulty_Tier` variable is set to high or realism, the engine turns off fixed attack timers. The Boom Dummy's reload time updates on every tick using a randomized calculation, clamping the duration between an unpredictable 1.1 and 3.4 seconds. This randomness breaks predictable combat rhythms and forces the player to adapt on the fly.

- 🎯 **Dynamic Velocity Lead Calculation**: The AI controller stops throwing grenades directly at Witya’s current position. Instead, the script reads Witya’s directional vectors and movement speed (`D-SAW` outputs) over the last 10 frames. Using this data, the system calculates a predicted intercept point (`Target_Lead_Vector`) and aims the magnetic throw arc right into Witya's path, punishing players who simply sprint in a straight line.

- 🤝 **Coordinated Group Fire Restraint**: To prevent all 3 to 5 active Boom Dummies from randomly shooting at the exact same frame — which would create an impossible wall of water explosions — the system uses a global queuing script. The main arena manager tracks all active artillery bots: if one dummy throws a grenade, a system lock blocks the other bots from throwing for exactly 15 frames, forcing a dense, staggered, and fair artillery sequence.

---

### **📺** THE HUB RESET & BRATS WEALES PROFILE

- 🏥 **The Central Hub Health Restoration**

**System Refresher Loop**: The exact frame Witya lands back in the central hub after the zipline descent, the health manager runs an automatic script. Witya’s health bar instantly refills to 100% for free. This reset ensures the player has full health before starting the next combat phase.

**Gateway Opening Event**: Brats Weales, who had been monitoring the obstacle course from his post the whole time, opens the Tensobarrier and goes straight to the central platform of the arena.

**Brats:** Congratulations, Katya, and congratulations, Witty. You did an exceptional job clearing all the trials.
**Witya:** Thanks.
**Brats:** Now, it is time for the final one.
**Witya:** The final what?
**Brats:** Me. I've been watching your movements. Only a few in my memory have managed to pass the games as cleanly as you... I want to test you personally. Don't worry, I will also use water weaponry.

---

### **⚔️** BOSS ENCOUNTER: BRATS WEALES

- 🎲 **Multi-Tier Attack Profiles**

The boss battle tracks Brats' current health percentage (`Boss_HP`) and checks the global difficulty setting (`Difficulty_Tier`) to dynamically change his attack patterns and fire rates.

#### 1) The Water Pistol AoE Strike Array (Водяной пистолет)

- **Standard Pattern (Low/Med Difficulty & Boss_HP > 40%)**: Brats aims and projects a single, bright circular warning marker onto the stadium floor. After a brief 15-frame startup warning (telegraph), he fires a water shell that explodes exactly in the center of that marker.

- **Low/Med HP Decay Modification (Boss_HP < 40%)**: The system increases the number of active targeting zones, forcing Brats to throw out multiple simultaneous warning markers at once.

- **High Difficulty Override (Legend/Plausible)**: Brats completely skips the single-target phase, projecting multiple warning markers across the floor from the absolute start of the battle. Once his health drops below 40%, the total number of simultaneous target markers scales up by an additional 50%.

---

#### 2) The Homing Water Rocket (Водяная ракета)

- **Standard Pattern (Low/Med Difficulty & Boss_HP > 40%)**: Brats opens his arm launchers to fire a single fluid-capsule rocket that actively tracks Witya's for up to 3.0 seconds. If the player avoids it for 3 seconds, the rocket loses its propulsion and drops to the floor.

- **Low/Med HP Decay Modification (Boss_HP < 40%)**: The launcher count scales up, firing two homing rockets one after another to double the pressure and force more precise dodging.

- **High Difficulty Override (Legend/Plausible)**: Brats fires both homing rockets at the exact same time right from the start of the boss battle.

- **High Difficulty Apex Modification (Boss_HP < 40%)**: The twin homing rockets launch in opposite directions sideways, tracing a curved pincer movement curve. The rockets close in on Witya from both flanks at once, locking the young **Fustix** in a tight tactical trap.

---

#### 3) The Pressure Water Shotgun — Jump-Over Vector (Водяной дробовик)

- **Standard Trigger Constraints (Low/Med Difficulty)**: This attack is completely locked until `Boss_HP` drops below 33%. Brats executes a 1.0-second visible weapon charge animation (telegraphed via a loud pneumatic audio cue). He then discharges a massive, flat horizontal water wave cutting across the floor. The collision height is clamped at 0.6 meters, forcing a strict jump-over mechanic: Witya can only avoid getting wet by performing a jump.

- **High Difficulty Override (Legend/Plausible)**: The Water Shotgun attack is unlocked and fully active from the absolute start of the boss battle.

- **High Difficulty Apex Modification (Boss_HP < 33%)**: Upon entering the critical low-health phase, Brats fires the horizontal shotgun wave twice in a row within a tight 20-frame window. This requires the player to execute two separate vertical jumps in rapid succession — hopping over the first wave, instantly hitting the deck, and jumping immediately a second time to clear the final wave.

---

#### **⚙️** HOMING PROJECTILE PHYSICS & PINCER VECTOR LOGIC

- 📐 **Homing Target Tracking**: Upon spawning at Brats's arm launcher socket, the water rocket locks its aim directly onto Witya's spine joint (`Spine_02`). The logic constantly calculates the direction vector toward the player's position, limiting its turning speed to exactly 60 degrees per second. This prevents the rocket from snapping instantly to the player and gives Witya a fair window to outrun its turn rate.

- ⏱️ **Lifespan Timer & Speed Acceleration**: The rocket cannot chase the player forever. It has a strict maximum life timer set to 3.0 seconds after spawning. During flight, its speed accelerates progressively from a starting 10.0 m/s up to a maximum velocity limit of 18.0 m/s. If the timer runs out before hitting Witya's collision box, the rocket loses its homing tracking, falls naturally due to gravity, and breaks apart upon hitting the steel floor.

- 🦀 **Pincer Trajectory Launch Offset**: When the system switches to the high-difficulty peak phase (`Difficulty >= High AND Boss_HP < 40%`), the logic adjusts the default direct tracking path. The twin rockets launch outward with a temporary 45-degree horizontal angle away from each other (left and right vectors) for exactly 15 frames. After this brief split window, the homing tracking turns back on, forcing the twin capsules to curve sharply inward in a pincer arc that closes on Witya from both flanks at once.

---

#### **⚙️** WATER SHOTGUN WAVE FX & HORIZONTAL COLLISION PROPERTIES

- 🌊 **Water Wave Material & Ripple FX**: The horizontal wave uses a flat mesh component with an additive, translucent water material. The material runs a scrolling wave ripple texture that moves rapidly forward to visually show its speed. To emphasize the heavy water pressure, the front edge of the wave has a high glow multiplier (3.5), creating a bright neon-blue crest that acts as a clear visual guide for the player to track the danger.

- 📐 **Height-Clamped Platform Collision**: The collision boundaries of the water wave use a thin, wide Box Collision component (`col_Shotgun_Wave`). Its dimensions are locked: the horizontal width extends to 15.0 meters to fully cover the central arena, while the vertical height is strictly clamped to exactly 0.6 meters. This height limit guarantees that Witya’s 1.5-meter character model can easily avoid the attack only by executing a well-timed jump.

- 💥 **Double-Wave Attack & Double-Jump Window**: Upon checking that the boss health is below 33% on High difficulty, the logic starts a double-shot attack. The engine spawns two independent wave meshes separated by a tight 20-frame delay. The player cannot clear both collision layers with a single jump; Witya must land two separate vertical jumps in rapid succession, hitting the floor after the first wave and jumping instantly again to clear the second one.

---

#### **⚙️** TUTORIAL DAMAGE EFFECTS & IMPACT STAGGER

- 📐 **Bone-Relative Hit Impulse**: At the exact frame where the water rocket's collision box hits Witya's 1.5-meter character collider, the system triggers an animation override in his animation graph (`AnimBP_Witya`). The engine applies a physical push force based on the impact angle: forcing his upper spine joints (`Spine_02` to `Spine_03`) to execute a rapid 15-degree backward tilt to visually show the heavy weight and force of the pressurized water blast.
- 🔴 **Speed Penalty & Movement Stagger**: The impact frame triggers a short 12-frame stagger animation state (`Hit_Water_Stagger_M`). During this short window, the movement system cuts Witya’s current forward speed (D-SAW movement speed) by 60% over 6 frames, before smoothly accelerating him back to full speed. This mechanic punishes the player for failing to dodge, disrupting their running rhythm without freezing their inputs completely.
- 💦 **Wet Material Layer Overlay**: Along with the stagger animation, the hit frame changes the material settings on Witya's fur and strap textures. The material instantly blends a high-gloss, ultra-low roughness (0.01) wet layer across his entire 3D model. At the same time, it fires a localized water splash particle effect (Niagara burst) that sprays droplets outward horizontally to confirm the massive jump in his `Body_Wetness_Index`.

---

#### **⚙️** BOSS HEALTH BAR UI/UX LAYOUT & PROGRESSION INDICATORS

- 🖥️ **Screen Anchor & Canvas Alignment**: When the boss fight starts, the UI manager spawns the main boss health widget (`W_Boss_Health_Root`) at the bottom center of the screen, taking up the lower 15% grid boundary. The health bar layout features a stylized industrial metal bracket texture frame that holds a wide, high-contrast horizontal progress bar. This design completely separates the boss UI from the smaller player health widgets.

- 📊 **Dual-Layer Delayed Damage Animation**: The main progress bar uses a dual-layer texture setup to make landing weapon hits feel highly responsive and visually rewarding to the player:
    1. **Layer 01 (Instant Foreground)**: The main bright crimson health bar drops instantly down to the new calculated `Boss_HP` value the exact frame Witya's weapon strike registers a hit on the boss.
    2. **Layer 02 (Delayed Background Catch-Up)**: A secondary dark-orange under-bar texture stays frozen at the old position for exactly 15 frames after the impact. Then, it smoothly glides down over 20 frames to match Layer 01. This leaves a temporary visual trail that highlights exactly how much damage the player's last hit dealt

- 🚨 **Phase Threshold Notches & Critical Flash States**: To help the player track Brats's phase changes without cluttering the screen with text pop-ups, the health bar track includes two small structural notch dividers at exactly the 40% and 33% marks. When Brats's health drops past these markers, the entire health widget triggers a fast flashing alert animation layer over 10 frames. This cleanly signals to the player that Brats has officially activated his advanced homing rockets or double shotgun waves.

---

### **⚔️** THE BOSS MOVEMENT STATES & COOLDOWN LOGIC

The boss blueprint features two distinct, alternating movement states managed by a dynamic cooldown script and difficulty modifiers.

**State 01: Ground Movement**

- **Ground Combat Logic**: Brats moves along the flat floor using standard enemy walk and run animations. In this state, his character collider is fully vulnerable to hits from both Witya’s Water Pistol streams and Water Grenade explosions.

**State 02: Airborne Wing Maneuvers**

- **Flight System**: Brats opens his insect-like wings and launches into a low-altitude flight mode. His movement script switches to a fast, erratic evasive system, making him perform sudden horizontal and vertical dashes to dodge the player's attacks.

- **Water Grenade Immunity**: While airborne, Brats's 3D model automatically ignores all throwable area-of-effect attacks. Throwing a Water Grenade at him while he flies results in a guaranteed miss; the player is forced to track him with the continuous stream of the Water Pistol to slowly chip away his health.

- **Difficulty Scaling Scaling**: The length and frequency of State 02 scale up linearly based on the global difficulty setting. On higher difficulty tiers (Legend / Plausible), Brats stays in his flying state 60% longer and shortens his ground recovery windows, keeping the pressure on the player.

---

### **🎥** CINEMATIC LAYOUT: THE TOURNEY TRIUMPH & BLUE CARD AWARD

- 🎬 **The Combat Intercept**

**Cinematic Transition Cut**: The exact moment Brats's health drops to zero, player control turns off, and the scene switches to a close-up cinematic camera. Brats turns off his water weapons and holds up his hand to stop the fight.

**Brats**: That’s enough.

**Visual Sequence**: Brats takes three slow, heavy steps forward, walking up to stand directly in front of Witya.

**Brats**: That was impressive. Congratulations, cadet, I haven't had a fight that dynamic in a very long time.  
**Witya** (with twitching ears and a light shrug): Thanks.  
**Brats** (bursting into a deep, booming laugh): Ha! Thank _you_. In any case, even if **Unlas** wasn't watching, the broadcast television certainly won't forget!  
**Witya** (with wide, excited eyes): Whoa, cool!

- 💳 **The Key-Card Distribution Interaction**

**Visual Sequence**: Brats reaches into the pocket of his uniform and pulls out a flat, glowing neon-blue card (a sector pass) and hands it to Witya. Vitya takes the card and carefully tucks it into his pants pocket.

**Brats:** Here, take this. The main building is right over there, and Unlas's office on the top floor. Good luck.

---

#### **⚙️** INSECTOID WING HOVER PHYSICS & EVASIVE DASH ILOGIC

- ⚙️ **Low-Altitude Wing Flight & Air Hover**: Upon entering State 02, the boss blueprint turns off his ground walking logic and activates a biological lift animation. The physics engine locks Brats's root position into a stable flight mode clamped precisely at 3.5 meters above the metal floor. The animation system triggers a high-frequency wing flap cycle, while the VFX manager spawns a heavy air-distortion particle ripple effect around his back to visually support his heavy metallic-scale mass staying in mid-air.

- 🏃‍♂️ **Erratic Wing Dash Evasion**: To avoid getting constantly hit by Witya's pressurized Water Pistol stream, Brats's flight logic runs a real-time raycast evasion check. If the incoming water stream hits a 1.5-meter threat sphere around his body, the AI triggers a high-velocity wing dash vector (`Flight_Dash_Step`). Brats performs a sudden sideways dash along the horizontal plane at a fast speed of 16.0 m/s, using a snappy movement curve over exactly 15 frames to cleanly dodge the fluid attack.

- ⚄ **Cooldown Scaling by Difficulty**: The delay between his flight maneuvers is directly managed by the global difficulty tier. On Low and Medium difficulty settings, the internal cooldown between consecutive wing dashes is locked to a long 20-second delay window. On High and Realism (Legend / Plausible) difficulty tiers, this cooldown is cut straight down to just 5 seconds, forcing Brats to execute rapid, back-to-back zigzagging maneuvers in mid-air that demand high aiming precision from the player.

---

#### **⚙️** BLUE KEY-CARD MATERIAL SHADER & INVENTORY LOGIC

- 💳 **Translucent Polycarbonate & Inner Neon Core**: The static mesh of the pass card (`SM_Blue_Sector_Pass`) uses a two-layer material setup. Layer 01 uses a translucent frosted plastic material with high roughness (0.4) to blur backlights naturally. Layer 02 acts as a glowing inner core, using a high emissive multiplier (4.0) to cast a soft cyan-blue light that visibly illuminates Witya's hands during the hand-over cutscene.

- 💻 **Dynamic Digital Scanning Mask**: The flat face of the card mesh includes a moving scan mask layer. The material procedurally scrolls lines of glowing digital micro-text and data code horizontally across the surface. This interface animation triggers a quick 1-frame brightness flash whenever the card faces the camera directly, simulating an active scanning signal.

- 🔑 **Inventory Check & Gate Unlock Trigger**: As soon as the pickup animation finishes, the physical card model is removed from the level, and its unique reference code (`Item_ID_Ceroscan_BluePass`) is added to Witya's global inventory list. This item has no weight or 3D model during normal gameplay; it works strictly as a key token that lets Witya open the locked doors.

---

#### **⚙️** ITEM TRANSFER SKELETAL SYNC & IK HANDOVER PROPERTIES

- 📐 **Two-Handed IK Tracking for Handover**: When the key-card delivery cutscene triggers, the animation system activates a twin Inverse Kinematics (IK) tracking setup. Brats's right wrist bone (`Brats_Wrist_R`) smoothly drops down to a 1.2-meter height vector. At the same time, Witya’s right arm bone chain (`Shoulder_R` to `Hand_R`) lifts up along the vertical Z-axis, automatically locking his hand position straight onto the coordinates of the card model.

- 🤝 **Dynamic Key-Card Socket Handover**: The blue key-card static mesh (`SM_Blue_Sector_Pass`) switches its attachment bone in exactly 1 frame. During the presentation phase, the card is attached to Brats's palm socket (`Socket_Prop_Brats_R`). The exact frame Witya's hand colliders touch the item, the system triggers a quick 1-frame brightness flash on the glowing material, instantly unlinking the card from Brats and attaching it straight into Witya's hand socket (`Socket_Prop_Witya_R`).

- 🦊 **Witya's Ear-Twitch & Tail Sweep Response**: To make Witya’s reaction to his first major tournament reward look organic and lively, his extra bones run a synchronized celebration animation. Once the card successfully attaches to his hand, his 4 dynamic foliage ears perform a rapid upward twitch animation over 4 frames to show his excitement. At the same time, his 12-segment tail does a wide, slow horizontal swing along the floor to balance his posture.

---

### 🎬 CINEMATIC SPECIFICATION: THE INDUCTION INTERVIEW (UNLAS'S HQ)

- 🏢 **Environment & models Placement**

**The Location Space**: Captain Unlas's Executive Office. The architectural layout is designed to look grand and intimidating, creating a feeling of maximum authority over the player.

**The Background Skybox**: A large panoramic window positioned directly behind Unlas's high-backed desk chair. The view outside opens onto the main planetary plaza, framing a colossal, hyper-stylized gold monument statue of Captain Unlas.

**The Executive Desk Props**: A dark, lacquered ornate wooden desk decorated with green malachite inserts and brushed gold elements. The surface layout features exactly two static props:

1. **Right Side**: A small desktop stand holding multiple micro-flags.
2. **Left Side**: Three old analog telephones in burgundy, brown and blue.

🖼️ **The Wall Galleries**

**Right Wall**: A long trophy shelving unit packed with high-gloss championship cups and military awards.

**Left Wall**: A portrait gallery featuring large oil paintings of Unlas in over-exaggerated heroic poses. Hidden among these massive frames are exactly two small, separate photographs depicting Sara Benolux and Brats Weales, framed visually like marketing products rather than employee photos.

**The Guest Stool**: Positioned away from the executive desk, sitting precisely in the absolute center of the room, is a tiny, completely bare white stool model.

---

## 🎬 2. Scripted Dialogue: Mission 1 Climax / Act I Transition

* - 🎬 **Interactive Cinematic Dialogue Sequence**

**The Context**: After Witya successfully wins the "Rangers Games," he is sent directly into the main office room for his interview. Witya enters the space, looks back toward the closed doors in hesitation, and sits down on the tiny white chair. Captain Unlas sits opposite him, leaning back in his high-backed red fabric chair.

* **Unlas:** "Congrats, potential cadet. Now, tell me... What is your lineage? What academy did you graduate from? And, most importantly... what is your budget for membership dues?"

* **Witya:** "Well... I'm fast. And tough. Pretty sure you just saw the Ranger Games."

* **Unlas:** (Looks Witya up and down) "Tough? Look at you, you're a twig. This is exactly why I should’ve been at the Games myself. Can't trust the staff to pick the right faces."

 * **System Animation Override:** [Unlas leans forward and aggressively grabs the Orange Phone].

* **Unlas: (Shouting into the receiver)** "Brats! What were you thinking by? Why did you let him straight into my office?!"

* **Witya:** "Fine. Since I'm such a twig, why don't you test my strength yourself, like Brats did?"

* **System Event Lock:** [Unlas Laughs].

* **Unlas:** "Who cares how strong you actually are? To be a hero, you gotta look like a hero!" (Flexes his massive bicep right in Witya's face).

* **Witya:** "Alright, then what is she even doing here? She definitely doesn't look 'like that.' She's got zero muscles."

 * **Sara:** "Zero muscles? What, you a sexist?"

* **Witya:** "Me, a sexist? I'm just using his logic! By his rules, you look terrible on TV!"

* **Sara: (Rolls her eyes, stepping closer)** "Oh, really? Maybe you're related to the Bennux lineage then?"

* **Witya:** "Okay, and how did _you_ even get in here?"

* **Timida:** "Fine. Since you insist on all of us bragging about ourselves... I graduated from the Presidential University of Military Shipbuilding. But, look, I am not a combatant here. My role is operational planning." _(Glances toward Unlas, lowering her voice)_ "Or at least, I try to plan. Not that anyone actually listens to me."

 * **Sara: (Checking her data-pad)** "By the way, some rather telemetry just popped up regarding his vessel. His propulsion systems are two prototypes for ultra-fast atmospheric acceleration. Accompanied by a military-grade scanning radar."

 * **Timida: (Snaps her head toward Witya, eyes wide, maintaining a strict academic and disciplined tone)** "Incredible... So, you are the un-authorized operative who dismantled my transport while I was taking a brief on Meltin?"

* **Witya:** "Why me? Am I the only mechanic in the entire Meltin’s undercity?"

* **Sara:** "Sure. Except you forgot to erase the serial numbers."

 * **Witya:** "Serial numbers... Noted..."

 * **Sara:** "He’s not even ashamed... Wait, there's another log here. _Shattered the Quantum-Time Continuum_."

* **Witya:** "Hey! I definitely did _not_ do that!"

* **Sara:** "Let's see the entry description. _'At the age of 26, arrived directly from the year 1834 with an older friend possessing white fur. Initiated an un-provoked assault on a Lucin Industries’ engineer, identifying the target as... Si-en-ce?'_"

* **Witya:** "I am 22! And I don't have any white-furred friends!"

* **Sara:** _(Smirks, closing the data-pad)_ "Fine. You didn't do it. Not yet, anyway."

* **Unlas:** "What about his family lineage?"
 
* ***Timida:** "Non-existent."

* **Unlas:** "What do you mean, non-existent?"

* **Timida:** "Completely untraceable. Even his biological species are absent from the registry. No documentation. I could potentially leverage my academic influence to authorize registration, but considering his age and the illegal circumstances, the administrative fee will strictly require no less than 50,000 bolts."

* **Witya:** "Great. And where is an unemployed mechanic from Meltin supposed to get 50,000 bolts?"

* **Timida:** "A self-built vessel... A mechanic? Actually, a skilled technician is precisely what we currently need."

* **Unlas:** "Fine. We'll organize the paperwork. We actually need a janitor and a repairman anyway—just to make sure our weapons don't jam during public matinees and look shiny at the parades!"

* **Witya:** "No way! I didn't bust my tail getting here just to swap one garage for another!"

* **System Event Lock:** _[Witya gets up from the small white stool and aggressively walks toward the exit doors]._

* **Unlas:** "Hey... hold on. What's your name anyway? No joking around, we actually fight sometimes! And hey... it's a _paid_ gig!"

* **System Visual Sequence:** _[Witya reaches the door handle, cracking it open slightly. Before he can step out, Katya swiftly slips inside the office through the narrow opening. Witya immediately stops and turns back toward the room]._

* **Witya:** "Fine. I'm staying."

* **Katya:** "More than that, Captain Unlas! We... I need your assistance! Who else but you can stop Quand Industries?!"

* **System Camera Pass:** _[Extreme close-up on Unlas's face. His heroic expression instantly drops into_ _panic]._

* **Unlas:** "You know what? I changed my mind."
* **Timida:** "What?"

* **Unlas:** _(Turning toward Timida)_ "We will find ourselves a different gunsmith. Someone with actual legal documentation and zero criminal history."

* **System Animation Override:** _[Unlas leans forward and forcefully grabs the brown Telephone unit once again]._

* **Unlas:** _(Shouting into the receiver)_ "Brats! Escort the Mechanic out. This candidate is rejected!"

---

#### 🔏 TECHNICAL & GAMEPLAY STREAMING NOTES

- ⚙️ **The Intercept Workflow**: The scene where Katya walks through the cracked door works as the main narrative hook that ties Witya into the primary story campaign. His quick change of mind ("Fine. I'm staying") must be delivered completely deadpan — instantly flipping his motivation from leaving the room in a fit of anger.

- 🎭 **The Unlas Cowardice Dynamic**: The animation team must animate a sudden facial expression shift on Unlas during his close-up shot. His transformation from a smug employer into a terrified bureaucrat the second he hears the name Quand Industries must hit with hard comedic timing, highlighting his deep fear of real combat and danger.

---

#### 🔏 TECHNICAL & HISTORICAL RE-CONSTRAINTS

- 🤝 **The Brats Comradeship Anchor**: The scenario establishes a foundational narrative anchor between Witya and Brats. Brats is explicitly coded as an eyewitness to Witya's absolute kinetic and mechanical output during the games. His decision to manually advance Witya to the executive office confirms his genuine respect for raw capability, positioning him as a legitimate ally before his future tragic encounter with the **Bitties** swarms.

- 📚 **Timida's Operational Friction Node**: The script permanently rejects any arrogant or elitist traits within Timida's profile. Her academic background is stated strictly as a passive historical metric, triggered only by Witya's defensive questioning. Her quiet remark ("Not that anyone actually listens to me") is a primary character vector establishing her immense professional frustration with Unlas's media-driven, anti-intellectual management style.

- ⏳ **The Great Breguet Scenario Protocol (Pre-Causal Log)**: The story rules regarding the 1834 historical event completely ban any "alternate dimension," "parallel reality," or "software glitch" interpretations. The game world runs on a single, continuous timeline governed strictly by **The Great Breguet**.

- 🌀 **The Consequence Precedes the Cause**: This log shows the strict rules of **The Great Breguet's** pre-programmed timeline. Because Witya and Alarein Suunt are predestined to travel back in time later in the story campaign, the historical results of that future trip have already happened and are baked into the past world history. The log tracks a completed historical event that Witya hasn't even experienced yet, acting as a fixed time-loop anchor in his present reality.

- ⏳ **The Great Breguet Protocol**: The game system enforces a single, unbroken timeline locked by **The Great Breguet**. Any scripts or story ideas involving alternate dimensions or timeline splits are completely blacklisted.

- 🦀 **The Pre-Causal Intercept**: Witya's future time-travel trip is already handled as a finished historical fact inside the current campaign database. The historical consequences appear in the world layout before Witya personally builds the time machine or activates the launch sequence.

---

#### **🗃️** MASTER GLOBAL LORE PROFILE: SKELETAL HISTORICAL RE-CONSTRAINTS

- ⏳ **Alarein Suunt Nomenclature**: His naming convention formally rejects random text assembly. The prefix Alarein acts as an intentional phonological distortion of Alathein — the ancient root of Alastor (meaning "The Unforgetting" / «Незабывающий»). This etymology sets his personality baseline: an unyielding, memory-locked commander who archives every strategic betrayal and grievance.

- 💥 **Executor of Scripts (EoS) Timeline Anchor**: In direct contrast to soft multi-verse media logs where side comedy characters handle plot strikes against faction leaders, the **Executor of Scripts** database enforces a strict rewrite rule. The physical facial fracture (**"финал/синяк"**) delivered to the main antagonist's face was executed personally and physically by **Alarein Suunt**.

- 📚 **Timida's Corporate Vocabulary**: Timida maintains her formal, disciplined vocabulary when describing bureaucratic corruption ("leverage my academic influence," "administrative fee," "strictly require"), positioning her as an elite contrast to Witya's street survivalist slang.

- 🦝 **The Theft Reveal Variable**: The dialogue officially locks Witya's criminal and opportunistic background. He did not arrive on Ceroscan through a legitimate corporate sponsorship; he literally stripped Timida's military vessel to build his own escape ship. This plot point instantly destroys any standard "boy-scout" hero trope

- 💬 **Witya's Dialogue Style**: The protagonist rejects standard heroic speech. His lines must carry a distinct, punchy "redneck-mechanic" slang rhythm. He uses short, sharp retorts and a relaxed, street-smart vocal delivery that heavily contrasts with Unlas's bloated ego.

- 🗣️ **Unlas's Speech Patterns**: Unlas's speech must remain completely basic, avoiding complex words or academic structures. He speaks in loud, sports-coach clichés and shallow corporate terms, tracking the character profile of a self-absorbed, low-intellect media puppet.

- 🎥 **Camera Positioning Rule**: During Unlas’s lines regarding the "membership dues," the camera must execute a low-angle, deep-focus tracking shot looking up from behind Witya’s tiny chair. This visual positioning maximizes the scale of Unlas’s desk and the massive background statue out the window, emphasizing the corporate wall blocking Witya’s path.

- 🎨 **Material Shader**: The texture team must apply high-bloom specular maps onto the desk's malachite and gold inserts. The three telephone units (Burgundy, Orange, and Blue) must maintain a matte plastic texture pass to contrast against the polished, lacquered dark wood surface of the table

---

### 🎥 CINEMATIC LAYOUT: THE INVASION (ACT I FINALE)

- 🚀 **The Orbit Spline Launch Vector**

**Visual Sequence**: A wide tracking shot follows Witya as he walks toward his starship with drooping foliage ears, clearly reflecting his disappointed mood.

**Katya**: And why did he change his mind the exact second he heard the name **Quand Industries**?  
**Witya**: Hit me. I found that pretty suspicious myself.

**Skeletal Animation Override**: Witya climbs inside his homemade spaceship and the cabin seals tightly. The vessel takes off sharply. The ship leaves the Ceroskan spaceport landing pad at high speed and heads straight into **Near Space**.

---

#### 🛰️ DEEP SPACE ORBIT: THE QUAND INDUSTRIES PAYLOAD

- 🌌 **Enemy Atmospheric Entry**

**Visual Sequence**: The camera shifts to a wide, cosmic skybox angle. Witya’s scrap starship drifts away from Ceroscan. Suddenly, space distorts and four **Quand Industries** corvettes emerge from hyperspace right in front of the camera.

**Technical Spec**: Each warship features a prominent forward-facing **Needle Drive Coil** (Катушка привода «Игла») on its nose cone. Upon completing their decelerating warp jump, the coils retract into the main hull armor, preparing the fleet for atmospheric entry.

**Katya** (Optical lens zooming and clicking in alarm): Witty... Those are combat vessels.  
**Witya**: Kate, look, just call me Witya then, or whatever... And... what do we care if those vessels are military?  
**Katya** (Mandible plates tensing as she drops her "Witty" nickname): Fine. Witya. We care because this is an active invasion, not a standard docking arrival!

- 🚀 **The Media-Driven Motivation Override**

**Flight Trajectory Override**: Witya aggressively slams his cockpit flight stick, forcing his scrap fighter to execute a high-velocity 180-degree turn back toward Ceroscan.

**Witya**: Attacking the galaxy cultural capital? What would make them do that?  
**Katya**: Do you think that I have the answer to that? But one thing is perfectly clear now—Tonata Rangers are not in cahoots. We should provide combat assistance.  
**Witya** (Pondering, eyes blinking): And why should we help them after all that garbage... (He thinks for a second, then a smirk appears on his face) Wait, exactly—the television! After an invasion, the cameras and news won't leave them alone for a single second! I'm putting myself in that broadcast!

**Flight Acceleration Vector**: The scrap starship back down into Ceroscan

---

#### **⚙️** NEEDLE DRIVE HULL RETRACTION PHYSICS & SKELETAL TRANSFORM

- 🚀 **Pre-Atmospheric Sequence & Animation Trigger**: As soon as the warships finish their warp-jump braking sequence, the AI manager updates the global variable (`Ship_State = Enter_Atmosphere`). This event turns off standard space drifting logic, triggering a precise 90-frame transform animation across the forward nosecone bone hierarchy to prepare the massive hull for atmospheric friction.

- ⚙️ **Linear Hydraulic Slide &Power-Down**: The main component — the high-poly Needle Drive Coil (`SM_Needle_Drive_Coil`) — must slide backward horizontally along its local X-axis. Over exactly 45 frames, heavy hydraulic piston bones compress to drag the coil structure 4.5 meters deep into the armored hull cavities. At the same time, the master material instance dims its blue warp-core glow, dropping its emissive multiplier from a blinding 15.0 down to a soft 0.5 baseline idle glow.

- 🧱 **Armored Shutter Sealing & Piston Release SFX**: On the exact final frame of the sliding animation, 4 lateral armored mechanical shutter plates (`SM_Hull_Cap_01` to `04`) snap inward to cleanly close the open nosecone slot. To emphasize the heavy industrial weight of these structures, the closure triggers a quick shockwave particle burst (Niagara vent release) at the armor joints, paired with a short screen shake effect if Witya’s cockpit camera is close enough to see it.

---

## **📥** CEROSCAN INVASION

- 🚀 **The Skybox Combat Telemetry Layout**

**Level Geometry Architecture**: The camera frames Witya's starship as it breaks through Ceroscan's atmosphere. On the main plaza below, a chaotic battle begins: Tonata Rangers are locked in a heavy ground skirmish against the **Quand Warbots** (Варботы Лучина) around the base of the massive **Unlas** monument.

**Background Level Streaming**: Positioned far up in the skybox layers are **three massive Grable Corvettes warships** (корветы Гралбов). The scene plays dynamic visual loops of landing dropships flying back and forth between the corvettes and the ground combat zone.

**Katya**: According to the radar, the Ranger headquarters has its own anti-air defense. Why is it offline?  
**Witya**: Beats me. Maybe they’re underestimating the threat. Though the situation on the ground doesn't look great. Let’s go fix that.

---

#### 🎥 CINEMATIC SEQUENCE: THE MONUMENT INTERCEPT

- 🗽 **The Target-Lock Failure Gag**

**Flight Dive Sequence**: Witya puts his ship into a steep nose-dive directly over the central plaza arena. He aims right at the middle of the battle, pressing the weapon trigger on his flight stick to open the lower missile bay.

**The Projectile Deflection**: The bay releases a single scrap rocket. Instead of tracking the enemy forces on the ground, the missile's broken tracking system locks directly onto the giant gold **Unlas monument**.

**The Structural Destruction**: The rocket explodes right against the statue's neck joints, completely blowing the head off. The pompous monument turns out to be entirely hollow inside.

**The Comedy Physics Handover**: The severed golden head drops straight down due to gravity, landing perfectly over **Unlas’s** shoulders and wedging onto his neck like an oversized helmet. The captain's character model drops his combat stance, running a panicked stagger animation loop as he frantically claws at the gold shell before successfully pulling it off.

**The Final Camera Cut**: The viewport switches instantly to Unlas’s localized first-person point-of-view (POV) layout. Having just frantically discarded the hollow gold shell from his shoulders, the furious captain stands on the plaza deck, tracking Witya’s scrap starship as it aggressively pulls out of its nose-dive trajectory and ascends back into the sky layer.

---

### **✈️** START OF THE BATTLE IN THE SKY

**Interior Cockpit Viewport**: The camera snaps back inside the starship cabin, tracking the flashing screens of Witya's messy flight instruments.

**Witya**: Whoops... Guess I didn't quite calibrate that guidance system.  
**Katya**: Those warships can deploy hundreds of Warbots. To help the ground forces, we must destroy the carrier ships themselves.  
**Witya**: And how do we do that? I don't have a weapon heavy enough to punch through their shields.

---

#### **⚙️** SEVERED HEAD RIGID-BODY PHYSICS & PROP SNAPPING

- 💥 **Model Replacement & Geometry Swap**: The exact frame Witya's rocket collider hits the statue's neck socket (`Socket_Neck_Statue`), the engine runs a mesh replacement. The single static monument model hides itself, instantly replaced by two separate objects: the static legs/torso base and the dynamic hollow head prop (`SM_Hollow_Unlas_Head`). This head model uses a custom collision shape with an empty interior space, shifting its physical center of mass realistically low near the chin.

- 🪂 **Gravity Fall & Rotation Modifiers**: As soon as the head detaches, its rigid-body physics turn on. The simulation applies a custom gravity scale (set to 1.15) along with a random rotation impulse to make the golden head roll and tumble naturally down toward the center of the metal plaza. To ensure perfect cinematic timing with Unlas's standing animation below, the air drag is locked at 0.05, keeping the heavy head from floating or drifting off course.

- 🧲 **Collision Lock & Neck Snap**: When the falling head model enters a 0.5-meter spherical trigger zone around Unlas's head bone (`Bone_Head_Unlas`), the free-falling physical simulation stops. The engine runs a quick 1-frame attachment, snapping the head model directly onto Unlas's neck bone hierarchy. The hollow head is locked straight to his neck rotation, moving perfectly along with the captain's frantic panic-stagger animations.

---

#### **⚙️** PANIC STAGGER ANIMATION CODE & PROP INTEGRATION LAYER

- 🏃 **Blind Movement & Root Motion**: The exact frame the hollow head prop snaps onto Unlas's head bone (`Bone_Head_Unlas`), the character controller disables his standard combat mode. The system starts a high-priority 90-frame panic animation layer (`Unlas_Blind_Stagger`). To visually simulate total blindness, his root motion forces him to take erratic, stuttered 0.4-meter steps along randomized diagonal paths across the metal plaza floor, bending his torso forward by 25 degrees.

- 👐 **Asymmetric Arm Movement & Pulling**: His arms (`Shoulder_L/R` to `Hand_L/R`) detach from standard weapon aiming logic. The animation runs a fast, chaotic flailing pattern over 40 frames: his left hand grabs the chin area of the golden head, while his right hand pushes against the top crown. The wrist and elbow joints vibrate heavily at a 15 Hz frequency to clearly show his physical struggle to the player's camera.

- 🧲 **Detaching the Head & Physical Launch**: At precisely frame 75 of the stagger timeline, the automatic struggle phase ends as Unlas executes a final upward thrust animation with his chest bones. The engine instantly detaches the `SM_Hollow_Unlas_Head` prop from his neck bone hierarchy, switches the head mesh back into a free physical object, and applies a fast upward push (+4.0 m/s along the Z-axis) to send the golden head rolling comically away across the plaza floor.

---

#### **⚙️** STARSHIP HORIZONTAL FLIGHT & HANDLING PHYSICS

- ✈️ **Tri-Axis Velocity & Flight Stick Controls**: During the baseline cruising phase across Ceroscan's atmosphere, the ship's movement code processes inputs via the `D-SAW` flight stick controls across three simultaneous axes: Pitch, Roll, and Yaw. The physics loop maps a custom velocity curve with a maximum horizontal cruise speed capped precisely at **32.0 m/s**, providing a comfortable and stable maneuvering baseline that lets the player easily fly around the massive meshes of the **Gable corvettes**.

- ⚖️ **Low Center-of-Mass & Radar Inertia Overlap**: The ship's skeletal setup rejects uneven lateral weights. To visually and physically show that the heavy military-grade radar stolen from **Timida** is mounted dead-center beneath the lower hull, the flight controller uses a custom pitch inertia coefficient. The ship maintains perfect horizontal roll symmetry, but its low center of mass creates a 10% resistance delay when pulling upward along the pitch axis (**кабрирование / подъем носа**) and an accelerated speed curve when diving toward the metal deck.

- 🚀 **Booster Acceleration & Dynamic Camera Drag**: Pressing the acceleration trigger `[INPUT_BOOST]` overrides the 32.0 m/s speed limit, activating secondary engine channels to rapidly scale the forward velocity up to **48.0 m/s** over a 20-frame window. At the same time, the camera component smoothly pulls backward along the local Y-axis by 1.5 meters, while the audio engine plays a loud, muffled jet engine roar to give the player a real sense of speed and raw thrust.

---

#### **⚙️** TIMIDA AURUS EXP-DRIVE & VECTOR FLIGHT HANDLING

- ✈️ **Multi-Axis Velocity & Flight Stick Controls**: During the baseline cruising phase across Ceroscan's atmosphere, the ship's movement code processes inputs via the `D-SAW` flight stick controls across three simultaneous axes: Pitch, Roll, and Yaw. The horizontal cruise speed is capped at **32.0 m/s**, serving as a stable maneuvering baseline.

- ⚙️ **Rotational Engine Platforms & Extreme Maneuverability**: The starship rejects sluggish movement. To visually and physically show the integration of **Timida Aurus's** experimental atmospheric expansion drives mounted on rotational platforms, the flight controller uses a high-velocity angular thrust override. The ship features total pitch and yaw symmetry; when pulling upward along the pitch axis (**кабрирование / подъем носа**), the engine platforms instantly rotate by 30 degrees to deliver a hyper-responsive vertical impulse, eliminating standard aerodynamic turn lag and letting **Witya** execute near-instantaneous loops.

- 🚀 **Experimental Hyper-Boost & Instantaneous FOV Warp**: Pressing the acceleration trigger `[INPUT_BOOST]` activates the experimental drive stolen from **Timida Aurus**, scaling the forward velocity from 32.0 m/s to a maximum atmospheric sprint of **55.0 m/s** over a rapid 8-frame window. This extreme acceleration curve triggers a short 2-frame camera shake and a tight field-of-view (FOV) warp stretching from 85 to 110 degrees, backed by a high-frequency ion-resonance shriek to convey the terrifying, stolen military-grade power at Witya's disposal.

---

#### **⚙️** ROTATIONAL THRUSTER VFX & DYNAMIC ION PLUME PROPERTIES

- ⚙ **Skeletal Joint Rotation & Alignment**: The two lower engine pod meshes (`SM_Exp_Engine_L/R`) must be rigged onto rotational bone joints capable of tilting up to 35 degrees along the pitch and yaw axes. When the player moves the flight stick to execute a tight turn or rapid climb (кабрирование / подъем носа), the animation blueprint must instantly sync the engine position with the steering direction, making the physical metal casings pivot on their brackets with a quick 3-frame transition delay.

- 🔮 **Ion Flame Glow & Shading**: The engine exhaust particle systems (Niagara GPU emitters) must dynamically update their shader values based on current thrust speed. At stable cruise speed (32.0 m/s), the ion flame renders as a narrow, semi-translucent cyan-blue cone. When making a sharp maneuver or holding `[INPUT_BOOST]`, the shader scales its glow brightness (emissive) multiplier to 12.0, stretching the flame geometry and changing the color to a blinding magnesium-white with purple heat-distortion edges.

- 🔥 **Exhaust Tracking & Afterburner Refraction**: As the engine platforms rotate to redirect thrust, the spawning source of the Niagara particles must perfectly track the moving nozzle sockets (`Muzzle_Thruster_L/R`). The emitter must instantly flip its direction to spray particles in the exact opposite direction of the turn. At the same time, a screen-space heat distortion ripple effect (Refraction Shader) spreads outwards around the wings to visually show the massive thermal power of the stolen military hardware.

---

### **💬** CINEMATIC DIALOGUE: THE ANTITHEFT SYSTEM (ACT II)

- 🚀 **The Shield Exploitation Briefing**

**Flight Setup Sequence**: Witya balances his ship in the air directly over the central plaza, dodging incoming anti-air tracer rounds from the fleet.

**Katya**: Their shields... They protect the warship from any fast-moving kinetic weapons. But... why are you mounting a magnet under the ship?  
**Witya** (Smirking, pulling the flight stick): Anti-theft system.  
**Katya** (Optical lenses clicking as she checks the scanner feed): According to the scans, those Warbots are highly magnetic. We could use the magnet to capture a cluster of Warbots, accelerate to maximum velocity, and release them. They would fly forward on inertia, smash directly into the defensive shield, and overload its grid with just a few impacts. Where are the controls for the magnet and acceleration?
**Witya:** Right here. **[INPUT_MAGNET]** activates the magnet, and **[INPUT_BOOST]** triggers the acceleration drive.

---

#### **⚙️** MECHANICS PROFILE: THE ANTITHEFT MAGNET-SLING LAUNCH (ACT II)

- 🛡️ **The Low-Velocity Shield Flaw & Inertial Loop**: The defensive energy shields wrapping the **Grable Corvettes** are designed to incinerate high-velocity kinetic projectiles like missiles and blaster bolts. However, they possess a critical structural flaw: absorbing a high-mass, hight-velocity mechanical impact completely shorts out their energy system.

- ✈️ **The Input Layout Handover:** Immediately following the dialogue, full steering and flight physics control (`D-SAW`) is released to the player. Witya must actively dogfight through the plaza air layer using a strict gameplay loop:

1. Approach the dense infantry ground skirmish.
2. Press and hold `[INPUT_MAGNET]` to project a conical magnetic tractor beam, instantly snapping a cluster of Warbots beneath the ship's center hull armor.
3. Engage `[INPUT_BOOST]` to activate the experimental drives, accelerating the combined mass toward a targeted **Grable Corvette** mesh.
4. Release `[INPUT_MAGNET]` at the peak of the acceleration curve to hurl the Warbots along a fast inertial trajectory directly into the shield system, before pulling up sharply to avoid crashing.

⚙️ **Acceleration Requirement**: The damage system strictly checks the ship's current speed. To successfully launch captured Warbots forward, Witya's custom ship must be in the active boost phase (`[INPUT_BOOST]`). If the player attempts to release them below this speed threshold, the robots will not damage the corvettes' energy shields.

---

#### **🛸** CORVETTE TURRET DIFFICULTY SCALING

- 🎛️ **The Turret Fire Rate Difficulty Scaling**: The heavy automated defense turrets mounted across the hulls of the **Grable Corvettes**, scale their targeting speed and firing behavior to match the global difficulty variable:
    - **Minimum Difficulty**: The corvette’s main anti-air blaster turrets are completely disabled (`Weapon_Active = FALSE`). The capital ships work strictly as passive obstacles on the level, letting the player safely gather Warbots without taking damage.
    - **Medium and Higher Difficulty Tiers**: The turret defense system is fully active. The corwettes actively track Witya’s starship, firing dense walls of defensive flak projectiles that the player must actively evade using quick **Flight_Dash_Steps** while holding their acceleration curve.

---

#### **📊** CORVETTE DESTRUCTION PROGRESSION

- 📊 **The Hit Requirements per Target**: To destroy a single **Lucin Corvette**, the player must score a precise number of hits using captured **Warbot clusters** ("порции") depending on the active game difficulty:
    - **Low Difficulty**: Requires exactly **1 Cluster** to drop the energy shield + **1 Cluster** slammed directly into the exposed hull plates. (Total: **2 clusters**).
    - **Medium Difficulty**: Requires exactly **1 Cluster** to drop the energy shield + **2 Clusters** slammed consecutively into the exposed hull plates. (Total: **3 clusters**).
    - **Legend & Plausible Tiers**: Requires exactly **2 Clusters** to break the reinforced energy shield + **2 Clusters** slammed directly into the exposed hull plates to blow up the ship. (Total: **4 clusters**).

---

#### **⚙️** MOMENTUM-RELEASE THROW PHYSICS & VELOCITY SCALING

- 🚀 **Instantaneous Launch Impulse Calculation**: At the exact frame where player input registers a valid release condition (`[INPUT_BOOST] = TRUE` AND `[INPUT_MAGNET] = RELEASE`), the physics script reads the starship's current velocity vector along the forward flight line. The system breaks the magnetic link beneath the hull armor, bundles the captured Warbots into a singular rigid-body cluster object (`BP_Warbot_Payload`), and applies a starting speed equal to the ship's current speed.

- 📐 **Hyper-Boost Gating & Perfect Ballistic Alignment**: If the launch command is executed precisely at the peak velocity of the experimental drives (**45-55.0 m/s**), the projectile object enters its optimal ballistic phase. The forward launch vector is perfectly aligned with the ship's nosecone target coordinates, maintaining a flat, zero-gravity trajectory line for the first **1.5 seconds** of flight. This linear stability lets the player safely snipe the defense shields of the **Grable corvettes** from a safe distance before breaking away.

- 🪂 **Sub-Threshold Velocity Drop**: If the player attempts to bypass the maximum acceleration curve and triggers the release loop at a mid-boost velocity threshold (clamped between **32.0 m/s and 45.0 m/s**), the projectile script applies a severe aerodynamic drag penalty. The starting speed of the flung Warbot cluster is cut instantly by **40%**, and a heavy gravity scale (set to **2.5**) is applied to the object. The payload curves downward prematurely, missing the corvette hull.

---

#### **⚙️** ENEMY PROFILE: YK-7 HYDROFIGHTER

- 📐 **Fuselage Design & Industrial Metal Aesthetics**: The fighter mesh (`SM_YK7_Hydrofighter`) uses a compact, twin-engine aerodynamic frame with a low nosecone. In strict alignment with the **Quand Industries** (Завод Лучина) branding design guides, the wing panels and stabilization flaps must completely reject curved organic modeling styles or hexagonal patterns. The layout enforces flat geometric plates covered in sharp, longitudinal panel lines and a matte charcoal-grey coating with burgundy warning stripes.

- 🔫 **Water-Blaster Turrets & Muzzle Sockets**: Positioned underneath the wing roots are two independent dual-barrel water blaster modules (`Socket_YK7_Blaster_L/R`). These hard-surface models feature visible hydraulic cooling lines and rotating cylinder magazines. When the AI controller triggers an attack run against Witya's starship on Medium or High difficulty, the muzzle tips fire sequential pressurized blue tracers, backed by a quick 3-frame neon-green muzzle flash particle burst.

- 🔥 **Afterburner Vent Layout & Heat Distortion VFX**: The rear section of the hydrofighter houses dual rectangular thrust exhaust chambers (`Muzzle_YK7_Exhaust_01/02`). The interior geometry uses a glowing orange material shader to simulate continuous ion combustion. During high-velocity evasive maneuvers, these exhaust nodes stream long, tightly pinched heat distortion lines (Refraction tracks) across the screen, letting the player easily track and target the enemy fighter by its tail trail.

---

#### **⚙️** AUDIO DESIGN & HYDROFIGHTER FLY-BY SFX PROPERTIES

- 🔊 **Three-Layer Engine Sound Mix**: The continuous engine sound for the YK-7 Hydrofighter combines exactly three distinct audio layers: a low-frequency heavy metallic turbine growl (set to 120 Hz to emphasize the ship's massive weight), a mid-range synthetic screaming engine whine, and a sharp, high-priority hiss that simulates pressurized fluid shooting through the lateral thruster ports.

- 🏎️ **Dynamic Doppler Effect Transformation**: When an enemy fighter flies past at high speed and enters a 15-meter sphere around the gameplay camera, the audio engine must apply a sharp Doppler effect. The system automatically bends the engine pitch upward as the ship approaches (scaling from a 1.0 multiplier up to 1.4), then drops the pitch instantly down to 0.75 the exact frame the ship passes the camera view.

- 🎧 **3D Spatial Panning & Crossfade Decay**: To help the player track enemies by ear, the fly-by audio loop must continuously follow the enemy's velocity vectors relative to the listener position. The system runs a 3D audio panning script that rapidly shifts the sound from left to right (or rear to front channels) within a tight 15-frame window during close fly-bys, fading out into a deep, bass-heavy echo over 2.0 seconds to simulate real atmospheric displacement.


---

#### **⚙️** CORVETTE ANTI-AIR TURRET TRACKING AI & LEAD CALCULATION

- 🎯 **Dynamic Velocity Lead Calculation**: When playing on Medium difficulty or higher (`Difficulty >= Medium`), each active corvette turret turns on its predictive aiming script. The weapon system stops tracking Witya’s current position coordinates. Instead, the AI reads the starship's real-time velocity and heading vectors over a rolling 15-frame window to calculate a predicted intercept point (`Target_Predictive_Vector`). This is where the dense stream of shells will fly.

- ⚙️ **Rotational Speed Limits & Dodge Windows**: To prevent the heavy defense turrets from snapping instantly onto the player's position — which would create unavoidable instant hits — the physical tracking gears have a strict rotational speed limit along the pitch and yaw axes. The turn speed is clamped at a maximum of **35 degrees per second**. This intentional delay lets the player outrun the turret’s line of sight and create temporary safe openings by using sudden **Flight_Dash_Steps** on the experimental engines.

- 🤝 **Coordinated Crossfire Array (Legend / Plausible)**: When operating on the **Legend** or **Plausible (Realism)** difficulty settings, individual turrets on a single corvette hull stop shooting independently and switch to a synchronized network loop. The main ship manager script coordinates exactly three adjacent turrets, forcing them to spread their `Target_Predictive_Vector` targets in a tight triangular layout around Witya's ship: one turret targets his nosecone directly, while the other two seal off his left and right escape flanks, locking the player into a dangerous tactical crossfire zone.

---

#### **⚙️** CAPITAL WARSHIP DESTRUCTION VFX & PHYSICS CASCADING BREAKDOWN

- - 💥 **Primary Structural Rupture & Internal Explosions**: At the exact frame where the final required Warbot cluster hits the exposed hull armor, the ship updates its blueprint state to `BP_Corvette_Dead`. The engine triggers a sequential loop of 12 internal explosion points rolling from the main engines down to the nose cone coordinates over 90 frames, spawning massive volumetric fireball effects (Niagara GPU particles) that physically tear and distort the outer steel plates.

- 📦 **Hull Fracturing & Debris Shedding**: The corvette model switches to a pre-fractured Chaos Physics layout. During this explosion phase, the master blueprint dynamically detaches exactly 15 to 20 large chunks (wing tips, armored panels, weapon turret housings) and converts them into free-falling rigid-body physics objects. These chunks fall along a high-gravity arc (gravity scale = 1.3), completely ignoring collision checks with Witya's starship to prevent accidental player death.

- 🌪 **Downward Crash Trajectory & Level Evacuation**: The burning wreck cannot instantly disappear from the level. The ship's movement script applies a slow 6-degree downward pitch angle, forcing a sluggish, smoky downward flight path that simulates total loss of engine thrust. The mesh continuously trails thick black smoke and orange spark paths across the screen before dropping beneath the lower cloud layer, where the ship is permanently deleted from memory to optimize performance and save GPU resources.

---

#### **⚙️** AMMUNITION LOOT

- 🛸 **The LCVP-84 Hovercraft Intercept Loop**: While hunting the primary corvette structures, the player can engage and eliminate lower-tier enemy **LCVP-84 Hovercraft** (Десантники ДЛСИТ-84 / Dropships). Depleting their health bar triggers an immediate explosion. The destroyed vessel drops a high-priority ammo loot crate that replenishes rockets for Witya's secondary missile bay, supplementing the built-in **Autocannons** (Автопушки) of the home-built starship.

---

### **💬** IN-GAME DIALOGUE: THE PERIMETER CLEARANCE

- 💬 **The Landing Zone Radio Communication**: Immediately following the destruction of all three **Grable Corvettes**, the mission updates to a completion state, triggering a localized real-time cockpit dialogue:

**Witya**: Skies are clear. Let me guess, landing directly next to the monument is prohibited?  
**Katya**: Affirmative. I have marked a safe landing position on your HUD.

- ⚓ **The Flight-to-Deck Navigation Task**: Control remains fully active. The player must steer the starship nose toward the designated landing marker and fly forward into the landing zone. Triggering the touchdown trigger locks player inputs and smoothly transitions into the next cinematic cutscene.

---

### **🎥** CINEMATIC: THE CASSETTE DECK INTEGRATION

- 🎒 **The Back-Harness Attachment**

**Visual Transition Cut**: Witya climbs out of his ship's cockpit. Katya folds compactly into a "toaster" shape and clicks into the magnetic socket (clamp) on his back. Witya calmly descends from the fighter onto the square, ignoring any unnecessary pirouettes or jumps.

Witya reaches into pocket, retrieving the flat, glowing neon-blue card (The Sector Pass). Without turning his head, he extends his right hand backward over his shoulder:

**Witya**: Do me a favor and hold onto this inside you, just so it doesn't drop out of my pocket during a fight.

- 📼 **The Cassette Deck opening**

**Visual Sequence**: Katya reaches forward and takes the pass. Her central display smoothly flips outward and down at a 45-degree angle, transforming into an authentic **cassette player**.

Katya inserts the flat card smoothly inside the internal slot. The screen door snaps shut with a crisp pneumatic mechanical latch chime.

- 📻 **The Rangers Radio Intercept**

**Visual Sequence**: Witya begins walking toward the main facility gate threshold. Suddenly, Katya’s optical lenses zoom and contract, and her speaker emits a low-amplitude radio static interference overlay, synced to the internal frequency of the Tonata Rangers encryption system:

**Katya**: It appears this access card unlocks more than doorways. I am intercepting the Tonata Rangers' internal radio transmission.  
**Witya** (Ears perking up, clicking his gloves): Excellent. Put it on speaker.

---

#### **⚙️** SCREEN SLOT SKELETAL RIGGING & KEY-CARD INSERTION LOGIC

- ⚙ **Dual-Axis Hinge Skeletal Rigging**: The robot sidekick central torso skeletal mesh (`SK_Katya_Body`) must include a mechanical hinge joint labeled `Bone_Screen_Hinge`. Upon triggering the 30-frame keycard sequence, the joint rotates downward precisely 45 degrees along the local Pitch axis while simultaneously sliding forward by 12 mm along the local X-axis, creating a realistic mechanical gap that mimics a spring-loaded analogue cassette pocket opening.

- 🔮 **Interior Slot Rendering & Optimization**: The interior layout behind the display panel houses a low-polygon hollow chamber detailed with electrical contact pin static meshes (`SM_Card_Pins_Reader`). To maximize optimization, the interior texture maps use a strict opacity mask: while the screen state is Closed, the cavity mesh is completely hidden; when the opening animation reaches a 0.5 interpolation value, the system dynamically toggles visibility to reveal the slot just before Witya inserts the pass card.

- 🧲 **Card Snapping & Mechanical Latch Clamp**: When the blue key-card prop mesh (`SM_Blue_Sector_Pass`) enters a 0.02-meter trigger zone relative to the slot center, the animation blueprint initiates the clamp script. The card position snaps instantly onto the reader socket coordinates, while the hinge bone reverses its pitch rotation over exactly 10 frames. To provide satisfying physical feedback, the last frame of the closure timeline triggers a quick 2-frame micro-vibration jitter on the display mesh, paired with a crisp mechanical latch sound effect to confirm the keycard integration.

---

### **💬** WIRELESS INTERCEPT (ACT III START)

- 📻 **The Radio Channel Connection**

**Visual Sequence**: The speakers on Katya's chassis emit a sharp burst of radio static before clearing into the tactical audio channel of the Tonata Rangers.

**Brats**: Whew... Seriously, how many more of them are out there? I’ve had my hands full with those applicants, and now we still have to clean up the city sectors.  
**Witya**: What's the matter, Brats? Did one of those applicants squeeze all the juice out of you?  
**Brats**: Yeah... Wait! What? Who is this?  
**Witya**: Witya. How are you holding up down there?  
**Brats**: Oh, forgot to take back my card... Well, it’s definitely a lot easier without those corvettes overhead. That was brilliant. You know, aside from the fact that you dropped them directly onto the city.  
**Witya**: Not my bad. Should I have just stood by and let them overwhelm you and occupy the whole city?

**Visual Sequence**: A brief, tense silence runs across the radio transmission channel.

**Witya**: I can assist with clearing the city blocks.  
**Brats**: Excellent. If you want to link up with our forces, the shortest route lies through the Botanical Garden and the Warehouse. If any security gates lock you out, just flash my pass card.

- 🚨 **The Unlas Audio Intercept**

**Visual Sequence**: Suddenly, a loud static beep cuts into the sub-frequency. Unlas’s pompous voice floods the channel:

**Unlas**: Brats! Who are you talking to over there?  
**Brats** (Instantly changing his tone to a casual grunt): No one, Captain. Just... thinking out loud.

---

### **📥** APPROACHING THE BOTANICAL GARDEN (ACT III)

- 📻 **The Background Radio Narrative**

**System Function Loop**: While the player has full control over Witya's movement and combat, the audio manager plays a series of comedic background radio logs to expand the sector's world-building:

- **Log 01 (The Infiltrator Threat)**: Ranger field units panic over a heavy new enemy — the **Warbot Tolerater** (Варбот-Впитыватель) — whose heavy armor entirely ignores their standard blaster fire.
- **Log 02 (The Captain's Blunder)**: Unlas attempts to attack a **Warbot Tolerater** with a hand-to-hand melee punch, resulting in an immediate audio clip of him groaning in pain.
- **Log 03 (The Culinary Dispute)**: A casual argument on the tactical sub-channel between Brats and Timida debating the culinary superiority of **Carniherring** (Плотоядная селёдка) versus **Fugu Shark** (Акула Фугу).

---

#### **🤖** THE STREET ENEMY COMPILATION

- 🧱 **The Anti-Spam Encounter Constraints**

**Sector Topology Note**: To prevent messy screen clutter, the street arenas maintain a low enemy density. Instead of spamming the player with copies of the same mob, combat setups rely on mixing distinct enemy archetypes.

- 🕷️ **Enemy 01: Walkermines (Гуляющие мины)**
	**Operational Blueprint**: Low-profile, fast-scuttling mobile landmines. Upon detecting the player, they run an aggressive chase loop straight toward Witya. On lower difficulties, they trigger a loud beeping timer just before detonating. On higher difficulties, they explode immediately if they get close enough to Witya.

- 🤖 **Enemy 02: Warbot Shooters (Варботы-Застрельщики)**
	**Operational Blueprint**: Standard enemy infantry units. They position themselves behind cover or on vantage points, firing continuous bullet streams to pin down the player from medium range.

- 💣 **Enemy 03: Warbot Catapulters (Варботы-Швырятели)**
	**Operational Blueprint**: They occupy supporting combat positions, continuously lobbing short-range explosive grenades to force Witya to keep moving and leave his cover.

---

#### **⚙️** WALKERMINE AI TRACKING BLUEPRINT & TERMINAL DETONATION LOGIC

- ⚙ **Target Detection & Chase Trajectory**: When Witya’s character collider enters a 12-meter radius proximity zone, the Walkermine’s AI controller switches from its static `Patrol_Idle` state to `Target_Chase`. The movement logic overrides standard linear pathfinding, forcing the mechanical chassis to move in a tight zigzag trajectory towards Witya's position. The movement speed handles sharp acceleration spikes up to 9.5 m/s, making the mine look frantically fast and unstable.

- 🚨 **Proximity Lock & Explosion Countdown**: When the distance between the Walkermine and Witya shrinks to a tight 1.5-meter threshold boundary, the chase state instantly ends, locking the mine's position in a fixed spot. The system starts a high-priority 24-frame countdown sequence (`Explode_Telegraph`). During this brief window, the mine's built-in light flashes from stable amber to high-frequency crimson at 60 Hz, accompanied by a rapid pneumatic overheating hiss to provide an urgent audio cue to the player.

- 💥 **Explosion Radius & Jump Evasion**: At exactly frame 25 of the countdown, the telegraph phase closes and the system executes the `Trigger_Blast` function. The mine spawns a spherical damage trigger zone with a 3.0-meter radius, dealing a fixed 22% damage to Witya's health bar and applying a steep push impulse to Witya.

---

### **🌿** THE PARKING CORRIDOR PLAZA

- 🌿 **The Flora-Infested Urban Environment**

**Level Design Layout**: The Botanical Garden's escaped ecosystems merge directly into the parking zone. The path integrates environmental hazards and hidden point-of-interest (POI) nodes.

- **Environmental Hazard: Carnivorous Plants (Плотоядные растения)**: Static foliage meshes with rapid biting collision triggers. Intersecting their proximity boxes triggers an instant physical snap attack, dealing minor damage to Witya's health.
- **Hidden Economy Node: Hofitum Crystals (Кристаллы Хофитума)**: Tucked into an obscured corner flowerbed is a cluster of high-value Hofitum Crystals, rewarding curious players who break away from the linear main path.

---

#### **⚙️** BOTANICAL GARDEN VISUAL STYLE & SHADER COMPILATION

- - 🌿 **Sub-Surface Scattering & Bio-Luminescent Core**: The foliage material master template (`M_Botanical_Foliage_Master`) must completely reject standard flat diffuse textures. The material requires an advanced Sub-Surface Scattering (SSS) profile to simulate light penetrating translucent alien plant leaves. The primary color spectrum maps to high-saturation violet, deep fuchsia, and teal-cyan hues. Additionally, the veins of the plants run a slow, rhythmic neon emissive pulsing animation set to a smooth 0.5 Hz frequency, creating a living, breathing ecosystem that physically projects light onto Witya's fur and leather straps.

- 🍃 **Wind Turbulence & Foliage Interaction**: To convey that the urban jungle is dense and volatile, all tree-crown, vine, and flower meshes must utilize world position offsets driven by Pivot Painter 2.0. The material runs a localized noise modifier simulating intense atmospheric wind vectors. Concurrently, when Witya’s 1.5-meter character collider or his 12-segment tail intersects a foliage mesh bounding box, the material must execute a rapid procedural vertex deflection away from his movement center, forcing the giant alien ferns and leaves to realistically brush aside and wobble back into alignment as he sprints past.

- 💎 **Hofitum Node Shaders & Screen-Space Refraction**: The high-value Hofitum Crystals (Кристаллы Хофитума) hidden in the garden terrace layers require a highly distinct mineral material profile. The shader instance must enforce a sharp, multi-faceted geometry layout with an ultra-low roughness value (0.02) and a non-linear Screen-Space Refraction (SSR) index. The internal core must apply a dual-color chromatic aberration filter that shifts its internal sparkle from piercing emerald-green to sharp amber based on the camera view angle, making the secret points-of-interest (POI) instantly pop against the organic dark-violet moss backdrop.

---

#### **⚙️** CARNIVOROUS PLANT COMBAT LOGIC & SNAP TRIGGER LOGIC

- 🌿 **Detection Radius & Idle State**: The carnivorous plant (`BP_Carnivorous_Plant`) must include an invisible spherical collision trigger (`Col_Detection_Sphere`) with a fixed radius of 1.8 meters. While Witya remains outside this boundary, the skeletal mesh runs a low-frequency breathing animation loop (`Plant_Idle_Loop`), forcing its jaw-like petals to slowly undulate and pulsate with an inviting neon-teal glow.

- 💥 **Bite Attack & Hit Detection**: The exact frame Witya’s 1.5-meter character collider enters the detection trigger, the plant instantly drops its idle state to start a high-velocity attack animation (`Plant_Snap_Bite`). The jaw bone components (`Bone_Jaw_Upper/Lower`) close completely along the pitch axis within a tight 5-frame execution window. If Witya is still inside the mouth bounds during the final frame, the collision check registers a hit, dealing a fixed 10% damage.

- 🏃‍♂️ **Knockback Impulse & Recovery Window**: To prevent the player from getting stuck inside the plant’s geometry, a successful bite attack must immediately execute a directional physics push. The logic calculates the direction vector between the plant’s center and Witya's position, applying a horizontal launch impulse (+8.0 m/s) that throws Witya backward onto a safe platform. This knockback forces a brief 10-frame landing recovery animation, giving the player a clear window to regroup and move around the hazard.

---

#### **🛠️** THE CYLINDRICAL GROUND SLAM TUTORIAL

- 💥 **The Explosive Crate Blacklist & Gismotron Advice (Вещетрон)**

**Level Geometry Constraint**: Game design completely bans traditional red explosive barrels or crates. When Witya approaches a dense pile of standard, destructible **Bolt Crates**, the **Gismotron Assistant** activates a voice prompt:

**Gismotron Assistant:** To quickly break a large group of crates, press [INPUT_JUMP] and press [INPUT_FIRE] while jumping.

**The Ground Slam Hitbox Logic**: The instruction coaches the player to execute a Jump-Attack combination to activate the Ground Slam (`Abil_Ground_slam`). Upon landing Witya's long legs onto the platform, the combat system spawns a cylindrical shockwave trigger zone stretching outward along a fixed radius and extending upward along a 1.5-meter vertical Z-axis. This simple cylinder shape ensures that all breakable boxes and low-tier enemies inside the radius receive equal damage regardless of any uneven ground or slope offsets.

---

#### **⚙️** CYLINDRICAL GROUND SLAM PHYSICS & SHOCKWAVE HITBOX

- 🏃 **Airborne Input & Descent Vector**: When the player registers a valid `[INPUT_MELEE]` command while Witya is at the peak of his vertical jump (`Airborne_Phase`), the system overrides standard physics values. The player's horizontal steering authority (D-SAW X/Y movement) is instantly dampened by 90% to lock his landing position, while an aggressive downward velocity force vector (+18.0 m/s along the Z-axis) is applied to plunge Witya straight onto the deck.

- 💥 **Wrench Impact & Cylinder Spawning**: The exact frame where the collision box of the VersaWrench registers a `Surface_Hit` event against the asphalt floor, the downward velocity component is zeroed out. The system triggers a 15-frame deceleration impact animation (`Heel_Strike_Land`) showing Witya slamming the weapon into the ground, and instantly spawns a dynamic Cylindrical Shockwave Volume (`Col_Slam_cylinder`) centered precisely at the impact coordinates.

- 📐 **Hitbox Limits & Slope Compensation**: To bypass standard sphere-trace collision bugs on uneven steps and garden terrace slopes, the shockwave hitbox limits are hard-clamped to a 3.5-meter radial expansion boundary along the horizontal plane and an absolute 1.5-meter vertical height ceiling along the Z-axis (extending equally 0.75m above and 0.75m below the exact contact plane vector). Any breakable Bolt Crates, Walkermines, or low-tier Warbots caught inside this spatial cylinder volume receive uniform damage, executing a forced physics knockback trajectory away from Witya.

---

#### **⚙️** UI/UX SCREEN ARCHITECTURE: WEAPON UPGRADE

- 💳 **The Ranger License Validation**: When Witya interacts with any distributed ST-07 vendor terminal while holding the sector pass, the **Gismotron Assistant** bypasses standard civilian restrictions. The terminal updates its clearance level, initializing an automated greeting dialogue:

**Gismotron Assistant**: Ranger license detected. Greetings, Brats Weales.  
**Witya** (Ears twitching in surprise): Whoa, this card even packs a license...

The terminal database instantly unlocks the secondary operational tabs: **Ammunition & weapon Purchases** and the **Weapon Upgrades Screen**.

**First Purchased Weapon:** Witya gains access to his first weapon: the Cadet Blaster. Despite its name, it fires standard bullets at medium range and a medium rate of fire. It's free. When the player hovers over it and clicks, a small ad appears:

**Terminal:** Brats, are you gripping your blaster too tightly again? Unfortunately, the standard terminal can only issue the Cadet Blaster. Contact the Armory at Headquarters for a full replacement
Moreover, in this advertisement, the model of Brats Weales will be used because of this card, while in all subsequent ones, Witya will appear.

---

### 🛒 UI/UX SCREEN ARCHITECTURE: THREE-PANEL SHOP LAYOUT

- 🖥️ **The Shop Interface Initialization**: Interacting with the ST-07 vendor terminal opens the main store menu screen (`W_Terminal_Shop_Canvas`). The UI setup splits the screen into a synchronized, three-panel vertical layout wrapped in flat trapezoidal frames to match the industrial branding rules.

- 📋 **Panel 01: The Left Navigation List (Primary Navigation)**: Renders a static vertical list containing all items available for purchase:
    - **Top Default Row**: Hard-coded as **"Full Ammo & Health"** (Полное восполнение боеприпасов и здоровья). The menu cursor permanently highlights this option every time the terminal opens.
    - **Weapon Selection Rows**: All subsequent lower rows list the weapons, displaying each item's title alongside its precise **Bolt** (Болты) cost counter.

- 📺 **Panel 02: The Center Preview Screen (Dynamic Media View)**: Occupies the middle sector of the layout. This window activates exclusively when the player highlights an locked or unpurchased weapon row on the left list. The UI engine runs a localized, stylized advertising commercial video broadcasted directly by the corporate weapon manufacturer.

- 🔧 **Panel 03: The Right Technical Inventory Box (Dynamic Info View)**: Occupies the rightmost side of the screen:
    - **Owned Weapon Listing**: Displays a clean vertical grid tracking all unlocked firearms currently held inside Witya's inventory.
    - **Upgrade Trigger Pass**: Pressing the confirmation key while highlighting an already owned weapon instantly opens a specialized sub-menu to purchase specific ammunition packs or display the stats upgrade.

- 🔘 **Cursor Hover & Purchase Execution States**: Moving the menu selection box over any item row triggers an `onHover` event over 10 frames: the row plate switches from dark charcoal to a sharp neon-blue gloss, while sliding open the detailed weapon stats cards. Pressing the validation key runs a currency check script: if Witya has enough Bolts, the engine deducts the price, plays a crisp mechanical cash-register chime sound, and increments his ammo pool until it reaches its maximum capacity limit.

---

### **🖥️** GRID TOPOLOGY & SCREEN COMPOSITION: THE BLUEPRINT INTERFACE

- 📐 **The Vector Blueprint Aesthetic**: The upgrade menu completely rejects heavy raster textures, enforcing a clean neon wireframe style.

- 📋 **The Left Segment Array**: Displays a vertical list tracking all firearms currently unlocked inside Witya's active inventory slots.

- 🎯 **The Center Focal Anchor**: Displays the highlighted weapon icon drawn in clean vector lines that match the physical contours of the gun model. This icon sits perfectly centered within a flat grid boundary holding exactly eight upgrade slots.

- 🔫 **Weapon Classification Layout Constraints**: The screen position of the eight upgrade slots dynamically changes based on how Witya holds the selected weapon:
    1. **One-Handed Weapon (Одноручное)**: The eight upgrade slots split evenly, positioning four slots to the Left and four slots to the Right of the central weapon icon.
    2. **Two-Handed Weapon (Двуручное)**: The eight slots rotate their placement, positioning four slots Directly Above and four slots Directly Below the central weapon icon.

---

#### ⚙️The Active Slot Constraints & Technical Callout Lines

- 🛑 **The Non-Linear Progression Clamp**: Every single upgrade within the weapon progression tree must eventually be purchased. To allow players to buy upgrades out of order, the menu interface displays up to 8 progression rows on the screen. However, the system enforces a strict interface constraint: **no more than 5 progression rows can be active simultaneously on the layout**. This number dynamically scales down to 4, 3, 2, or 1 depending on how many unpurchased upgrades are left in that weapon's tree.

- 📐 **Procedural Blueprint Leader Lines**: Each active upgrade slot connects directly to a specific mechanical component of the weapon design (such as the barrel, battery, or grip) via a thin technical leader line. The line’s end-point coordinates can be explicitly hard-coded or generated procedurally across the mesh surfaces to look like an active assembly blueprint schematic.

---

#### SCREEN COMPOSITION: DYNAMIC WINDOW OVERRIDE LOGIC

- 🔄 **The Sequential Window Refresh Script**: The menu layout eliminates repetitive, single-spot click loops. The moment player validation confirms a purchase on any of the 5 active rows, the system executes an instant interface update over 1 frame:
    - **The Stale Node Fade**: The purchased row immediately dims its vector glow, shifts its state configuration to `Purchased_Inactive`, and locks out further inputs.
    - **The Next Node Ignition**: The interface blueprint drops that row from the active 5-slot ceiling, instantly activating a new unpurchased row linked to a completely different component socket on the opposite side of the weapon blueprint. This ensures a dynamic, scattering visual progression across the entire screen layout.

---

#### **⚙️** VECTOR WIREFRAME SHADER & BLUEPRINT CANVAS UI

- 📐 **Real-Time Outline Filter**: The weapon preview window inside the UI menu rejects heavy pre-rendered textures. Instead, the shader applies a procedural Sobel filter directly to the 3D model. It strips away all lighting, shadows, and textures, scanning the geometry to generate clean, single-pixel vector stroke lines outlining every internal component of the gun.

- 💡 **Neon Cyan Material Glowing**: The vector stroke lines use a glowing translucent material locked to a strict cyan color map (Hex: **00E5FF**) to deliver a high-contrast neon tech glow. The brightness is clamped at a steady 2.5 value. This ceiling ensures crisp scannability against the dark-grey background, entirely preventing light blur from washing out sharp technical details like the inner barrel or battery housings.

- 🎯 **Line Anti-Aliasing & Thickness Locking**: To eliminate visual shimmering or jagged edges when scaling or switching weapon models inside the layout, the vector lines run a clean anti-aliasing script. The line thickness variable is dynamically locked to exactly 1.5 screen pixels, maintaining uniform, razor-sharp technical visibility across all monitor resolutions from 1080p up to 4K displays.

---

#### **⚙️** PROCEDURAL LINE ATTACHMENT ALGORITHM & ANCHOR TRACKING

- 📐 **Component-Bound Node Socket Assignment**: The vector wireframe mesh of each weapon includes exactly eight pre-defined structural vertex zones bound to its mechanical components (such as `Muzzle_Zone`, `Barrel_Zone`, `Battery_Zone`, and `Grip_Zone`). When opening the upgrade screen, the engine reads these 3D socket coordinates and projects them onto the 2D interface screen via the `Project_World_To_Screen` node, creating precise target coordinates for the leader lines.

- 🎯 **Offset Randomization & Line Intersection Check**: To make the schematic layout look natural rather than stiff, the attachment point within each component zone runs a subtle random offset check. The algorithm selects a random valid vertex on the model's surface within a **0.15-meter radius** around the main component socket. Concurrently, the system runs a geometric trace check to ensure that no two lines cross each other's paths on the screen, completely avoiding intersection visual bugs.

- 📈 **Dynamic Line-Trace Interpolation & Anchor Locking**: The exact frame an upgrade window switches to the active state, the system spawns a 2D line render element. The screen-space line coordinates start at the edge of the active UI slot and draw smoothly toward the calculated weapon component anchor over exactly **12 frames** using a `Line_Draw_EaseOut` interpolation curve. Once connected, the line locks its tip directly to the tracking anchor node, moving perfectly along with any scaling or rotation adjustments of the central weapon model.

---

#### **⚙️** TERMINAL AMMO PURCHASE AUDIO DESIGN & INTERACTIVE UI SFX

- 🔊 **Cursor Hover SFX**: Moving the menu cursor across the vertical ammo rows triggers a short menu navigation sound (`SFX_ST07_Menu_Hover`). The source wave file is a clean, 0.05-second electronic click layered with a soft sine-wave chime capped at 2200 Hz. This design delivers a sharp, non-fatiguing auditory confirmation of cursor movement that cleanly cuts through background combat loops.

- 💰 **Purchase Confirmation Currency Drain**: The exact frame the player presses the purchase input and passes the coin check, the engine triggers the main transaction sound block (`SFX_ST07_Purchase_Success`). This audio track combines a retro-industrial fast mechanical gear spin, a digital cash-register chime, and a quick electronic zap to clearly communicate the deduction of Bolts from Witya's wallet balance.

- 📦 **Pneumatic Dispenser Box Drop SFX**: Immediately following the purchase chime, a heavy, spatialized physical sound executes directly from the terminal (`SFX_ST07_Dispense_Chamber`). The sound design layers a sharp pneumatic valve pressure release hiss with a heavy, metallic locking thud capped at 150 Hz. This simulates the terminal's heavy internal iron trays physically dropping the fresh ammunition pack or energy cell down into the lower retrieval slot.

---

### **📥** WEAPON UPGRADE CLASSIFICATION

- 📊 **The Two-Tier Functional Upgrade

The database divides all eight display windows within the weapon upgrade layout into exactly two functional tier groups, each regulated by its respective economy:

 **🟢Green Upgrades (Standard Tier)**

- **Cost & Economy**: Purchased exclusively by spending standard **Hofitum Crystals** (Кристаллы Хофитума).
- **Gameplay Adjustments**: Provides minor incremental increases to weapon stats, such as slight weak-point damage bonuses, basic recoil dampening, or minor fire-rate adjustments. This resource is distributed widely across all level paths to reward standard exploration.

 **🟡 Gold Upgrades (Premium Tier)**

- **Cost & Economy**: Purchased exclusively by spending extremely rare **Nirgenium shards** (Осколки Ниргениума), strictly requiring exactly **1 shard** per premium upgrade slot.
- **Gameplay Adjustments**: Activates massive, foundational changes to the weapon's behavior, such as a large overall damage boost, major fire-rate scaling upgrades, or unlocking completely unique alternative firing modes.

---

### 🔊 INTERACTIVE TUTORIAL: THE STEP-BY-STEP FLOW

- 📋 **First-Contact Interface Training Loop**

Upon triggering the active interaction node with the shop terminal, the store menu screen opens. The system instantly locks all exit controls, forcing the **Gismotron Assistant** to play sequential instructional voice lines synchronized with required player actions immediately after the vendor's welcome line:

**Gismotron Assistant**: The column on the right displays currently accessible firearms in your inventory. Please click on the Test Weapon.

- 🎯 **Action 01 Check**: The player moves the selection cursor to the right column and clicks on the owned **Test Weapon** row. The center preview screen instantly switches from the corporate commercial video to the weapon upgrade blueprint schematic layout.

**Gismotron Assistant**: The center window now houses the weapon upgrade schematic layout. It displays the weapon contour alongside the upgrade windows. For this instructional, three separate windows are required. A test currency package has been credited to your balance. Standard upgrades require Hofitum. Please click on three different active green upgrade windows consecutively.

- 🔧 **Action 02 Check**: The player clicks on three different active green upgrade windows inside the center panel exactly once per window, spending the test **Hofitum Crystals**. Upon completing all three distinct rows, the connected path opens, activating the premium gold node slot.

**Gismotron Assistant**: Excellent. You are now presented with a Gold Upgrade. These require Nirgenium for acquisition—a resource encountered with extreme rarity across global sectors. This specific upgrade type introduces sweeping overhauls to the firearm properties or injects unique operational capabilities. Please acquire the upgrade using the test resource provided.

- 🏆 **Action 03 Check**: The player clicks the unlocked gold upgrade slot in the center panel, spending the provided test **Nirgenium shards** and successfully completing the interface training sequence.

---

#### **⚙️** HOFITUM UPGRADE PARTICLE VFX & MESH LINE FILL LOGIC

- 🟩 **Progressive Segment Fill & Color Interpolation**: The exact frame the player clicks on an active green upgrade row, the UI manager runs a fill script. The row background — styled as a clean trapezoid frame with angled bevels — smoothly blends its shader color from a dull charcoal shade into a high-saturation emerald-green. Concurrently, the interior filling bar increments by exactly **33.3%** per click, visually tracking the three-step training sequence.

- 🔮 **Technical Wireframe Flow & Particle Spline Inflow**: Along with the window activation, the system spawns a localized Niagara GPU particle system at the center coordinates of the card row. The emitter releases a tight stream of glowing teal-cyan micro-particles and square dust trails. These particles ignore random scattering, hard-locking their flight paths along the thin callout blueprint lines to visually flow straight into the targeted weapon component (such as streaming directly into the barrel or muzzle socket mesh nodes).

- ⚡ **Component Pulse Resonance & Flash Dispersal**: The exact frame the particle stream hits the weapon component vertex coordinates, the central vector line-art icon triggers an immediate reaction. The affected outline stroke lines flash with a high-intensity neon pulse (emissive value = **10.0**) over **8 frames** to confirm energy absorption. This effect is backed by a tight, screen-space cross-shaped spark blast overlay that expands and vanishes within a **12-frame** decay window, cleanly returning the store menu layout to a stable idle state without cluttering the screen.

---

#### **⚙️** GOLD NIRGENIUM NODE ACTIVATION VFX & MATERIAL OVERRIDE

- 🔲 **Row Unlocking & Glitch Animation**: The exact frame the player maxes out the last green node, the interface triggers the `Gold_Node_Unlock` sequence. The locked premium row background — styled as a trapezoid frame with 45-degree angle bevels — executes a sudden 10-frame digital glitch animation. The default charcoal-grey stroke lines split into animated, sharp geometric fragments that slide rapidly along the horizontal plane to visually show the interface unlocking.

- 💥 **Gold Emissive Burst & Rectangular Glow**: At frame 11 of the sequence, the center of the premium upgrade row releases a high-intensity magnesium-gold flashing light effect (emissive multiplier = 15.0). The visual completely rejects smooth organic particle spheres, spawning a widening array of sharp, nested rectangular wireframe boxes that expand outward across the screen over 15 frames, cleanly pulling the player’s focus directly onto the newly exposed Nirgenium slot.

- 💎 **Core Glow & Chromatic Effects**: As the gold flash fades out within its 20-frame decay window, the inner slot material updates its state code to `Active_Gold`. The material applies a high-gloss texture pass with an ultra-low roughness value (0.01) and a progressive chromatic aberration filter along the border edges, running a hot neon-orange energy ripple from left to right. This glowing core physically projects a warm amber light pass onto the central weapon vector icon, signaling that the premium tier is fully operational and waiting for a Nirgenium shard purchase.

---

#### **⚙️** GOLD NIRGENIUM UPGRADE AUDIO DESIGN & SYNCHRONIZED BLAST SFX

- - 🔊 **Glitch Distortion SFX Layer**: The initial 10-frame visual disruption phase of the upgrade slot triggers a high-frequency digital glitch sound effect (`SFX_Nirgenium_Glitch`). The sound processes an erratic, bit-crushed square wave mixed with a fast phase modulation, creating a sharp, high-speed static distortion chime that signals to the player that the interface layout is changing.

- 💥 **Gold Blast & Sub-Bass Drop**: At the exact frame index 11 where the gold node discharges its maximum visual flash, the audio engine fires a heavy sound block (`SFX_Nirgenium_Blast`). The sound design combines a sharp synthetic laser snap and a massive, sub-bass sine-wave drop clamped at a heavy 45 Hz threshold to create a powerful rumble, completely cutting through any background combat audio loops.

- 🔮 **Crystallization Resonance & Latch Snap**: Immediately following the sub-bass explosion, the system blends into a stable activation loop (`SFX_Nirgenium_Active_Idle`). The track layers a high-frequency crystalline mineral resonance shimmer at 3200 Hz that tracks the moving neon-orange energy ripple, resolving into a solid, heavy mechanical dead-thud clamped at 90 Hz to audibly confirm that the premium capability is unlocked.

---

### **📥** PHASE: URBAN SECTORS — THE CEROSCAN TRAIN STATION INTERCEPT (ACT III)

- 🚉 **The Transit Corridor Infrastructure**

**Level Structure Note**: Positioned precisely between the Botanical Garden and the Warehouse is the active Ceroscan Railway Station. The primary environmental obstacle on the central platform tracks is a fast transit train featuring a massive orange bomb shell structurally mounted onto its lead locomotive.

---

#### **💬** WIRELESS DIALOGUE: THE BOMB RUN

- **The Context**: Witya enters the train platform zone.

**Katya:** Witya, I am highly uncertain that transporting a bomb of this magnitude is safe.
**Witya:** Brats. Do you copy?
**Brats:** Hearing you. Something important?
**Witya:** What do you hear about transportation of the massive bomb from the local station?
**Brats:** What? What bomb? Unlas!
**Unlas:** What happened?
**Brats:** I received information that some kind of bomb was being transported by train.
**Unlas:** So you received it, but for some reason I didn't?
**Brats:** Acknowledged. Witya, intercept that train. We have nearly cleared our ground here.

---

#### **🔊** STATION ENVIRONMENTAL AUDIO & DIEGETIC INTERCOM LOGS

- 📢 **Audio Function Loop**: As Witya explores the railway station tracks and platforms, a funny automated voice message loops continuously from the station’s overhead speakers, running an ironic corporate liability announcement:

_"Attention all passengers. Due to the active invasion, trains may be swarmed by aggressive Warbots. We apologies with this inconvenience._

---

### **🗺️** THE PLATFORM BOX CACHE & LOCK GATING

- 🧱 **Platform Layout Note**: The railway platform layout features a large barricade made of stacked cargo boxes. Executing a standard jump over these boxes reveals a hidden point-of-interest (POI) zone containing valuable **Hofitum Crystals**, rewarding players who explore the platform corners.

#### **🔐** THE WAREHOUSE GATE & LICENSE STRIPPING

- 🔐 **The Dynamic Lock Validation Logic**

**Level Layout Note**: Branching off the station platform is a locked security door leading to the Warehouse zone. This gate is hard-gated by a heavy locking mechanism that covers a massive stash of Bolt Crates and exactly one Nirgenium shard. The unlock script checks your current difficulty settings and story-state inventory items.

- **Minimum Difficulty Sequence (The Casual Access)**: The train countdown timer is completely disabled; the locomotive patiently waits at the platform. Witya has plenty of time to walk up to the terminal and flash Brats's pass card (`Item_ID_Ceroscan_BluePass`). Because this card carries high-level security clearance, the door opens instantly, granting immediate access to the Nirgenium shard.

- **Higher Difficulty Sequence (The Time-Attack Block)**: The train departure countdown loop is highly aggressive. Witya is forced into an immediate high-speed sprint to catch the last train car, making it physically impossible to detour toward the locked Warehouse gate during the initial run.

- **The Backtracking Rule (The Ranger License Stripping)**: Upon completing the main story chapter and returning later to the Ceroscan Station for cleanup exploration, a narrative script updates Witya's items. Brats's blue card has been permanently removed from the inventory. In its place, the system gives Witya his personal Rookie ID Card, which lacks administrative access. To bypass the lock and claim the Nirgenium shard on higher difficulties, the player must return later and use a specialized illegal hacking gadget—The **Lapsepasser** (Посягатель)—to bypass the lock.

---

#### **⚙️** TRAIN CAR CATCH UP PHYSICS & ATTACHMENT OVERRIDE

- - 🚂 **Train Acceleration & Time-Attack Window**: The train blueprint (`BP_Ceroscan_Train_D`) runs a custom velocity curve along the station tracks. The moment the loudspeaker announcement finishes, the train switches its state to `Departing`. The physics system smoothly scales the forward velocity along the X-axis from a dead stop (0.00 m/s) up to a maximum escape speed of 16.5 m/s over a 150-frame acceleration curve, setting a tight time-attack window for Witya's sprint.

- 📐 **Inertia Calculation & Jump Assist**: While Witya is in mid-air (`Airborne_Phase = TRUE`) jumping toward the moving train, the physics engine continuously calculates the speed difference between his horizontal vector and the accelerating train cars. This relative calculation ensures that if Witya leaps in the same direction the train is moving, his airborne trajectory extends realistically. This prevents unfair drop-offs, keeping the player from falling directly into the lethal rail hazard zone.

- 🤝 **Handrail Attachment & Weight Absorption**: Positioned on the exterior mesh of the last two train cars are invisible box collision triggers linked to the metal handrails (`Socket_Train_Handlebar_L/R`). The exact frame Witya’s hand colliders touch these trigger zones during his jump, free-falling rigid-body physics turn off. The engine runs a quick 1-frame attachment script, hard-locking Witya’s base position directly onto the moving wagon’s position. This action instantly starts a 45-frame landing compression animation to visually absorb the kinetic momentum.

---

#### **⚙️** TRAIN D ACCELERATION AUDIO DESIGN & COUPLING SYNCHRONIZATION

- 🔊 **Three-Layer Mechanical Propulsion Mix**: The master audio event for the train's acceleration combines three independent real-time sound layers bound to the locomotive: a low-frequency heavy electric turbine hum (set to 80 Hz to emphasize the train's massive weight), a mid-range hydraulic stabilizer pressure whine, and a high-priority cutting metallic screech from track friction that dynamically pans across the station platform coordinates.

- 🎚️ **Velocity-Linked Rhythm Shift & Pitch Warping**: The rhythm sound — the signature metallic wheel-clack sound (`SFX_Train_Wheel_Clack`) — cannot run on a static playback loop. The audio engine must query the locomotive's real-time velocity vector float data. As the train scales its forward velocity up along the 150-frame acceleration curve from 0.0 m/s to 16.5 m/s, the system must linearly scale up both the audio playback speed (tempo) and pitch by a factor of **2.2**, transforming a slow, heavy clanking sound into a fast, terrifying rhythmic roar.

- 💨 **Pneumatic Brake Release & Bass-Heavy Decay**: At the exact frame index where the train shifts its state to Departing, the default idle loops are overridden. The system discharges a high-priority starter sound block combining a sharp pneumatic valve emergency pressure release hiss with a deep, sub-bass mechanical clutch latch thud capped at 55 Hz. This initial audio blast physically rumbles the player's audio canvas, providing an immediate, urgent acoustic cue that the time-attack sprint window is officially operational.

---

#### **🏃‍*♂️** TIME-ATTACK CONSTRAINT: THE CLOCK WORKSHOP DEPOT

- ⏱️ **The Platform Overlap Trigger & Immediate Fail-State**: On all campaign difficulty tiers above the absolute minimum setting, free exploration of the train station is strictly blocked during the initial story run. The locomotive will not wait for the player to clean out their inventory or check corners.

- 📢 **The Intercom Dispatch Signal**: The exact frame Witya crosses a designated trigger line on the platform floor, the public speakers override all background audio channels with an urgent dispatch warning:_

*"Train D is now departing from platform line two. Next scheduled termination stop: The Clock Workshop."*

- 🏃‍♂️ **The Sprint Execution**: Witya must instantly drop all exploration and initialize a maximum-speed sprint toward the train tracks. The player must successfully intersect the collision boxes of either the final or second-to-last train car during their acceleration phase. Failing to reach the wagons within the hard-coded time window instantly triggers the global **Game Over screen** (Fail Canvas).
---

### The remainder of this document is currently under development. Its development is not a high priority, as the author is currently actively engaged in publishing and copyrighting materials created over 15 years of active creative work. The document then presents dialogue and cutscenes that will occur during the storyline.

---



### **📺** MISSION DIALOGUE: THE HYDROSWAPPER ACQUISITION

- 💼 **The Gadget Allocation**

**The Environment:** The tropical resort shoreline of **Del-Alformar**. **Fyodor Nakagavin** stands near an interactive water management terminal mesh, engaging with Witya and Katya.

**Fyodor:** Here is the device for water redistribution. I call it the **Hydroswapper**. You can keep it after you’re done using it.
**Witya:** What, for free?
**Fyodor:** Of course. Why, should I force you to pay just so you can help me? What, do you think you're playing some game from 2002 b.g.w.?
**Witya:** Well, no, I'm pretty sure I'm living real life. What does a game have to do with this?
**Fyodor:** Oh, Whiteman, look at this! Another normie completely missed the depth of **neo-post-meta-irony**!
**Witya:** Ah. Ok.
**Katya:** Whiteman? How do you know that name?
**Fyodor:** Oh, I see you're a woman of culture. Of course I know him—he regularly visits my resort!
**Katya:** Actually... he's dead.
**Fyodor:** Whiteman lives! Just like Fencloon!
**Katya:** I see...

---

#### **⚙️** ANIMATION & GESTURE OVERRIDE NOTES

- 🤪 ANIMATION & GESTURE OVERRIDE NOTES

- 🤪 **Fyodor's Hyper-Active Gesturing Loop**: The exact frame the dialogue trigger runs (_"Another normie completely missed the sheer depth of neo-post-meta-irony!"_), Fyodor’s default idle pose must break into a fast gesture override track. His hands must perform chaotic, asymmetric flailing in 3D space (e.g., drawing invisible geometric shapes or aggressive air-quoting) to visually highlight his unhinged, conspiracy-theorist personality.

- 🗣️ **Jaw Amplitude**: The lip-sync system must apply an exaggerated motion multiplier for the mouth and jaw blend shapes during the word _neo-post-meta-irony_. The jaw bones must drop **20% lower** than standard dialogue values to over-emphasize the prefix delivery, while the tongue and lip meshes stretch to their limits for exactly **24 frames**.

- 🙄 **Eye-Roll & Head Roll Vector Synchronization**: Along with the hand gestures, Fyodor’s head joint must perform a fast, dramatic 360-degree tilt loop (head roll). This movement ends with his eyes locked onto the upper screen edge, creating a classic "looking to the heavens / pleading with the gods" pose. Witya's look-at controller, conversely, must remain completely static and deadpan, maximizing the comedic contrast of the scene.

---

### **📥** THE CORPORATE DISPUTE

- 💼 **Confrontation due to failures**

Visual Sequence: Chairman Quand and Unlas stand adjacent to each other within the central lab sector layout, engaged in a high-intensity communication sequence.

**Quand:** I told you to get rid of Witya! Why the Nether is he still causing problems? Ah, he even managed to rescue Nimsov!
**Unlas:** Chairman Quand, I honestly tried. I threw him right into the testing grounds of the Systematic Snackerbeast, and then straight into your factory's security defense systems...
**Quand:** It's solely because of your "initiatives" that I've incurred heavy financial losses. And that Chord is still... (Stammers in pure rage) running around!
**Quand:** It's not like I can go out and fight him personally!
**Quand:** Exactly! The next time you cross paths, you will be the one to face him!

**Tikhon Approach:** From the shadow layer of the entrance threshold, a cough audio cue registers.

**Tikhon:** Ahem...

Quand turns 180 degrees and meets Tikhon.

**Tikhon:** I apologize for interrupting, Chairman, but I am here regarding the payment allocation for the development of the Acatadop...
**Quand:** Of course... You see, too many bolts are being wasted on robot bolts. If you've been here long enough (Quand rotates back to target Unlas with an aggressive look-at constraint), then you know exactly whose fault that is.

---

#### **📺** THE CORPORATE DISPUTE (THE ROBOTIZATION INCIDENT)

**Tikhon (Stepping closer):** I understand you perfectly. What I don't understand perfectly is how this fraud managed to gain such a high level of trust.
**Unlas:** Oh, come on...

**Physics-Driven Interaction Trigger:** Unlas casually gives Tikhon a light nudge. He flips over the handrail and plummets directly into the robotization device.

**First-Person Camera Override:** The camera abruptly switches to a first-person view of Tikhon. As he falls, his two arms, stretched upward, are visible at the edges of the screen. He hits the bottom of the chamber, and the heavy mechanical shutters begin to slowly close.

**Unlas:** We are already... Different...
**Quand:** What have you done, you Netherite!
**Unlas:** I'm sorry, Chairman, I didn't mean to... I forgot he was so fragile...
**Quand:** Fine, he already finished his development anyway.

**Cinematic Camera Switch:** At this point, the robotization device are completely closed. The camera framework cuts back to a medium shot setup focusing on Quand and Unlas.

**Quand:** I'll find him a manager job appropriate for a robot later. As for you... One more failure, and you'll end up in that device yourself! And I definitely won't bother picking out a worthy position for you! You'll go work as a janitor, just like Fencloon!

Quand turns away from Unlas and rides away on his Hover Scooter towards the doors from which Tikhon came.

---

#### **⚙️** ANIMATION & FACE MORPH STREAMING

- 😡 **Quand Rage-Stammer Animation Sequence**: The exact frame the dialogue breaks (_"And that Chord is still... running around!"_), Quand’s default body pose must switch to a fast, intense body shake. The animation track must simulate a state of pure, unbridled fury. His fists must lock into tight, rigid structures, to cleanly show extreme physical tension before the scene resolves.

- 👁️ **Eye-Tracking & Brow Distortion**: During this verbal breakdown, Quand’s pupil mesh scales must rapidly alternate between minimum and maximum sizes to create a manic, unhinged stare. The eyebrow bones must drop to their lowest limit, aggressively pressing down onto the upper eyelid geometry, while the jaw blend shape locks in a semi-open, trembling pose for exactly **15 frames**.

---

#### **⚙️** TECHNICAL & AUDIO-VISUAL STREAMING NOTES

- 🔊 **Robotization Chamber Shutter Audio Subsystem**: The closing sequence of the mechanical shutters must trigger a multi-layered sound design block. The master mix requires a heavy hydraulic pressure hiss, followed by a metallic screech, and finishes with a heavy, low-frequency sound thump (bass drop) on the exact frame of total closure. The ambient reverb inside the lab room must dynamically update to simulate a fully sealed, pressurized containment cell.

- 🎥 **First-Person Shutter Masking & Screen Fade**: During the first-person camera override, the mechanical shutters must render using independent, high-polygon physical models moving from the screen borders toward the center. As the mesh boundaries touch and completely block the camera view, the engine must execute a hard black screen fade, transitioning the screen layout to absolute pitch black inside a tight **5-frame** window.

- ⚡ **Exothermic Venting & UI Warning States**: At the exact moment of total chamber closure, all background terminal monitors and holographic displays within the lab environment layer must dynamically switch from their default corporate green into flashing, high-intensity warning amber. Simultaneously, the base of the robotization device must trigger a heavy Niagara particle system spawn, venting high-pressure white steam across the metal floor to convey the immediate start of the transformation sequence.

---

#### **⚙️** PHYSICAL SIMULATION & COLLISION NOTES

- 🛹 **Skeletal Mesh Ragdoll Interpolation**: At the frame index of Unlas's nudge interaction, Tikhon's character controller must instantly deactivate its root motion animations and enable full global ragdoll physics simulation. The transition blend duration between the kinematic state and physical simulation must be clamped to exactly 0.1 seconds to simulate an abrupt, realistic loss of structural balance without causing vertex stretching or model clipping.

- 🚧 **Handrail Collision & Angular Velocity**: The handrail geometry must utilize a precise, non-convex primitive collider. When Tikhon's hip and pelvic bone markers intersect the handrail collision bounds, the physics engine must apply a forward torque modifier to his upper spine bone targets. This forces a rapid angular velocity shift, causing the character model to dynamically flip and spin upside down as it clears the boundary, rather than just sliding off the edge.

- 📐 **Trajectory Clamping & Center of Mass**: To ensure Tikhon’s organic chassis lands precisely inside the center of the robotization chamber, his physical center of mass must be temporarily adjusted during the fall phase. The drag and gravity scale modifiers for his limbs (specifically the arm and leg bone) must be increased by 15% to prevent loose ragdoll flailing from hitting the outer walls of the device, keeping his trajectory locked to the target zone.

---

#### **⚙️** AUDIO DESIGN & SIGNAL PROCESSING NOTES

- - 🔊 **Robotization Chamber Shutter Sound**: The closing sequence of the mechanical shutters must trigger a multi-layered sound design block. The audio mix requires a heavy hydraulic pressure hiss, followed by a metallic screech, and finishes with a heavy, low-frequency sound thump (bass drop) on the exact frame of total closure. The ambient reverb inside the lab room must dynamically update to simulate a fully sealed, pressurized containment cell.

- 🎥 **Shutter Closing & Screen Blackout**: During the first-person camera view, the mechanical shutters must render using independent, high-polygon models moving from the screen borders toward the center. As the mesh boundaries touch and completely block the camera view, the engine must execute a hard black screen fade, transitioning the screen layout to absolute pitch black inside a tight 5-frame window.

- ⚡ **Steam Venting & UI Warning States**: At the exact moment of total chamber closure, all background terminal monitors and holographic displays within the lab environment layer must dynamically switch from their default corporate green into flashing, high-intensity warning amber. Simultaneously, the base of the robotization device must trigger a heavy Niagara particle system spawn, venting high-pressure white steam across the metal floor to convey the immediate start of the transformation sequence.

---


## 🗂️ ENVIRONMENT & PROP SPECIFICATION: ENDGAME PHASE (WITYA'S APARTMENT)

### 🛏️ 1. THE LIVING & SLEEPING ZONE: THE POST-OPOZITUM DEPRESSION CELL

- **The Room Constraints**: A tiny, cheap kennel. Cramped and constricted, capable of causing claustrophobia and a feeling of moral emptiness.

- 🪟 **The Window & Lighting Layout**: Positioned directly opposite the entry door is a basic window frame with no windowsill. It is covered by thin, cheap drapes that let external ambient light bleed into the room.

- 🛏️ **The Bed Arrangement**: A thin, cheap mattress sits flush right against the window frame. The bed is covered in a plain brown, patternless bedspread that hides two flat pillows and a tightly folded blanket.

- 📦 **The Decorative Props**:
    - A single golden-yellow accent pillow with a long, shag texture sits on one side.
    - A small audio speaker prop, shaped exactly like the corporate logo of the **Tonata Rangers**, lies carelessly on the bed.

---

### 🛠️ 2. The Workbench & Tech Infrastructure (The Outlaw Engineer Grid)

**The Desk Workspace:** Positioned against the opposite perimeter wall is a heavily cluttered, un-organized engineering workbench covered in soot, tools, and hardware scrap.

**The Technical Equipment Arrays:**
1.     A high-temperature soldering iron prop.
2.     An outdated, analog oscilloscope.
3.     A heavy-duty **BGA Reballing Station** utilized for high-tier processor and microchip replacement swaps, positioned immediately adjacent to the desk layout.

* **The "Grentera Fat" Easter Egg Container:** A cylindrical snack container (visually identical to a _Pringles_ can) sits on the workbench surface. The texture map contains two distinct localized warning labels:
	* _Primary Label:_ **"Grentera Fat"** (Жир Гринтера).
	* _Secondary Subtext:_ **"For culinary use only—Do NOT use as soldering flux!"**

* **The Wall Graphics:** A faded, slightly torn marketing poster depicting Captain Unlas and the Tonata Rangers hangs directly above the cluttered workbench.

* **The Improvised Ventilation:** Located on the window-side wall, close to the desk structure, is a crudely chiseled, rough circular hole smashed through the concrete. A standard industrial cooling fan is forcefully jammed into the opening to serve as makeshift ventilation against toxic rosin fumes.

---

### 🗄️ 3. The Storage Rack Inventory (The Trophy Archive)

* **The Structural Rack:** A crude, self-built wooden shelving unit is wedged tightly between the bed frame and the main entrance door seal.

* **The High-Priority model (The Aviator Cap):** The topmost shelf holds a distinct **Aviator Cap (Кепка авиатора)**.

	* This item is a narrative milestone tool. Shaders and vertex lighting must ensure this cap is highly visible and rendered as an essential, un-missable visual element of Witya's permanent silhouette from this narrative point forward.

* **The Auxiliary Prop:** The lower shelves contain exactly the following models:

	0.     One pristine **Unbinil Bolt** trophy.
	1.     Multiple device housings of un-identified origin.
	2.     A pair of worn, oil-stained boots.
	3.     Several **Nirgenium Cartridges** reserved for replacement when his integrated chest cell runs dry.
	4.     A backup **VersaWrench**
	5.     Miniature collectible figurines of Captain Unlas, the Tonata Rangers, and the deceased legend, **Master Allshield**.

---

## 🪐 THE REJECTION OF THE BRAND

* 🗂️ **Master Cinematic Event & Dynamic Camera Lock Pass**

* 📍 **The Context:** Immediately following the destruction of Opozitum. Witya returns to his quarters in a state of high-intensity emotional and psychological collapse.

---

#### 🎥 1. Camera Composition & Blocking (The Obstructed Frame)

* **The Camera Vector:** The camera lens maintains a static, fixed perspective directed entirely at the center storage rack array. The **Aviator Cap** is framed precisely in the absolute dead-center of the middle shelf.

* **The Obstruction:** Witya opens the door to the room with his foot. The door panel covers a significant part of the screen, completely hiding the **VersaWrench** location.

* **The Helmet Discard:** Witya violently strips the **Tonata Ranger Helmet** from his head structure, hurling it directly down toward the camera lens vector into the empty floor pocket between the entry wall and the soldering workbench.

* **The Kit Transition:** Kate swiftly enters directly behind him, silently sealing the door.

---

### 🛏️ 2. The Mammal Plant Physiology & The Corporate Speaker

* - **Witya's Despair**: Witya falls heavily onto his classic frame bed, overwhelmed by emotional shock.

- **The Ear-Leaves Reflex**: As Witya sits near the window, his long ear-leaves—which were previously tightly clamped and pressed together due to severe post-combat trauma—gradually expand and unfurl on their own, turning naturally toward the sunlight streaming through the curtains.

- **The Emblem Speaker Playout**: Witya picks up an audio speaker shaped like the Tonata Rangers emblem. He presses the device exactly five times to listen the recorded tracks:
	1. _Clicks 1, 2, 3:_ The speaker playout triggers generic, high-gloss marketing propaganda regarding altruism, cosmic safety, and universal heroism.
	2. _Click 4:_ The audio logs transition into socio-economic criteria, enumerating the mandatory financial baseline and personal status required for entry.
	3. _Click 5:_ The log loops into corporate "benefits, privileges, and membership preferences."
	4. _The Terminal Sequence:_ The broadcast concludes via the flatline corporate audio track: **"And remember—absolute, un-compromised obedience to Captain Unlas is primary!"**

---

#### 💥 3. THE ANGER OUTBURST & THE WALL CRACK REVEAL

- **Smashing the Speaker**: Witya snaps into an immediate rage state. He slams the emblem speaker onto the floor and stamps down hard on it with his foot, acting like a heavy industrial press. The plastic casing shatters completely, exploding into sharp shards across the room corners.

- **Tearing the Poster**: Witya leaps onto his work-chair, aggressively gripping and tearing down the Tonata Rangers promotional poster hanging above his soldering workbench.

- **The Exposed Crack**: The destruction of the poster reveals a massive, jagged structural crack running vertically down the concrete wall. A small fragment of this crack was already visible, sticking out past the edge of the poster.

---

#### 📝 PRODUCTION NOTE: ANIMATION & SHADER SYNC

**The Ear-Unfurling Animation**: The character animation team must use morph targets (blend-shapes) to sync the gradual opening of Witya's ear-leaves with the exact moment he enters the window's lighting area. The movement must look subconscious, slow, and purely organic, contrasting sharply against his explosive, hyper-aggressive physical outbursts during the poster destruction.

### 🪐 THE TIME-CUT

- 📁 **Master Cinematic Exit & Lighting Setup**
- 📍 **The Context**: Witya faces the immediate threat toward his home planet. This sequence locks in his final emotional transformation before the credits roll or the next level starts.

---

#### 🎥 External Camera & Tactile Micro-Animations

* - **The External Wall Crack View**: The camera cuts outside the building, tracking Witya strictly through the jagged concrete wall crack. Witya's facial expression shifts dynamically from raw, explosive rage to profound, catatonic grief.

- **90-Degree Shot**: The camera pans directly over the bed frame, at a precise 90-degree angle downwards. Witya is lying on his back, still in his full Tonata Ranger armor, clutching a small, pillow to his chest plate.

- **The First-Person View & The Insect**: The camera shifts to a strict first-person perspective from Witya's view, looking straight up. Suspended directly above him is a rotating miniature model of star system, styled like a handmade baby mobile. A insect flies into the frame and lands directly onto the sphere of the planet Meltin, which hangs by an old, worn thread.

- **Turning Towards the Side Camera**: The camera dynamically cuts to a close side-angle view, positioned near pillows. Witya turns onto his left side, rolling over to face directly into the camera lens while placing a yellow, long-pile pillow under his head. Witya lies still in silence for a few moments, his face close to the foreground.

- **The Foreground Drop**: The insect chews through the old, fragile thread. The miniature sphere of Meltin detaches from the mobile frame and drops heavily onto the bed sheets, landing directly in the foreground, right between Witya's nose and the camera lens.

- **The Companion Arrival**: Witya sits up slightly as Katya steps near him.

    - **Katya**: "Witya..."

- **Timida's Message**: Katya activates the communication receiver on her chest, launching a recorded audio log from Timida:

    - **Timida (Audio Filter)**: "Mechanic! We finally intercepted your tracking coordinates. His next target... is Meltin."

- **The Broken Helmet**: Witya rises into a full sitting position, fixating his eyes on the floor corner: his broken Tonata Ranger Helmet, showcasing a clear fracture.

---

### 🚪 THE SHUTTING DOOR CINEMATIC (THE EMPTY SHELVES REVEAL)

- **The Fixed Camera Frame**: The camera cuts to its final shot, locking its focus strictly onto the storage rack wall. The opening door frame completely blocks the player's view of where the **Aviator Cap** and the **VersaWrench** are stored.

- **The Disappearance Moment**: The door model plays a slow closing animation. As the moving door seals the view and then opens back up to clear the line of sight toward the shelving unit, the engine updates the game state: the **VersaWrench** and the **Aviator Cap** are now completely gone from the shelves.

---

#### 📝 PRODUCTION NOTE: VFX AND TRANSITION CODES

⚙ **The Silent Model Deletion**: The level design and scripting teams must ensure that the model deletion pass (the removal of the wrench, boots, and cap) is executed silently while the closing door mesh completely blocks the camera view. When the shelves are exposed again, the empty slots serve as the primary visual confirmation of Witya's deployment.

---


## 🪐 Helplessness of Quand (The Acatadop Bridge)

*  🗂️ **Master Cinematic Event & Dynamic Shadow Shader Trigger**

📍 **The Location:** The main bridge chamber of the Acatadop. The panoramic windows show the Wealth Refussi.

Captain Unlas is defeated by Witya. Witya instantly turns his eyes and aims Chairman Quand.

Quand rushes toward the exit doors in a panic. Before he can reach the threshold, a high-speed plasma projectile overtakes him, welding the heavy metal doors shut.

Quand crashes off his hover-scooter. He crawls backward on his back, clumsily kicking his legs out in terror, pinning his chassis against the welded wall substrate. A massive, sharp shadow of Witya—holding the silhouette of an oversized heavy firearm weapon—slowly eclipses his body.

* **Quand:** Everything has its price, right? W-w-what's yours?
* **Witya (Gesturing with his blaster):** Yeah, yeah. At the Houses... lives... souls. Everything. Move it. I’m gonna let you pay up."

Quand swallows hard. He obediently crawls back onto his hoverscooter.

---

### 📺 SCENE ON THE CONTROL BRIDGE

* The camera cuts to the interior layout of the Command Bridge. The automatic heavy doors slide open. Several Grable technicians stand at the control terminals.

* Quand rides into the chamber space on his scooter. Witya follows immediately behind him, targeting his back with a secondary, compact single-handed sidearm.

* **View in the background:** The starship **Bennu 1** is clearly visible through the panoramic window. Witya does not notice its presence.

* **Witya**: Aim the Acatadop at Wealth Refussi and commence deplanetation!
* **Quand:** I won't!
* **Witya:** Aim it.
* **Quand:** And what are you gonna do, kill me, huh?
* Witya holsters his blaster and equips the Sheepmorpher.
* **Witya:** No. You’re going to enjoy hay and barn.
* **Katya:** He won't. He... will keep his sanity.
* **Witya:** Even better. That means you will definitely press that button. What's my price.

---

### **📥** PHASE: THE TONATA INTERVENTION (THE Acatadop BRIDGE)

- 💼 **The Sovereignty Shift Trigger**

Visual Sequence: Quand turns away sharply, breaking eye contact with Witya, and barks an order toward the control terminal.

* **Quand:** Prepare for Deplanetation!
* **Katya:** Maybe... maybe we should just keep this Frankenplanet? We could use it to... relocate those whom he displaced.
* **Witya:** Yeah. And blow up Meltin and several other planets just to fit it into orbit like he wanted?

Visual Sequence: A massive red button rises from the main control panel. Quand flips open the protective glass cover but hesitates to press it. The camera cuts to a tight close-up shot focusing entirely on the button. Suddenly, a voice echoes from the entrance threshold: _"I order you to stop!"_

---

### **📺** INTERCEPTION OF ACTION AND ARRIVAL OF TONATA RANGERS

The command bridge automatic heavy doors slide open. Positioned outside the threshold are two Tonata Ranger robots, featuring alternative paint skin. Standing between them is **Sveta Bennux**. The robots advance into the chamber space with their blaster barrels raised and targeted directly at the heroes' positions.

Witya and Quand spin around instantly, raising their arms in compliance.

* **Sveta:** Witya, you can lower yours. We aren't aiming at you.
* **Sveta:** Wealth Refussi is now the property of the Tonata Rangers and the Social Fund of the Tonata Government.

**The Background Frame Action:** As **Sveta** and the automaton guards approach the console, the background viewport showcases Captain Unlas traversing the hallway corridor under escort by exactly four Ranger robots. Unlas is visibly bored. He casually brings his linked hands up toward his jaw structure to execute a massive yawn—and entirely fails to notice that this simple muscular reflex forcefully snaps the steel chain links of his handcuffs completely in half. He continues walking without offering any reaction to the failure.

The surrounding robots scatters away from Unlas, tracking him with their weapon systems and re-targeting their blaster barrels.

* **Unlas:** _(Forcefully raising his hands)_ "I didn't mean to! Honestly!"

---

### **📺** THE WEALTH REFUSSI DESTRUCTION

* **Witya:** The Social... Fund?

Sveta continues her stride toward the central bridge.

* **Sveta:** Yes. We will relocate Wealth Refussi to another star system and resettle all those whom Quand displaced.. For free.
* **Quand:** For free?

**Psychological Destabilization:** Instantly reacting to the statement, Quand’s capitalistic logic collapses. In a split-second movement, he dives downward, aggressively slamming his hand onto the large red button.

* **Quand:** No one...

One of the Tonata Ranger robots fires an immediate shot. The energy projectile impacts Quand. Quand collapses onto the deck substrate but remains semi-conscious. He stares at the floor, shaking his head violently.

Witya turns away from the bridge crew, redirecting his view entirely toward the panoramic observation window. He watches as Wealth Refussi shatters into small kinetic fragments. The camera captures the full-scale cosmic apocalypse rendering outside the hull structure.

* **Witya:** I'm sorry. This is my fault. I brought him here at gunpoint...

**Sveta** stands next to Witya, placing her hand on his shoulder. **Sveta** and Witya make eye contact.

* **Sveta:** It's not your fault... You... You couldn't have known. Even I don't completely... It's okay to love your home. It's normal.

By this shot, the robot rangers had already closed the distance and begun arresting Quand.

* **Witya (Looking back at the destruction of Wealth Refussi):** But I never loved it! I always dreamed of escaping it!

Sveta removes her hand  from Witya's shoulder and walks toward the main control console.

The camera tracks backward, cutting to a wider reverse-angle shot focusing on the control console. **Sveta** closes the plastic protective cover over the button, and the entire button module retracts inside the control panel housing. While this animation plays, **Sveta** delivers her dialogue line:

* **Sveta:** You know, sometimes you only start to love something after you lose it, or... when you very close to lose it... And, honestly, thank you...

**Witya (not Looking back at her):** For what?

At first, Witya looks forward, but then turns his gaze in her direction.

The camera zooms in, emphasizing the subtle twitch of Sveta's tail.

Vitya turns his whole body and adopts a slightly lustful expression.

**Sveta (Turning to face him):** For clearing out the Acatadop.

**Cinematic Camera Switch:** The camera cuts sharply to a dedicated tracking frame focused entirely on **Sveta**.

**Sveta:** Honestly, I... was surprised. You did it even faster than we arrived.

**Witya:** Yeah. So they really call someone after all...

Sveta scans Witya's from top to bottom, breaking into a smirk as she delivers her line.

**Sveta:** Hero.

Witya looks up from under his brows, but his brow ridges remain relaxed, creating a non-aggressive expression. He smiles, raising his hand to scratch the back of his head, but only scratches his helmet. He presses a button and the helmet slides off his head, revealing he's wearing an aviator cap.

Sveta executes a quick wink animation, and walks off to assist the Ranger robots in escorting Quand.

Witya tugs at the collar of his suit.

**Katya:** Why did you put on that dusty aviator cap?

The camera zooms in on a close-up of Sveta's shoulder pad. She's standing in profile relative to Viti; the pad bears the Tonata Rangers logo.

**Witya:** Hey, I've never seen you in the Tonata Rangers before...

**[SCENE END]**

**[FADE TO BLACK]**

**[ROLL CREDITS]**

---

#### **⚙️** TECHNICAL & GAMEPLAY STREAMING NOTES

- ⚡ **The Door-Welding Trigger**: The sequence where Witya’s plasma bolt seals the blast doors acts as a definitive point of no return for the cinematic scene. The visual effect must convey instant, high-temperature thermal welding, completely cutting off **Quand's** path of retreat and shifting the tone from a standard chase to a high-stakes cornered confrontation.

---

#### **🗃️**TECHNICAL & HISTORICAL RE-CONSTRAINTS

- 🐏 **The Sanity Preservation Rule**: The dialogue explicitly establishes that the **Sheepmorpher** transformation does not destroy the target’s consciousness. Katya's remark (_"He... will keep his sanity"_) serves as a critical narrative anchor for the third game. The lore rejects any magical explanations; the victim remains fully aware of their physical state inside the animal body, instantly shifting the weapon's profile from pure comedy to real psychological horror.

* 🚀 **Staging the shot with Bennu 1 outside the window**: The panoramic window of the location must constantly show the ship **Bennu I** moored near the massive hull of **Akatadop** in the background. This visual composition is essential for plot continuity.

---

#### **⚙️** TECHNICAL & GAMEPLAY STREAMING NOTES

- - 👮‍♂️ **Tonata Ranger Skin Swap**: The Ranger models in this scene must switch to their alternative texture setup. While their 3D mesh is identical to standard Tonata Rangers, the materials change colors to show their official Tonata government faction alignment. All physics-driven accessories like armor plates and holsters must match this new color palette.

- ⛓ **Handcuff Breaking Physics**: The animation sequence where Unlas snaps his handcuffs must activate a physical simulation override. The chain model requires a predefined stress break-point, instantly splitting the solid mesh into independent, physics-governed fragments that scatter naturally onto the metal floor. The metal snapping sound effect must play with high audio priority to guide the player's attention to this background action.

- 🤖 **Dynamic Threat Re-Targeting**: The moment Unlas casually breaks his cuffs, the four escorting Tonata Ranger robots must instantly drop their passive path-following AI behavior and switch to a combat-ready scatter phase. Their weapon barrels must use a strict look-at controller, snapping instantly toward Unlas's head bone. This animation blend must execute within a tight 10-frame window to maximize the comedic contrast between Unlas's relaxed yawn and the robots' sudden panic.

---

#### **⚙️** CINEMATIC PRODUCTION NOTES: THE DESTRUCTION OF WEALTH REFUSSI

- 🪐 **Planet Destruction Visuals (Благополучный Рефусси)**: The video sequence showing the destruction of **Wealth Refussi** must avoid using a basic particle explosion overlay. The 3D animation setup requires a detailed, multi-stage breakup process: first, the planetary crust cracks into massive, continent-sized tectonic plates, and then high-velocity molten plasma geysers must erupt from the exposed layer to convey the immense physical scale of the disaster.

- 🌌 **Lighting Contrast & Interior Cabin Shadows**: At the exact moment of the detonation, the video frames must capture a blinding full-screen flash. This flash must dramatically illuminate Witya and Sveta inside the cockpit, casting heavy, high-contrast moving shadows onto the interior bulkhead walls behind them to visually ground the characters within the global cosmic explosion event.

---

#### **⚙️** TECHNICAL & UI/UX STREAMING NOTES

- 📜 **End Credits UI & Resolution Scaling**: The end credits sequence must use a dedicated screen-space UI panel set to the highest rendering priority layer. The text scrolling speed must remain completely independent of the game’s global frame rate to prevent any visual stutter or jitter during background level loading. All font sizes, kerning, and localized text bounding boxes must dynamically scale based on the player's screen resolution.

- 🎬 **Post-Cinematic Transition Buffer**: The transition from the final frame of the Acatadop bridge (Witya’s final dialogue line) to the credits screen must execute via a smooth 2-second linear fade-to-black. During this black-screen state, the game engine must force a memory cleanup to clear all heavy character morph targets and cinematic facial animation caches, preparing the system for the cutscene

- 🎵 **Audio Sync & Soundtrack Transition**: The soundtrack layer must seamlessly transition from the tense cinematic orchestral arrangement into the game’s main heroic theme. This audio shift must hit its peak volume exactly when the primary title card — "Ask from Heroism" (Задайте из Героизма) — triggers on-screen. The audio manager must mute all ambient engine hums or generic UI click sound effects during the entire credits sequence to keep the musical track perfectly clean.

---

## **📺** POST-CREDITS SCENE: THE DUMPSTER ALLIANCE

- 🧹 **The Janitor Animation

**The Environment Layout**: A dimly lit, dusty utility room. An unknown robot named **Fencloon** — resembling a short, portly human dressed in a tuxedo, visually looking exactly like a well-fed penguin — holds a broom like an electric guitar. He executes broad arm swings, performing an energetic guitar solo while simultaneously shouting awkward vocal rock sounds.

**Voice-Over Trigger**: From an off-screen intercom channel, a harsh voice commands: _"Fencloon! If you don't resume cleaning, I will revoke today's oil ration!"_

**The Routine Resumption**: Fencloon triggers a heavy sigh animation layer, positions the broom back into its default stance, and begins sweeping dust from corner to corner. He isn't actually cleaning the room, but rather shifting the debris into neat, organized piles.

**Debris Spawn Event**: A new pile of trash is aggressively thrown into a nearby dumpster from outside the camera frame. A significant portion of the debris misses the target container and scatters onto the floor.

- 🗑️ **The Cascade Hazard Interaction**

**The Visual Sequence**: Fencloon sighs a second time, navigates toward the dumpster, and leans downward to collect the scattered items from the floor. At that exact frame, a massive, heavy piece of trash drops from the chute directly into the dumpster module. The kinetic force of this heavy impact displaces the existing trash inside the container, causing a massive wave of debris to overflow and spill over the edges. This displaced secondary avalanche drops straight onto Fencloon's back.

---

### **📥** PHASE: THE BIRTH OF THE SIENCE SIDEKICK

- 💼 **The Trash-Heap Genesis Node**

**The Threat Revelation:** Sitting inside the peak of the garbage pile is a newly robotized entity. With a banana peel on the glass dome of the head, under which various mechanisms are visible.

**Tikhon:** Quand! Unlas! Be you both cursed to the Nether! I will turn you into robots!
**Fencloon:** And what's the point? They'll just stand out as robots with souls.
**Tikhon:** Then, I don't know... I'll turn everyone into robots! By the way, who are you?

**The Camera Vector:** The camera framework cuts to a static, flat shot tracking nothing but an empty, bare wall surface layout.

**The Handshake:** From the upper frame boundary edge, Fencloon’s hand stretches downward into the view space—intentionally bypassing the fact that, according to level design, he is physically positioned lower than Tikhon.

**Fencloon:** My name is Fencloon.

From the lower frame boundary edge, Tikhon’s metallic hand stretches upward.

**Tikhon:** Doctor...

His movement pauses, and his hand freezes in mid-air for exactly 8 frames. He then aggressively squeezes Fenklun's hand, delivering his line:

**Tikhon:** Sience.

---

#### **⚙️** ANIMATION & INTERACTIVE DEBRIS NOTES

- 🧹 **Fencloon Broom Skeletal Attachment**: The broom handle must use a rigid two-handed skeletal attachment setup. The animation layer for the upper body must convey complete relaxation, forcing the shoulder joints to stay loose. The broom head mesh must maintain a tight collision contact with the iron deck floor throughout the idle loop to visually simulate a lazy, low-effort dragging movement rather than active scrubbing.

- 📦 **Debris Scattering & Trash Piles**: The dust and debris models on the floor cannot simply be deleted or hidden upon contact. Instead, when the broom's collision box intersects the dynamic trash props, the physics engine must apply a gentle horizontal force vector. This impulse pushes the meshes away from the broom's path, automatically gathering them into pre-defined trash piles at the corners of the room.

- 😮💨 **Sigh Animation Layer**: At the exact frame index where the sigh audio cue triggers, a separate face and torso animation override layer must blend in with high priority. The chest bone structure must noticeably drop downward along the vertical Z-axis while the head joint drops by exactly 5 degrees. The sweeping speed must temporarily slow down by 40% during this 45-frame sequence to perfectly emphasize the character's total lack of workplace motivation.

---
CC-BY-SA 4.0 + Custom IP Restrictions
