# Appleの「notarytool」を使用したアプリケーションの公証

Using Apple’s "notarytool" to Notarize Applications (Technical Note 25-01): Japanese edition.

Apple App Store以外で配布するmacOSアプリケーションは、Appleの公証（notarization）を受ける必要があります。このテクニカルノートでは、Appleの「notarytool」を使用して4Dアプリケーションを公証する手順を説明します。キーチェーンプロファイルの初回セットアップ、追加ファイルを含むアプリケーションへの署名、コマンド1つでの公証、コンパイル済みデータベースの署名、ログの確認、そしてステープルまでを扱います。

This technical note explains how to notarize 4D applications with Apple's `notarytool`: first-time keychain profile setup, signing applications that contain additional files, one-command notarization, signing compiled databases, checking the log, and stapling.

## Download

| | |
|---|---|
| PDF (Japanese) | [25-01_Notarization_ja.pdf](https://github.com/miyako/Notarization/releases/latest/download/25-01_Notarization_ja.pdf) |
| Original (English) | `document/25-01_Notarization.pdf` |

This technical note has no companion 4D demo project.

## Differences from the original

- The screenshots of the Build Application dialog (fig-01) and the two Gatekeeper alerts (fig-02, fig-03) are replaced with Japanese versions. The Big Sur alert (fig-02) is a generated image, not a screen capture.
- The Terminal screenshot (fig-04) is kept as is: `notarytool` prints its messages in English.
- The quoted alert messages in the text match the Japanese macOS wording.
- The technical note number is not repeated on the Japanese cover page.
- The table of contents is regenerated from the headings.

## Editing and rebuilding

The PDF is generated from plain-text sources. Edit them and run `make`.

| File | What |
|---|---|
| `src/ja.md` | Translated body text. **Don't touch code blocks** (`make check` verifies them). |
| `figures/fig-NN.ja.txt` | Text drawn in figure NN. Line N corresponds to line N of `fig-NN.en.txt`: an identical line keeps the original, an empty line erases it. (Not used in this note: all figures are screenshots.) |
| `figures/layout/fig-NN.json` | Per-label overrides for size, weight, alignment and position; `"replace"` uses a ready-made image (`figures/fig-NN-ja.png`) |
| `glossary.md` | Terminology |

```sh
make            # check → figures → build/25-01_Notarization_ja.pdf
make check      # code blocks unchanged, figure references complete
make review     # contact sheets of the figures (build/contact-N.png)
make release-assets
```

Requirements: Python 3, Google Chrome, CJK fonts, and Tesseract (only needed for re-extraction).
See the [localisation template](https://github.com/miyako/4d-technote-localisation-template) for the full workflow.

## Credits

- Original: Brianna Rentfrow, Technical Services Engineer, 4D Inc.
- Produced with [4d-technote-localisation-template](https://github.com/miyako/4d-technote-localisation-template) and GitHub Copilot.
