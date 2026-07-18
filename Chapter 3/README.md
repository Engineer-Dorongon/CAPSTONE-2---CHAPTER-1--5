# SENSEY Spatial Navigation Reference Guide

In your current optimized program, the system processes spatial data across three core distance tiers and generates audio cues across three core categories (startup, real-time alerts, and spatial reports).

---

## Part 1: All Active Distance Thresholds

Your system is structured around three precise physical distance zones:

| Distance Zone | Exact Metric | Features & Active System Rules |
| :--- | :--- | :--- |
| **Emergency Stop Zone** | **$\le 0.60\text{ m}$** | • **Unified Depth Stop:** Triggers an immediate `"stop"` navigation command if *any* center obstruction is detected under 0.60 meters (including `0.0m` sensor saturation close-up events).<br>• **Metronome Radar:** Shuts off the metronome ticks instantly when center depth falls below this limit. |
| **Path-Keeping & Steering Zone** | **$\le 0.80\text{ m}$** | • **Active Wall Avoidance:** If your center path is completely open, but you drift too close ($\le 0.80\text{ m}$) to the left staircase or right railing, the system actively prompts a corrective steer: `"turn right"` (for left structures) or `"turn left"` (for right structures). |
| **AI Warning & Side-Path Blockage** | **$\le 1.20\text{ m}$** | • **AI Warning Range:** Only whitelisted objects (such as your backpack obstacles) within 1.20m trigger active directional warnings.<br>• **Turning Safety Guard:** Side depth measurements under 1.20m mark that side path as blocked, preventing the AI steering engine from directing the user into side walls.<br>• **Immediate Spatial Report:** Button descriptions report objects in this range as actively blocking paths (e.g., *"student bag on center"*). |
| **Look-Ahead Preview Zone** | **$1.20\text{ m} \text{ to } 2.50\text{ m}$** | • Used solely by the manual **Spatial Reporter** (button press) to provide a helpful look-ahead warning of upcoming objects (e.g., *"desk further ahead on left"*) without triggering immediate automated steering alarms. |

---

## Part 2: Automated Navigation & Steering Cues (Category 2)

These directional prompts are processed automatically in real-time as you walk. They are designed to keep you safe and centered without overwhelming your ears.

### 1. Stop (Emergency Brake)
* 🎙️ *"stop"*
* **Trigger Conditions:**
  * Raw center depth drops below **$0.60\text{ meters}$** (`c_dist <= 0.60` or sensor saturates/returns `0.0`).
  * **OR** the center is blocked by an AI-detected object, and both the Left and Right paths are blocked (by AI objects or raw depth structures).
* **Priority & Cooldown:**
  * **High Priority:** Operated on a strict **2.0-second cooldown**.
  * **Process Interruption:** It immediately kills ongoing directional speech ("turn left", "turn right") instantly, clears the queue, and speaks `"stop"` to keep the user safe.

### 2. Left Steering Alert
* 🎙️ *"turn left"*
* **Trigger Conditions:**
  * Center is blocked by an AI object, left is open, and right is blocked.
  * **OR** center path is completely clear, but a wall or railing is detected on your right side within **$0.80\text{ meters}$** (wall avoidance).
* **Priority & Cooldown:**
  * **Normal Priority:** Operated on a **3.0-second cooldown**.
  * Can be interrupted instantly if the emergency `"stop"` is triggered.

### 3. Right Steering Alert
* 🎙️ *"turn right"*
* **Trigger Conditions:**
  * Center is blocked by an AI object, right is open, and left is blocked (such as your steps/vases).
  * **OR** center path is completely clear, but a concrete wall/staircase is detected on your left side within **$0.80\text{ meters}$** (wall avoidance).
* **Priority & Cooldown:**
  * **Normal Priority:** Operated on a **3.0-second cooldown**.
  * Can be interrupted instantly if the emergency `"stop"` is triggered.

---

## Part 3: On-Demand Spatial Reports (Category 3 - Button Press)

These are descriptive, grouped sentences generated dynamically when you press the physical button or key. 

* **The Interruption Rule:** Instantly cuts off any active directional steering alerts ("turn left", "turn right") to speak your requested environment description.
* **The Safety Lock Rule:** While speaking your report, the automated steering engine is **silently locked** (`spatial_report_active = True`) so that the detailed description is never interrupted by automated navigation stops or turns. Normal alerts resume the moment the report finishes speaking.

### 1. Supported Nouns (Whitelisted Classes)
* `"student"` (YOLO `"person"`)
* `"student chair"` (YOLO `"chair"`)
* `"student bag"` (YOLO `"backpack"`)
* `"desk"` (YOLO `"dining table"`)
* `"umbrella"` (YOLO `"umbrella"`)
* `"books"` (YOLO `"book"`)
* `"water bottle"` (YOLO `"bottle"`)
* `"plant"` (YOLO `"potted plant"`)
* `"vase"` (YOLO `"vase"`)
* **`"obstruction"`** *(Generic fallback word used if a physical structure—like your steps, clay pots, or concrete columns—is detected strictly by depth and has no AI label).*

### 2. Clear Space Indicators
* **`"clear"`** *(Instead of "no obstacle" to keep commands direct and highly actionable).*

---

### Dynamic Phrase Combinations (How they sound in action)

Because of the modular, grouped-phrase architecture of the code, the system automatically and dynamically generates these exact expressions:

#### **A. All Paths Clear:**
* 🎙️ *"clear on left, center, and right."*

#### **B. Single-Zone Obstructions (e.g., just the steps on the left or bag on center):**
* 🎙️ *"**obstruction** on left, clear on center and right."*
* 🎙️ *"**obstruction** on center, clear on left and right."*
* 🎙️ *"**obstruction** on right, clear on left and center."*
* 🎙️ *"student bag on center, clear on left and right."*

#### **C. Multi-Zone Blocking (e.g., steps and nearby vases):**
* 🎙️ *"**obstruction** blocking both left and center, clear on right."*
* 🎙️ *"**obstruction** blocking both right and center, clear on left."*
* 🎙️ *"**obstruction** on left and right, clear on center."*
* 🎙️ *"student bag blocking both left and center, clear on right."*

#### **D. Absolute Path Blocking (e.g., facing a solid wall/dead end):**
* 🎙️ *"**obstruction** blocking all paths."*
* 🎙️ *"student bag blocking all paths."*

#### **E. Look-Ahead Previews (e.g., steps or bags further away in the distance):**
* 🎙️ *"**obstruction** further ahead on left, clear on center and right."*
* 🎙️ *"**obstruction** further ahead on center, clear on left and right."*
* 🎙️ *"**obstruction** further ahead on right, clear on left and center."*
* 🎙️ *"student bag further ahead on left, clear on center and right."*
* 🎙️ *"student bag further ahead on left and right, clear on center."*
* 🎙️ *"student bag further ahead on left, center, and right."*
