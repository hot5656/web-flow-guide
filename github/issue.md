# GitHub issue

*   [Root](../README.md)
*   [1. A dependency defined in package-lock.json has known security vulnerabilities and should be updated](#a1)

<h2 id="a1">1. A dependency defined in package-lock.json has known security vulnerabilities and should be updated</h2>

package-lock.json hoek known security vulnerabilities 2.16.3
### npm ls hoek
```
C:\work\git\html\github\bootstrap-custom-build>npm ls hoek
customize@1.0.0 C:\work\git\html\github\bootstrap-custom-build
`-- node-sass@4.9.1
  `-- node-gyp@3.7.0
    `-- request@2.81.0
      `-- hawk@3.1.3
        +-- boom@2.10.1
        | `-- hoek@2.16.3  deduped
        +-- hoek@2.16.3
        `-- sntp@1.0.9
          `-- hoek@2.16.3  deduped
```
### npm install node-sass@latest



