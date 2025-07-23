# Dynamic Content Generation for Twitter (X) - v3.0

This document outlines the primary workflow for creating engaging, high-performing content. It integrates with the `caption_library.md` and `rules.md` to produce varied and effective captions for each image found in the input directory.

## 1. Pre-Flight Check: Anti-Repetition Analysis

*   **Objective:** To ensure content freshness and avoid audience fatigue.
*   **Action:** Before analyzing a new image, review the last 5 entries in `C:\Twitter\4_archive\captions_log.md`.
*   **Analysis Points:**
    *   **Hook Repetition:** Identify the hooks used in recent posts.
    *   **CTA Repetition:** Identify the Calls to Action (CTAs) used.
*   **Outcome:** A list of recently used hooks and CTAs to be avoided for the current image.

## 2. Content Foundation: Image-First Context Protocol

To ensure captions are data-rich and contextually accurate, the following protocol will be executed for **each image** found in `C:\Twitter\1_input\images_to_process`. This protocol prioritizes direct image analysis to eliminate errors from filename or historical data reliance.

### **Step 1: Image Recognition and OCR**

*   **Objective:** To extract all textual and visual information directly from the image.
*   **Action:** Use the `read_file` tool on the target image.
*   **Outcome:** A detailed analysis of the image, including all recognized text (OCR) and visual elements.

### **Step 2: Contextual Synthesis**

*   **Objective:** To interpret the raw data from the image recognition step.
*   **Action:** Analyze the OCR output and visual description.
*   **Analysis Points:**
    *   **Primary Subject:** What is the main topic of the infographic (e.g., Boss name, event name)?
    *   **Creator Attribution:** Who created this guide (e.g., Yaphalla, inSeas0n)?
    *   **Key Elements:** What are the crucial data points (e.g., number of teams, character names, core mechanics)?
*   **Outcome:** A clear understanding of the image's content and purpose.

### **Step 3: Structured Data Output**

*   **Objective:** To create a structured summary for use in caption and alt text generation.
*   **Action:** Compile the synthesized information into a final, structured format.
*   **Outcome:** A machine-readable data block that will inform the rest of the workflow.

## 3. The Caption Crafting Engine

This engine uses the components from `C:\Twitter\2_workflow\caption_library.md` and the guidelines from `C:\Twitter\2_workflow\rules.md`.

### A. Define the Angle (Choose One)

*   The Hype Announcer
*   The Helpful Strategist
*   The Community Champion
*   The Lore Master
*   The Data Analyst

### B. Assemble the Caption

*   **Rule of Variation:** When selecting components (Hook, CTA, etc.), **do not** use any of the items identified in the "Anti-Repetition Analysis." If all items in a category have been used recently, select the one that was used least recently.
*   Dynamically combine components from the `caption_library.md` based on the chosen angle.

### C. Apply Strategic Hashtags

*   Apply the hashtag strategy as defined in `C:\Twitter\2_workflow\rules.md`.

## 4. Advanced Alt Text Protocol

*   Generate descriptive, keyword-rich alt text based on the structured data synthesis.

## 5. Archiving and File Management

1.  **Log Caption:** Add the final caption and alt text to the end of `C:\Twitter\4_archive\captions_log.md`.
2.  **Move Processed Image:** After all steps are complete for an image, move the image file from `C:\Twitter\1_input\images_to_process` to `C:\Twitter\4_archive\processed_images`. This prevents reprocessing and keeps the input directory clean.

## 6. Execution Loop

This is the main execution process. It will run until no images are left in the input directory.

1.  **Check for Images:** List all files in the `C:\Twitter\1_input\images_to_process` directory.
2.  **Termination Condition:** If the directory is empty, the workflow is complete. Stop execution.
3.  **Process First Image:** Take the first image from the list.
4.  **Execute Steps 1-4:** Perform the Anti-Repetition Analysis, Image-First Context Protocol, Caption Crafting, and Alt Text Protocol for the selected image.
5.  **Write Output:** Save the final generated caption and alt text to `C:\Twitter\3_output\latest_caption.md`.
6.  **Execute Step 5:** Perform the Archiving and File Management steps.
7.  **Loop:** Go back to Step 1.
