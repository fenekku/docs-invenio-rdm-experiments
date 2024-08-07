# Try InvenioRDM

You can quickly try InvenioRDM to see if it's for you through a few different means.

## Zenodo

You can interact and visit zenodo.org. Zenodo is built on InvenioRDM. It has some customizations specific to its use case, but it's the most well-known instanceo of InvenioRDM.

## InvenioRDM demo site

The InvenioRDM project also hosts a demo site here: https://inveniordm-qa.web.cern.ch/ . This is a generic out-of-the-box instance of InvenioRDM. It usually runs the latest release for demo purposes. It's frequently reset, but that is also a benefit as it allows you to try things in an environment that is not permanent.

## Containerized installation

It's possible to install InvenioRDM locally two ways. The containerized and development approach. Although both approaches do use containers, the containerized approach goal is to let you preview InvenioRDM by making it possible to install an instance that runs completely in containers thus mitigating the need to install dependencies or modify your own environment. There are even projects in the community that aim to simplify to its strict minimum.

Walkthrough previewing InvenioRDM this way in this section (TODO: extract containerized approach separately).

### Steps

Run

```shell
invenio-cli containers start --lock --build --setup
```

and get an instance of InvenioRDM running on https://localhost .

## Conclusion

All these methods give you a quick sense for what InvenioRDM has to offer from different perspectives. Take InvenioRDM for a spin and see if it has what you are looking for!
