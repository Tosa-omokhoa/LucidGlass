# LucidGlass

Train a real machine learning model on your CSV, right in your browser. No upload, no server, no code, and your data never leaves your device.

**Live demo:** _add your Vercel link here once deployed_

## What it is

Most people who work with data every day cannot write code. LucidGlass closes that gap. Upload a CSV, see your data, pick what you want to predict, pick an algorithm, hit train. You get accuracy, feature importance, and a plain English explanation of what the model found. Everything runs entirely client side.

Every competing tool in this space, Google AutoML, SageMaker Canvas, Obviously.ai, requires uploading your data to their cloud. For HR data, financial records, client information, or health data, that is a hard blocker. LucidGlass never sends a single row anywhere. The entire pipeline, parsing, training, and prediction, runs in JavaScript in your own browser tab.

## Features

- **Drag and drop CSV upload** with automatic column type detection (numeric, categorical, boolean, date)
- **A magnifying column rail** for browsing columns without a wide overflowing table
- **A data health score** flagging missing values, duplicate rows, and heavily imbalanced columns before you even pick a target
- **Four real algorithms**, K Nearest Neighbors, Decision Tree, Random Forest, and Logistic Regression for classification, plus Linear Regression for continuous targets, all implemented from scratch in vanilla JavaScript
- **Automatic target suitability detection**, warning you when a column looks like a continuous number rather than a fixed set of categories, and switching to regression accordingly
- **Compare mode**, training two algorithms on an identical train and test split and showing results side by side
- **Data Insights**, a full exploratory view with per column statistics, histograms, a correlation grid, and plain English observations about what stands out in the dataset
- **Plain English summaries** after every training run, explaining what the model actually found in ordinary language
- **One page PDF export** for both training results and data insights, built entirely client side with jsPDF
- **Light and dark mode**, both designed around a frosted glass visual language

## Tech stack

Plain HTML, CSS, and JavaScript. No framework, no build step, no backend. PapaParse handles CSV parsing, jsPDF handles PDF export. Every ML algorithm, KNN, Decision Tree, Random Forest, Linear Regression, and Logistic Regression, is a from scratch implementation, no ML library dependency.

## Running locally

Clone the repo and open `index.html` directly in a browser. That's the entire setup.

```bash
git clone https://github.com/Tosa-omokhoa/LucidGlass.git
cd LucidGlass
open index.html
```

## Project structure

```
LucidGlass/
  index.html       the current, deployed version of the app
  prototypes/       the phase by phase build history, phase 1 through phase 5
  docs/             design notes and planning
  assets/           logo and design system references
```

## How it was built

LucidGlass was built in phases rather than all at once.

1. **Design system.** Color tokens, type scale, and the frosted glass component language, before any ML logic existed.
2. **Core loop.** CSV upload, column detection, target selection, KNN and Decision Tree, results with feature importance.
3. **Explainability.** Plain English summaries, confidence indicators, Linear and Logistic Regression, PDF export.
4. **Depth.** Random Forest, an expanded sample dataset library, and the data health score.
5. **Data Insights.** A full exploratory data view independent of any target or model.
6. **Comparison mode and refinement.** Side by side algorithm comparison, mobile layout fixes, and launch polish.

## License

MIT, see [LICENSE](LICENSE).

## Author

Built by Omokhoa Oshose Tosayoname.

- GitHub: [Tosa-omokhoa](https://github.com/Tosa-omokhoa)
- LinkedIn: [oshose-omokhoa](https://linkedin.com/in/oshose-omokhoa-3982aa364)
- Twitter/X: [@Tosa_omokhoa](https://twitter.com/Tosa_omokhoa)
