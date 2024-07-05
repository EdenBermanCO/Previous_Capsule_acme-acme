This [Code Ocean](https://codeocean.com) Compute Capsule will allow you to run and reproduce the results of [Previous Capsule - acme-acme - Original](https://acmecorp-edge.codeocean.com/capsule/4080345/tree) on your local machine<sup>1</sup>. Follow the instructions below, or consult [our knowledge base](https://docs.codeocean.com/user-guide/compute-capsule-basics/managing-capsules/exporting-capsules-to-your-local-machine) for more information. Don't hesitate to reach out to [Support](mailto:support@codeocean.com) if you have any questions.

<sup>1</sup> You may need access to additional hardware and/or software licenses.

# Prerequisites

- [Docker Community Edition (CE)](https://www.docker.com/community-edition)

# Instructions

## Download attached Data Assets

In order to fetch the Data Asset(s) this Capsule depends on, download them into the Capsule's `data` folder:
* [hg38 Reference Sequence](https://acmecorp-edge.codeocean.com/data-assets/3d815b66-e4ad-475e-a535-0c955d23fd7a) should be downloaded to `data/Reference_1`

## Log in to the Docker registry

In your terminal, execute the following command, providing your password or API key when prompted for it:
```shell
docker login -u eden.berman@codeocean.com registry.acmecorp-edge.codeocean.com
```

## Run the Capsule to reproduce the results

In your terminal, navigate to the folder where you've extracted the Capsule and execute the following command, adjusting parameters as needed:
```shell
docker run --platform linux/amd64 --rm \
  --workdir /code \
  --volume "$PWD/code":/code \
  --volume "$PWD/data":/data \
  --volume "$PWD/results":/results \
  registry.acmecorp-edge.codeocean.com/capsule/794dc3ba-edd2-47c1-8aca-76868e5848a3 \
  bash run 4.4 b
```
