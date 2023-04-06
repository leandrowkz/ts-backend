# Typescript node template
Typescript template for backend packages/apps. It provides a working set of
packages/resources ready to be used. Just put your code under `src` and you'll
be ready to go.

## Packages
- [Typescript](https://www.typescriptlang.org/)
- [TSConfig Paths](https://github.com/dividab/tsconfig-paths) (transform `import x from '@/sample'; @/ => src/`)
- [Node 19+](https://nodejs.org/dist/latest-v19.x/docs/api/)
- [NPM 7+](https://nodejs.org/dist/latest-v19.x/docs/api/)
- [Eslint](https://typescript-eslint.io) (typescript)
- [Prettier](https://prettier.io/) (on eslint)
- [Jest](https://jestjs.io/docs/getting-started) (with ts-jest)
- [Editorconfig](https://editorconfig.org/)
- [Husky hooks](https://typicode.github.io/husky/#/) (pre-commit lint and pre-push test hooks)
- [Semantic-release](https://semantic-release.gitbook.io/semantic-release/) (automatically publishes this repo on NPM)

## Automatic releases and publishing NPM package
This repo has all things necessary to be published as a public package on
[NPM](https://www.npmjs.com/). All you need to do is to:
1. Create a NPM access token (https://docs.npmjs.com/creating-and-viewing-access-tokens)
2. Create a repository secret called `NPM_TOKEN` with the value above
3. Create a Github personal access token (https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token#creating-a-personal-access-token-classic)
4. Create a repository secret called `GH_TOKEN` with the value above
5. That's it! Now every time a push/merge is made on branch `main` a release pipeline will run,
   building the application, generating a new tag to the repo, bumping `package.json` version on
   branch `main` according to the last commit change (check the `.releaserc.js`) and publishing this
   to NPM, according to the config set on `package.json` `publishConfig`.

## Conventional commits
This repo uses [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) to standardize
commit messages. This is also necessary for the release/publish step. Make sure you use it on your
work, or let the `pre-commit` hook validate it for you.
