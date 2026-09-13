# Learn Myanmar Script

A lightweight, browser-based Myanmar handwriting learning and recognition application. Learners can browse Myanmar characters, practise drawing them on a canvas, and take a short quiz.

Handwriting inference runs entirely in the browser with [ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/). The ONNX graph and its external weights are fetched from the public Hugging Face model repository, while the static frontend is deployed with GitHub Pages.

## Links

- [GitHub repository](https://github.com/aungthuhein2005/learn-myanmar-script)
- [Hugging Face model](https://huggingface.co/aungthuhein-dev/myanmar-handwriting)
- [Live demo](https://aungthuhein2005.github.io/learn-myanmar-script/)

## Run locally

No build step or Python dependencies are required. From the repository root, start any static HTTP server, for example:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000/>. An internet connection is required for the Google font, ONNX Runtime Web, and model files.

## Model hosting

The frontend fetches these public files directly:

- `https://huggingface.co/aungthuhein-dev/myanmar-handwriting/resolve/main/model.onnx`
- `https://huggingface.co/aungthuhein-dev/myanmar-handwriting/resolve/main/model.onnx.data`

The model files are intentionally excluded from this Git repository. The code license in this repository does not make any claim about the licensing of the model or its training data; consult the model repository for those terms.

## Deployment

The workflow in `.github/workflows/deploy.yml` publishes the repository contents as a GitHub Pages artifact whenever `main` is updated. In the GitHub repository settings, set Pages **Source** to **GitHub Actions**.

## License

The frontend source code is licensed under the Apache License 2.0. See `LICENSE`.
