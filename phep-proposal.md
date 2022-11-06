```
PhEP {
        #id: 0,
        #type: #packaging,
        #title: 'Providing VMMaker-generated VM sources',
        #authors: [ 'Daniel Ziltener' ],
        #created: '2022-11-06'
}
```

# Abstract
A proposal to provide the VM sources generated by VMMaker as a download on files.pharo.org.

# Motivation
Packaging of Pharo for various platforms and distributions is currently hindered by the lack of a tarball of the VM sources; instead, the packagers have to generate them themselves using Pharo, create a tarball, and either host it somewhere or make it part of the respective package repository. It would be much simpler to have it readily available on files.pharo.org, especially for platforms without an officially provided VM binary, like the BSD OSes.

# Description
Implementation of this would mean to have the latest generated VM source on https://files.pharo.org/get-files/ in the sub-directory according to the VM version, ideally deployed by a CI/CD script; at the time of this writing, this would be deployed at https://files.pharo.org/get-files/90/pharo-vm-generated-source.zip for the stable Pharo9 VM. Packagers can then have their packaging scripts download and use that zip file to compile the VM.