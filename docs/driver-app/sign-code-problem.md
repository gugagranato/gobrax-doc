---
sidebar_position: 1
---

# Problemas com código assinado

Galeres, bom dia. 

Descobri uma parada que, pra mim, é nova. 

Tive uma task que era pra integrar um repo em outro (assistent-virutal x driver-app). 

Mesmo o driver-app sendo a base pro app do assistente, ao fazer o merge, o código vem 'assinado'. 
Pelo que entendi ele só vai assinado, se você esteve logado no eas com contas distintas e gerou o build.
Ele funciona normal a maioria das coisas, só naõ funcionou a permissão de background e não gera build, mesmo local, e dá um erro genérico (ReferenceErrorV2 Stacktrace). 

Demorei até pra descobrir. 

E, claro, se eu tivesse feito da forma mais grotesca, copiando o arquivo e colando no outro repo, nada disso teria acontecido. 

Acontece que eu fiz isso aqui que segui de um tutorial: 

git remote add repo-do-assistente **URL do assistente**
git fetch repo-do-assistente
git checkout -b  repo-do-assistente
git merge repo-do-assistente/master


E, fazendo isso, o trem zangou. 

Então, caso precisem fazer algo do tipo, antes de fazer isso, criei um novo branch, deslogue do eas e limpe o apontamento do keystore, pq aí não acontece esse erro.

Só como informação mesmo, é nois. Bjus

## Create a docs version

Release a version 1.0 of your project:

```bash
npm run docusaurus docs:version 1.0
```

The `docs` folder is copied into `versioned_docs/version-1.0` and `versions.json` is created.

Your docs now have 2 versions:

- `1.0` at `http://localhost:3000/docs/` for the version 1.0 docs
- `current` at `http://localhost:3000/docs/next/` for the **upcoming, unreleased docs**

## Add a Version Dropdown

To navigate seamlessly across versions, add a version dropdown.

Modify the `docusaurus.config.js` file:

```js title="docusaurus.config.js"
module.exports = {
  themeConfig: {
    navbar: {
      items: [
        // highlight-start
        {
          type: 'docsVersionDropdown',
        },
        // highlight-end
      ],
    },
  },
};
```

The docs version dropdown appears in your navbar:

![Docs Version Dropdown](./img/docsVersionDropdown.png)

## Update an existing version

It is possible to edit versioned docs in their respective folder:

- `versioned_docs/version-1.0/hello.md` updates `http://localhost:3000/docs/hello`
- `docs/hello.md` updates `http://localhost:3000/docs/next/hello`
