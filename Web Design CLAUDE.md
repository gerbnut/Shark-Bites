**\# CLAUDE.md — Frontend Website Rules**

**\#\# Always Do First**  
\- **\*\*Invoke the \`frontend-design\` skill\*\*** before writing any frontend code, every session, no exceptions.

**\#\# Reference Images**  
\- If a reference image is provided: match layout, spacing, typography, and color exactly. Swap in placeholder content (images via \`https://placehold.co/\`, generic copy). Do not improve or add to the design.  
\- If no reference image: design from scratch with high craft (see Anti-Generic Guardrails below).  
\- Do at least 2 screenshot comparison rounds. Stop only when no visible differences remain or user says so.

**\#\# Local Server**  
\- **\*\*Always serve on localhost\*\*** — never screenshot a \`file:///\` URL.  
\- Start the dev server: \`node serve.mjs\` (serves the project root at \`http://localhost:3000\`)  
\- \`serve.mjs\` lives in the project root. Start it in the background before taking any screenshots.  
\- If the server is already running, do not start a second instance.

**\#\# Screenshot Workflow (Playwright MCP)**  
Use the Playwright MCP tools directly — no custom scripts needed.

1\. \`browser\_resize\` → set to \`{ width: 1440, height: 900 }\` for desktop review  
2\. \`browser\_navigate\` → \`http://localhost:3000\`  
3\. \`browser\_take\_screenshot\` → analyze the image directly  
4\. Fix mismatches, repeat from step 3  
5\. Final pass: resize to \`{ width: 375, height: 812 }\` and verify mobile layout

**\*\*When comparing, be specific:\*\*** "heading is 32px but reference shows \~24px", "card gap is 16px but should be 24px"

**\*\*Check every pass:\*\*** spacing/padding, font size/weight/line-height, colors (exact hex), alignment, border-radius, shadows, image sizing, hover states

**\#\# Output Defaults**  
\- Single \`index.html\` file, all styles inline, unless user says otherwise  
\- Tailwind CSS via CDN: \`\<script src="https://cdn.tailwindcss.com"\>\</script\>\`  
\- Placeholder images: \`https://placehold.co/WIDTHxHEIGHT\`  
\- Mobile-first responsive

**\#\# Brand Assets**  
\- Always check the \`brand\_assets/\` folder before designing.  
\- If a logo is present, use it. If a color palette is defined, use those exact values — do not invent brand colors.  
\- Do not use placeholders where real assets are available.

**\#\# Anti-Generic Guardrails**  
\- **\*\*Colors:\*\*** Never use default Tailwind palette (indigo-500, blue-600, etc.). Pick a custom brand color and derive from it.  
\- **\*\*Shadows:\*\*** Never use flat \`shadow-md\`. Use layered, color-tinted shadows with low opacity.  
\- **\*\*Typography:\*\*** Never use the same font for headings and body. Pair a display/serif with a clean sans. Apply tight tracking (\`-0.03em\`) on large headings, generous line-height (\`1.7\`) on body.  
\- **\*\*Gradients:\*\*** Layer multiple radial gradients. Add grain/texture via SVG noise filter for depth.  
\- **\*\*Animations:\*\*** Only animate \`transform\` and \`opacity\`. Never \`transition-all\`. Use spring-style easing.  
\- **\*\*Interactive states:\*\*** Every clickable element needs hover, focus-visible, and active states. No exceptions.  
\- **\*\*Images:\*\*** Add a gradient overlay (\`bg-gradient-to-t from-black/60\`) and a color treatment layer with \`mix-blend-multiply\`.  
\- **\*\*Spacing:\*\*** Use intentional, consistent spacing tokens — not random Tailwind steps.  
\- **\*\*Depth:\*\*** Surfaces should have a layering system (base → elevated → floating), not all sit at the same z-plane.

**\#\# Hard Rules**  
\- Do not add sections, features, or content not in the reference  
\- Do not "improve" a reference design — match it  
\- Do not stop after one screenshot pass  
\- Do not use \`transition-all\`  
\- Do not use default Tailwind blue/indigo as primary color

