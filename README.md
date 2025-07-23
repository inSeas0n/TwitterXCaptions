# 🚀 TwitterXCaptions

### A Gemini-Powered Content Workflow for *AFK Journey*

Welcome! This project uses the power of Gemini to automatically create engaging Twitter (X) captions. Just drop in an infographic, and Gemini will analyze it, write a great caption with descriptive alt text, and get it ready for you to post. ✨

---

## 🚀 Getting Started

Getting started is simple. Just follow these steps:

1.  **📥 Add Your Image**

    Place any new image you want to process (like a boss guide or event infographic) into the `1_input/images_to_process/` folder.

2.  **🤖 Run the Workflow**

    In your Gemini CLI, run the following command:

    ```bash
    execute commands from @2_workflow\main.md
    ```

    Gemini will read the `main.md` file and begin the automated workflow.

3.  **✅ Get Your Caption**

    Once the process is finished, you'll find the ready-to-use caption and alt text in the `3_output/latest_caption.md` file. The original image will be automatically moved to the `4_archive/processed_images/` folder.

---

## ⚙️ How It Works: The Magic Behind the Curtain

Curious about what Gemini is doing? Here’s the step-by-step process:

1.  **Checks for New Images**
    The workflow starts by looking for images in the `1_input/images_to_process/` directory. If it's empty, the process ends.

2.  **Avoids Repetition**
    To keep your content fresh, Gemini first checks the `4_archive/captions_log.md` to see which caption styles have been used recently and avoids using them again.

3.  **Analyzes the Image**
    This is the core of the magic. Gemini uses its vision capabilities to read all the text and understand the visuals directly from the image, ensuring the information is accurate.

4.  **Crafts the Caption**
    Using a library of templates (`2_workflow/caption_library.md`) and a set of content rules (`2_workflow/rules.md`), Gemini assembles a unique caption and detailed alt text tailored to the image.

5.  **Archives Everything**
    After the caption is created, the workflow logs the new caption and moves the processed image into the archive, keeping your workspace clean and organized.

---

## 📂 Project Structure

-   `1_input/`: Your starting point. Drop images here.
-   `2_workflow/`: The "brain" of the operation, containing the instructions and templates Gemini uses.
-   `3_output/`: Where you'll find the final, ready-to-post caption.
-   `4_archive/`: A record of everything that has been processed.
-   `5_references/`: Contains extra context about the game and audience to help Gemini make better captions.