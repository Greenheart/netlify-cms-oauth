<div align="center">
    <h3>
        Netlify CMS on Vercel
    </h3>
    <p>
        A simple OAuth2 serverless gateway for Netlify CMS
    </p>
</div>

---

## Why do I need this?

If you would like to use Netlify CMS to manage your site deployed to Vercel.

[GitHub](https://github.com) and [Gitlab](https://gitlab.com) requires a server for authentication and Netlify provides this server only for sites deployed to it. Fortunately, such server is rather small and can work with Vercel's serverless functions.

## Usage

In yours projects modify `config.yml` file:

```yaml
backend:
  name: [github | gitlab]
  repo: adrian-ub/adrian-ub # Path to your Github/Gitlab repository
  branch: main # Branch to update
  base_url: https://netlify-cms.adrianub.vercel.app
```

## Deploy

- Create Github OAuth App:
  - Go to [developer settings](https://github.com/settings/developers)
  - Set `Authorization callback URL` to your deployed oauth website's callback URL:
    `https://netlify-cms.adrianub.vercel.app/callback`
- Create Gitlab OAuth app:
  - Go to [User settings > Applications](https://gitlab.com/-/profile/applications)
  - Set `Redirect URI` to your deployed oauth website's callback URL:
    `https://netlify-cms.adrianub.vercel.app/callback`
- Set environment variables on `Vercel`

  ```shell
  OAUTH_GITHUB_CLIENT_ID=<you-client-id>
  OAUTH_GITHUB_CLIENT_SECRET=<you-client-secret>

  OAUTH_GITLAB_CLIENT_ID=<you-client-id>
  OAUTH_GITLAB_CLIENT_SECRET=<you-client-secret>
  ```

## Authors

- Adrián UB ([@AdrianUB](https://twitter.com/AdrianUB))
