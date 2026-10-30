# Datux Labs

A minimal, editorial landing page built around the origin of the Datux name: data + UX. A short purpose statement introduces the parent company and its data-driven approach to continuously improving user experiences.

## Local preview

No dependencies or build step are required. From the repository root, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open <http://127.0.0.1:8000>. Stop the server with `Ctrl+C`.

## Files

- `index.html`: page content, metadata, and navigation.
- `styles.css`: responsive layouts, visual styling, keyboard focus, and reduced-motion support.

The page uses system fonts, native anchor navigation, and no JavaScript, remote assets, or tracking.

## Publishing

The site is published at <https://datux-labs.github.io/> using GitHub Pages. The publishing source is the `joshc-datux-labs-landing` branch, **/ (root)**. Pushing changes to that branch triggers a new deployment. No build configuration is needed.

The publishing source can be changed in the repository's **Settings > Pages**.

## Custom domain

Replace `example.com` below with your own domain.

1. Ideally, verify domain ownership in the Datux Labs organization's **Settings > Pages** first, using the TXT record GitHub supplies.
2. In the repository's [Pages settings](https://github.com/Datux-Labs/datux-labs.github.io/settings/pages), enter `example.com` under **Custom domain** and save **before** changing DNS. This creates a `CNAME` file on the publishing branch; keep that file in future updates.
3. At your DNS provider, add the records below. Replace conflicting website A, AAAA, or CNAME records for these hosts, but preserve unrelated records such as email MX and TXT records.

| Type | Host | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `datux-labs.github.io` |

4. Once GitHub's DNS check passes and the certificate is ready, enable **Enforce HTTPS** in Pages settings.

Use your provider's default TTL. DNS propagation and certificate provisioning can take up to 24 hours. With both root and `www` records configured, GitHub redirects `www.example.com` to the configured root domain. To prefer `www`, enter `www.example.com` as the custom domain instead.

For a different subdomain, such as `labs.example.com`, enter that full name as the custom domain and add a CNAME for `labs` pointing to `datux-labs.github.io`; root A records are not needed unless you also want to use the root domain. Do not use wildcard DNS records.

See [GitHub's custom-domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) for details.

Update the copy in `index.html` and the design tokens at the top of `styles.css` to customize the page.
