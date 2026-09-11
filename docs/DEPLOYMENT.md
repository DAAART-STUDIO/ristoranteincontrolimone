# Deployment

## Deployment Model

Ristorante Incontro Limone is a static website built with HTML, CSS and vanilla JavaScript ES modules.

There is no build step.

The website can be deployed by serving the project files directly over HTTPS.

---

## Repository

```text
https://github.com/DAAART-STUDIO/ristoranteincontrolimone
```

Production/deployment branch:

```text
main
```

The `main` branch is the current deployment source.

---

## Hosting — GitHub Pages

The project is configured for static deployment through GitHub Pages.

The intended GitHub Pages configuration is:

1. Open the repository **Settings → Pages**.

2. Under **Build and deployment → Source**, select:

   **Deploy from a branch**

3. Configure:

   **Branch:** `main`
   **Folder:** `/ (root)`

4. Save the configuration.

5. The project is served from the repository's GitHub Pages URL.

Current project URL:

```text
https://daaart-studio.github.io/ristoranteincontrolimone/
```

6. A new push to `main` triggers a GitHub Pages deployment.

Deployment may take some time to become available after a new push.

---

## Project-Subpath Constraint

The current GitHub Pages deployment uses the project subpath:

```text
https://daaart-studio.github.io/ristoranteincontrolimone/
```

The website therefore does not run at the domain root.

Asset and internal resource references should remain **relative**.

Preferred:

```html
<link rel="stylesheet" href="css/base.css">
<script type="module" src="js/app.js"></script>
<img src="assets/images/example.webp" alt="">
```

Avoid root-relative paths:

```html
<link rel="stylesheet" href="/css/base.css">
<script type="module" src="/js/app.js"></script>
<img src="/assets/images/example.webp" alt="">
```

Root-relative paths resolve from the domain root and can result in broken resources when the project is deployed under `/ristoranteincontrolimone/`.

Keep paths compatible with the current GitHub Pages project-subpath deployment.

---

## Custom Domain

A custom domain may be configured when the production domain is ready.

The custom domain should be configured through:

**Repository → Settings → Pages → Custom domain**

DNS records must also be configured at the domain provider according to GitHub Pages requirements.

When a custom domain becomes the production URL, update all domain-dependent resources, including:

* `robots.txt`
* `sitemap.xml`
* canonical URL
* Open Graph URLs
* structured data
* `site.webmanifest`
* any absolute URLs used by the website

HTTPS should be enabled after the custom domain has been correctly configured.

---

## Deployment Checklist

Before deploying changes to `main`, verify:

### Content

* Restaurant name
* Address
* Telephone
* Email
* Opening hours
* Menu information
* Reservation information
* Location information

All restaurant-specific information must be verified before publication.

### Technical

* `index.html` loads correctly
* CSS files load correctly
* JavaScript modules load correctly
* JSON files load correctly
* Images load correctly
* SVG assets load correctly
* Navigation works
* Mobile navigation works
* Reservation interface works
* Language switching works
* Theme switching works
* Animations work
* Responsive layouts work

### SEO

Verify:

* page title
* meta description
* canonical URL
* Open Graph metadata
* structured data
* `robots.txt`
* `sitemap.xml`
* favicon
* web manifest

All production metadata must correspond to Ristorante Incontro Limone.

---

## Local Verification

Because the project uses JavaScript ES Modules, do not open `index.html` directly using `file://`.

Run a local HTTP server before deployment.

### Python

```bash
cd ristoranteincontrolimone
python -m http.server 8002
```

Then open:

```text
http://localhost:8002
```

Verify the website locally before pushing changes to `main`.

---

## Production Verification

After pushing changes to `main`:

1. Wait for GitHub Pages deployment to complete.
2. Open the live website.
3. Verify the homepage.
4. Test navigation.
5. Test mobile behavior.
6. Test language switching.
7. Test theme switching.
8. Test interactive sections.
9. Check the browser console for JavaScript errors.
10. Check the Network panel for failed resources or `404` responses.

---

## Production Branch Policy

The `main` branch is the deployment branch.

Development work should be tested locally before being pushed to `main`.

Avoid committing unfinished or experimental functionality directly to the deployment branch unless the change is intentionally part of the current development state.

---

## Deployment Integrity

The deployment must preserve the existing project architecture.

Do not introduce a build process, frontend framework or deployment dependency unless explicitly required.

Before deployment, verify that:

* relative paths remain valid
* JavaScript ES Modules load correctly
* localized JSON files are available
* static assets are accessible
* responsive behavior remains intact
* existing interactions continue to work

---

## Privacy Note

GitHub Pages serves the frontend as static web resources.

Visitors can inspect the deployed HTML, CSS, JavaScript and other publicly served assets through browser developer tools or page source.

Repository visibility controls access to the GitHub repository itself and does not make already deployed frontend resources private.
