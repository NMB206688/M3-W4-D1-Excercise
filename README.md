# M3-W4-D1-Excercise



# Week 4 Day 1 Homework

This homework involves practicing the use of LESS by converting a given CSS file into LESS. The goal is to apply LESS principles such as variables, nesting, imports, and mixins to create a modular, maintainable stylesheet.

## Project Structure

```
your-project-folder/
│
├── css/
│   ├── fonts.css
│   ├── responsive.css
│   ├── bootstrap.min.css
│   ├── racing.css
│
├── less/
│   ├── racing.less
│   ├── colors.less
│   ├── fonts.less
│   ├── mixins.less
│
├── index.html
└── ...
```

## Instructions

### Step 1: Create a New Repository

1. Go to GitHub and create a new repository named `m3-w4-d1-exercise`.
2. Clone this repository into your `WESTCLIFF` folder on your local machine using the command:

   ```bash
   git clone https://github.com/your-username/m3-w4-d1-exercise.git
   ```

### Step 2: Download and Set Up Files

1. Download the `wk4-day1-homework.zip` file from GAP Week 4 Day 1.
2. Unzip the file and move its content into the cloned repository folder.

### Step 3: Set Up Visual Studio Code

1. Open Visual Studio Code (VS Code).
2. Turn on auto-save by going to `File` > `Auto Save`.
3. Install LESS locally by running the command:

   ```bash
   npm install -g less
   ```

### Step 4: Create `fonts.css`

1. Navigate to the `css` folder in your project.
2. Create a new file named `fonts.css` and add the following content:

   ```css
   /*---------------------------------------------------------- Import Fonts -----------------------------------------------------------------*/
   @import url('https://fonts.googleapis.com/css2?family=Poppins:100,200,300,400,500,600,700,800,900&display=swap');
   @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&display=swap');
   ```

### Step 5: Update `index.html`

Make sure your `index.html` file includes a reference to the new `fonts.css` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/fonts.css">
    <link rel="stylesheet" href="css/racing.css">
</head>
<body>
    <!-- Your content here -->
</body>
</html>
```

### Step 6: Create LESS Files

1. In the `less` folder, create the following files:
   - `colors.less`
   - `fonts.less`
   - `mixins.less`

2. Add the following content to `colors.less`:

   ```less
   @primary-color: rgb(12, 1, 22);
   @secondary-color: rgb(102, 102, 102);
   @background-color: rgb(234, 231, 231);
   @highlight-color: rgb(207, 67, 79);
   @white-color: rgb(255, 255, 255);
   ```

3. Add the following content to `fonts.less`:

   ```less
   @primary-font: 'Poppins', sans-serif;
   @secondary-font: 'Syncopate', sans-serif;
   @font-size-base: 1em;
   @font-size-large: 2em;
   @font-size-medium: 1.2em;
   @font-size-small: 1em;
   @font-size-extra-large: 3em;
   @line-height-base: 1.80857;
   @line-height-large: 1.75em;
   ```

4. Add the following content to `mixins.less`:

   ```less
   .box-sizing {
       box-sizing: border-box !important;
   }

   .transition {
       transition: ease all 0.5s;
   }

   .font(@size, @weight, @family) {
       font-size: @size;
       font-weight: @weight;
       font-family: @family;
   }

   .text-center {
       text-align: center;
   }

   .bg-color(@color) {
       background-color: @color;
   }

   .padding(@top, @right, @bottom, @left) {
       padding-top: @top;
       padding-right: @right;
       padding-bottom: @bottom;
       padding-left: @left;
   }

   .width(@width) {
       width: @width;
   }
   ```

### Step 7: Create `racing.less`

In the `less` folder, create a file named `racing.less` and add the following content:

```less
@import "colors.less";
@import "fonts.less";
@import "mixins.less";

/*---------------------------------------------------------- Import Fonts -----------------------------------------------------------------*/
/* Moved to fonts.css */

/* Apply global styles */
* {
    .box-sizing();
    .transition();
}

body {
    .width(100%);
    height: 100%;
    color: @secondary-color;
    .font(@font-size-base, normal, @primary-font);
    line-height: @line-height-base;
    overflow: hidden;
}

.about_main {
    .collection_section {
        .width(100%);
        float: left;
        margin-top: 40px;

        .container {
            .new_text {
                .width(100%);
                float: left;
                .font(@font-size-large, normal, @primary-font);
                color: @primary-color;
            }

            .consectetur_text {
                .width(100%);
                float: left;
                .font(@font-size-medium, 400, @primary-font);
                color: @primary-color;
                margin-left: 0px;
                padding-bottom: 30px;
            }
        }
    }

    .collection_section_3 {
        .width(100%);
        float: left;
        padding-top: 0px;

        .container {
            .racing_shoes {
                .width(100%);
                float: left;
                .bg-color(@background-color);
                height: auto;
                padding-top: 70px;
                background-size: 100%;
                padding-bottom: 100px;
                margin-bottom: 100px;

                .shoes-img3 {
                    .width(100%);
                    float: left;
                    .text-center();

                    img {
                        margin-top: 4em;
                        width: 70%;
                    }
                }

                .sale_text {
                    .width(100%);
                    float: left;
                    .font(@font-size-extra-large, bold, @secondary-font);
                    .bg-color(@highlight-color);
                    .text-center();
                    padding: 30px 0px;
                }

                .number_text {
                    .width(100%);
                    float: left;
                    .font(@font-size-extra-large, normal, @primary-font);
                    color: @highlight-color;
                    line-height: @line-height-large;
                }

                .seemore {
                    .width(80%);
                    height: 50px;
                    .bg-color(@highlight-color);
                    color: @white-color;
                    .font(@font-size-medium, normal, @primary-font);
                    margin-top: 35px;
                    .text-center();
                }
            }
        }
    }
}

.copyright {
    .width(100%);
    float: left;
    color: @white-color;
    .text-center();
    .font(@font-size-small, normal, @primary-font);
    .bg-color(@highlight-color);
    padding: 10px 0px;
}
```

### Step 8: Compile the LESS File

Compile your LESS file into CSS by navigating to the project folder where the `less` folder is located and running:

```bash
lessc less/racing.less css/racing.css
```

### Submission

1. Push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Completed LESS conversion"
   git push origin main
   ```


---

This README file provides a comprehensive guide to setting up, organizing, and completing the homework assignment, ensuring that all steps are clearly explained and easy to follow. 