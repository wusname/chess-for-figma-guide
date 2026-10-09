# Chess for Figma: Design Your Own Chess Set

**Play chess without leaving Figma.**

**Design your own chess set in Figma. Then play with it.**

A **Chess for Figma Design Kit** is an editable canvas template with twelve piece slots and one complete board. Importing takes a static snapshot of your artwork and puts it inside a playable Chess for Figma Widget. Your original kit stays editable. No external image hosting or separate accounts are needed.

This is the user and designer guide for **Chess for Figma 1.2 — Game Portability**, including Custom Set and Material Freedom.

**Design with gradients, textures, blends and richer Figma materials. Then play with them.** Chess for Figma works in Figma Design and FigJam; creating and importing your artwork happens in Figma Design.

## Game Portability

**Bring any chess game into Figma. Make it yours.**

Select your Widget and open **Game** in Figma Design or FigJam.

- **Load FEN:** Paste a chess position to start playing from there. FEN restores the position and turn, not earlier move history.
- **Load PGN:** Paste an ordinary game to restore its mainline and Score Sheet. Games with SetUp/FEN starting positions work too.
- **Copy FEN:** Copy the current position to take it elsewhere.
- **Copy PGN:** Copy the game, including any additional moves you played in Figma.

Imported games can continue normally on the canvas. Your Custom Set pieces, custom board, board size and Material Freedom appearance remain intact. Replacing a played game or imported position asks for confirmation; invalid input leaves the current game unchanged. Copying works locally without a chess-service account or connection.

PGN comments and alternative variations are not retained. The existing automatic draw rules still apply.

## Create a Design Kit

In a **Figma Design** file, open the Widget's palette action, **Custom set**, then choose **Create Design Kit**. Return to that same panel to import your finished kit.

The kit appears beside your work. It contains original editable vector pieces, an editable checkerboard, labels and safe-area guides. Use ordinary Figma tools to change them. Labels and guides are not part of the imported artwork.

## Design the Pieces

Each piece slot is **100 x 100**. Start with a centered **80 x 80 safe area**, leaving 10 units on each edge. This is a recommendation, not a style restriction. Geometric, illustrative, typographic and other static artwork are welcome; keep the roles readable at your chosen board size.

Keep the outer slot at 100 x 100. Scale or rotate the artwork inside it, not the slot itself. Transparent areas remain transparent. Keep strokes and effects inside the slot to avoid unexpected bounds. When Figma exports expanded bounds for overflowing artwork, the Widget fits it proportionally rather than stretching it to fill a square; the visible piece may become smaller.

Keep all twelve exact, lowercase slot names:

| White | Black |
| --- | --- |
| `white/pawn` | `black/pawn` |
| `white/knight` | `black/knight` |
| `white/bishop` | `black/bishop` |
| `white/rook` | `black/rook` |
| `white/queen` | `black/queen` |
| `white/king` | `black/king` |

Names inside a slot are entirely yours: `Face`, `Crown` or `My pawn` are all fine. Only the outer slot names are reserved. The slot name determines the chess role: artwork inside `white/pawn` still moves like a pawn, whatever you draw there.

## Design the Whole Board

`board/background` is **800 x 800**, covering the entire 8 x 8 board. Each logical square is **100 x 100**. The upper-left square is **a8**, and White starts at the bottom.

Replace the checkerboard with any static composition. You do not need to define separate light-square and dark-square colors. Keep board artwork within the 800 x 800 slot, with **Clip content** enabled. Do not rotate or resize that slot. Keep square boundaries understandable so players can read their moves.

The Widget adds last-move tint, selection outlines, legal-target dots/rings and check indication above your artwork. Coordinate labels sit outside the artwork on a neutral margin and are not customizable in 1.1. Flipping the board rotates its artwork 180 degrees and repositions the pieces; the pieces remain upright.

## Keep the Kit Structure

Keep the outer frame named **Chess for Figma Design Kit**. All thirteen named slots must sit directly inside it, exactly once each. Do not put the slots inside an extra `Pieces` folder. Additional labels or notes outside the slots are ignored.

The slots may be **Frames, Components or Instances**, with the required dimensions and visible artwork inside. The whole kit may also be a Frame, Component or Instance with the same structure. A Component Set is not a slot: put an instance of the desired variant inside a correctly named Frame instead.

Do not place playable Widgets, videos, embeds or other dynamic objects inside a slot. Keep the playable chess Widget outside the kit.

## Material Freedom

Use richer Figma materials in **both your pieces and your complete board**. The importer keeps artwork as SVG where that reliably preserves its appearance, and uses a static PNG snapshot for materials that need it. Your original kit stays editable.

| Material | What you play with |
| --- | --- |
| Vectors and solid fills | SVG artwork |
| Linear/radial gradients | SVG gradients |
| Masks and clipping | SVG masks/clipping when the other materials allow it |
| Ordinary drop/inner shadows and normal layer blur | Static SVG effects |
| Image/texture fills | Static PNG snapshot |
| Tiled image fills | Static PNG snapshot, retaining the repeated texture |
| Layer, paint and shadow blend modes | Static PNG snapshot |
| Angular/diamond gradients | Static PNG snapshot |
| Shader fills | A still PNG snapshot, not a live shader |
| Text | Outlined in SVG or flattened with a snapshot slot |
| Motion, video and animated image fills | Unsupported; use a deliberate still image instead |
| Native PATTERN paint | Unsupported; use tiled image fills or repeated vectors instead |

If any material in a slot needs a snapshot, the whole slot is flattened. The import result names those slots. Snapshots preserve appearance, **not live behavior**; they do not animate, stay linked to a shader, or let you choose a timeline frame.

Background/progressive blur, shader effects (rather than shader fills), noise/glass/texture effects and other unsupported advanced effects are rejected. Export a deliberate still PNG/JPG first when using those effects. Keep blend backdrops inside the same slot rather than relying on the kit background or outside layers.

Make sure Figma can display your fonts. External image links, scripts, animated SVG and arbitrary SVG styling are not supported. Errors leave the previous set and game unchanged.

## Import and Play

1. Select the complete Design Kit on the canvas.
2. Open **Custom set** from the target Widget's palette button, then choose **Import Design Kit**. If the kit is no longer selected, select it again while the small window stays open.
3. The importer checks all thirteen slots before replacing anything. An error names the slot to fix. If validation or export fails, your game and previous imported set stay unchanged.
4. After success, the Widget switches to **Custom** with the new artwork and keeps the current game. Choose **Done** and play normally.

The import window stays attached to the Widget that opened it while you select the kit. Import is a snapshot, not a live link: later edits to your kit appear in the game only after importing again. Your original components and instances are not changed by import.

## Scaling, Switching and Replacing

The same kit works at **Small, Medium, Large and Ridiculous**. These are playback sizes, not authoring dimensions. A 100 x 100 piece slot maps to one square; the 800 x 800 board maps to the whole board. Pieces fit proportionally and keep their aspect ratios. Snapshot pieces normally contain 200 x 200 pixels and the board 1600 x 1600; extreme zoom and Ridiculous size can look softer than SVG.

Choose **Club**, **Candy** or **Ink** in the theme menu to return to a built-in style. Your imported artwork stays stored. Choose **Custom** to bring it back.

To replace a set, edit your kit or select another complete kit and import again into the same Widget. To remove it, open **Custom set**, choose **Remove custom set**, then confirm **Remove**. This removes only the imported snapshot, not your canvas kit or game. One custom set is stored per Widget.

The artwork and visual choice belong to the shared Widget rather than to one person's view. Duplicating or copying a Widget carries the artwork with it, while the copied game can evolve independently. Deleting the source kit does not delete the imported snapshot. The original 1.0 set passed a creator-run full Figma Desktop quit/reopen test. For 1.1, textured sets also passed Design and FigJam file-close/reopen checks, with artwork and history retained.

## Keep It Responsive

Simple silhouettes and economical vector paths give the quickest play. The 1.1 textured example, covering all twelve pieces and the board, stored about **160 KiB** and took about **0.4 seconds** to export and validate. A dense angular-gradient board increased a mixed set to about **1.7 MB**. These are examples, not guarantees; each duplicate stores its own set.

Historical 1.0 vector examples on an Apple M4 Pro:

| Example | Stored artwork | Import export/validation time | Rendering/export check |
| --- | ---: | ---: | ---: |
| Simple original vectors and board | 17.8 KiB | about 0.9 seconds | about 0.6 seconds |
| Moderate: 384 extra ellipse details | 48.9 KiB | about 1.0 seconds | about 0.7 seconds |
| Heavy: 3,840 extra ellipse details | 328.8 KiB | about 2.6 seconds | about 13.6 seconds |

All three examples stored, rendered and duplicated successfully. These are examples, **not maximum sizes or speed guarantees**. The import timing excludes making the kit and preparing its export copy. The final column includes waiting for Figma and exporting a PNG, not just drawing on screen. The heavy example also took about 7.7 seconds in another run, so dense artwork can vary considerably. No hard storage-size limit was established.

The moderate example is a useful starting point for complexity. Thousands of tiny details, outlined text and embedded images can multiply the work each time pieces render. If play feels slow, simplify the source kit and import it again. Each copied Widget stores its own snapshot, so many large sets can increase file size.

## FigJam

Create and import in **Figma Design**, then copy the customized **Widget**, not just the kit, into FigJam. FigJam uses the stored artwork and does not need the source Frames or Components. Imported custom artwork has been tested rendering and playing moves in FigJam.

Theme switching and removing an imported set are available there. Creating or importing a Design Kit is Design-only. Game Portability, including both imports and both copy actions, works in FigJam as well as Figma Design.

## Shared-Canvas Play

Built for shared-canvas play: editors in the same file can take turns on the same board. Game and visual choices use Figma's synchronized state. Automated state checks are in place, but a live test with two separately authenticated editors was unavailable before 1.0 and remains a post-release verification item. We do not claim a completed two-editor native QA session.

## Scope

Static custom sets only. No Motion, animated SVG, online asset hosting, set marketplace, Community-sharing system, AI generation or chess variants. Your game remains ordinary chess: Custom Set changes its appearance, while Game lets you bring in a position or mainline game.

## Support

Questions or trouble importing a set? Contact [support@wusname.studio](mailto:support@wusname.studio).
