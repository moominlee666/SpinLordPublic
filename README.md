# SpinLord GitHub Pages Package

This is a prebuilt static-site package. It intentionally contains no application source, package manager files, local environment files, or source maps. The Pages workflow deploys `dist/` directly and does not build from source.

## Publish

1. Create a new public GitHub repository with an empty history. Do not push this package into the old SpinLordRelease repository because its Git history contains the previous source files.
2. Upload the contents of this package to the new repository and use `main` as the default branch.
3. In **Settings > Pages**, set the build and deployment source to **GitHub Actions**.
4. Push to `main` or run **Deploy prebuilt site to GitHub Pages** from Actions.

## API and privacy

The built browser app calls its configured public API endpoint. A website must expose its API hostname and client code to visitors; these are not secrets. Do not put passwords, tokens, private upstream hostnames, or server credentials in this package or any `VITE_*` setting.

The API must allow the exact GitHub Pages origin, including OPTIONS requests and the required Authorization and Content-Type headers. GitHub Pages is static hosting and cannot proxy requests to hide an internal API. To keep an upstream host private, deploy a server-side proxy and rebuild the site to use that proxy's public endpoint.
