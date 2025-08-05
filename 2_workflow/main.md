# Dynamic Content Generation for Twitter (X) - v4.0 (Config-Driven)

This document outlines the optimized workflow for creating engaging, high-performing content. It leverages a central `config.json` file to manage caption components, rules, and anti-repetition data, making the process faster and more automated.

## 1. Initialization: Load Configuration

*   **Objective:** To load all necessary data and settings for the session.
*   **Action:** Read the `C:\TwitterXCaptions\2_workflow\config.json` file into memory.
*   **Outcome:** All caption components, angle definitions, hashtag rules, and anti-repetition history are ready for use.

## 2. Content Foundation: Image-First Context Protocol

To ensure captions are data-rich and contextually accurate, the following protocol will be executed for **each image** found in `C:\TwitterXCaptions\1_input`. This protocol can be run in parallel for multiple images.

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
    *   **Key Elements:** What are the crucial data points (e.g., number of teams, character names, core mechanics, data-heavy)?
*   **Outcome:** A clear, structured understanding of the image's content and purpose.

## 3. The Caption Crafting Engine (Automated)

This engine uses the data from the `config.json` and the image analysis to intelligently construct the caption.

### A. Automated Angle Selection

*   **Objective:** To choose the most contextually relevant angle for the caption.
*   **Action:** The system will automatically select an angle based on the image's content:
    *   If the image contains significant data/numbers -> **"The Data Analyst"**
    *   If the creator is a known community figure -> **"The Community Champion"**
    *   If the subject is a new boss/event -> **"The Hype Announcer"**
    *   Otherwise -> **"The Helpful Strategist"**
*   **Outcome:** A context-aware angle is chosen.

### B. Assemble the Caption

*   **Rule of Variation:** The system will automatically select a hook and CTA from the `config.json` that has been used least recently, based on the `antiRepetition` data.
*   **Action:** Dynamically combine components from the `config.json` based on the chosen angle.

### C. Apply Strategic Hashtags

*   **Action:** Apply the hashtag strategy as defined in the `config.json` file.

## 4. Advanced Alt Text Protocol

*   Generate descriptive, keyword-rich alt text based on the structured data synthesis.

## 5. Archiving and State Management

1.  **Log Caption:** Add the final caption and alt text to the end of `C:\TwitterXCaptions\4_archive\captions_log.md`.
2.  **Update Config:** Update the `antiRepetition` section in `config.json` with the hook and CTA used in the generated caption.
3.  **Move Processed Image:** Move the image file from `C:\TwitterXCaptions\1_input` to `C:\TwitterXCaptions\4_archive\processed_images`.

## 6. Execution Loop

This is the main execution process. It will run until no images are left in the input directory.

1.  **Check for Images:** List all files in the `C:\TwitterXCaptions\1_input` directory.
2.  **Termination Condition:** If the directory is empty, the workflow is complete. Stop execution.
3.  **Process Images:** Take all images from the list and process them (Steps 2-5 can be run in parallel).
4.  **Write Output:** Save the final generated caption and alt text to `C:\TwitterXCaptions\3_output\latest_caption.md`.
5.  **Loop:** Go back to Step 1.