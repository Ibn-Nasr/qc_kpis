# Hassan's Monthly KPIs

A static KPI dashboard hosted on GitHub Pages. You log each day, and the page adds the days up into monthly KPIs.

**Per issue** (one row per issue and action, with issue number, type, module, and for tests the stage — MR, Dev or Main — and result):

- Issues created, developed, tested and re-tested (each counts distinct issues per month)
- Test pass rate = passed test rounds ÷ all test rounds (tested and re-tested)
- Review rounds = how many times an issue was tested or re-tested
- Test cases run per issue (entered on each Tested / Re-Tested row)
- Issue types (bug / feature / enhancement) and modules worked in

**Per day:**

- Bugs found, by severity (Critical, High, Medium, Low) and where they were found (MR, Dev, Main)
- Test cases executed: manual (Regression, MR, Dev, Main) and automation, with failed and blocked/skipped counts
- Test cases written: manual cases and automation scripts
- Bugs per 100 cases = bugs found ÷ test cases executed × 100
- Meetings attended, split into support, internal, integration and client
- Integrations worked on

You can set optional monthly targets for created, developed, tested, re-tested, meetings, pass rate and test cases in the owner panel.

All data lives in `data.json` in this repository. Every save from the page is a commit, so the git history is also a backup of your data.

## 1. Create the repository

1. On github.com, create a new **public** repository, e.g. `kpis`.
2. Upload `index.html`, `data.json` and this `README.md` to the root of the `main` branch.

## 2. Turn on GitHub Pages

1. In the repository, open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, then pick branch `main` and folder `/ (root)`. Save.
3. After a minute or so, the site is live at `https://<your-username>.github.io/kpis/`.

## 3. Create a token so only you can save

1. Go to **GitHub → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. **Repository access:** Only select repositories → pick `kpis`.
3. **Permissions → Repository permissions → Contents:** Read and write. Leave everything else as it is.
4. Pick an expiry date (for example, 1 year), generate the token, and copy it.

## 4. Sign in on the dashboard

1. Open the site and click **Owner sign-in** at the bottom right.
2. Paste the token. The repository and branch fill in automatically on GitHub Pages.
3. Click **Sign in**. The **Log a day** form appears at the top.

The token is saved only in that browser. Sign in once on each device you use (laptop, phone). Never commit the token to the repository.

## Daily routine

Open the site and click **Today**. Add one row per issue: its number, type, what you did (created, developed, tested or re-tested), the stage (MR, Dev or Main) and result if you tested or re-tested it, and the module. Then fill in the bugs grid (severity × MR/Dev/Main), the test cases you executed, and meetings, tap the integrations you worked on, and click **Save day**. When you type an issue number you've logged before, its type and module fill in automatically. To fix a day, click it in the daily log. Visitors see the change about a minute later, once Pages redeploys.

## Notes

- The data is public. Anyone with the link can read `data.json`.
- If the token expires, the page signs you out with a message. Create a new token and sign in again.
- **Export issues CSV** and **Export days CSV** in the owner panel download your data as spreadsheet files.
- Keep your existing `data.json` when updating `index.html`. Older entries still load.
