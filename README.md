# DRM Controller documentation

This project is the documentation source for Sphinx online documentation (https://drm-controller-documentation.readthedocs.io/en/latest/) of the DRM Controller IP.

When there is a push on this git repository, a build is automatically done on https://readthedocs.org/projects/drm-controller-documentation/builds/. If the build is "passed", a new versoin of "latest" version of documentation is automatically available online: https://drm-controller-documentation.readthedocs.io/en/latest/.

To be sure to be notified by any change on Algodone repository, apply email notifications when there is activity on the root documentation done on Algodone git: https://externalgit.plda.com/profile/notifications and set to "watch" for Algodone. It's allow to know when a documentation is necessary


## How to update documentation

The root documentation is coming from Algodone git repository: https://externalgit.plda.com/Algodone/DRM-Controller. Documentation is present on: https://externalgit.plda.com/Algodone/DRM-Controller/blob/BRANCH/docs/DOCUMENTATION.md and https://externalgit.plda.com/Algodone/DRM-Controller/blob/BRANCH/docs/RELEASE_NOTES.md .

When there is update of the DRM Controller repository (https://externalgit.plda.com/Algodone/DRM-Controller), we need to apply this modification on this current repository:
   - Use comparison between 2 commits: https://externalgit.plda.com/Algodone/DRM-Controller/compare
   - Get the 2 hash commits: https://externalgit.plda.com/Algodone/DRM-Controller/activity
   - Apply difference on https://github.com/xlz-jeydoux/DRM-Controller-documentation/tree/master/docs corresponding rst file(s) and images.


## How to write documentation in restructured text (.rst) format

To know how to witre documentation on restructured text (.rst) format, also, DRM integration documentation is a good reference project to see the differents aspects of the rst syntax: https://github.com/xlz-jeydoux/DRM-integration-documentation/blob/master/docs/index.rst.

Online rst preview and syntax verification: http://rst.ninjs.org/# 

Rst syntax: http://openalea.gforge.inria.fr/doc/openalea/doc/_build/html/source/sphinx/rest_syntax.html

## Documentation version management

When you create a tag on this git repository to release a new documentation version, this new version must be activated on  https://readthedocs.org/projects/drm-controller-documentation/versions:
   - Check: https://readthedocs.org/projects/drm-controller-documentation/versions/ that the new tag version exist.
   - You can now set the version "active":
      - click on "edit"
      - click on "Active"
Now the version is available online with link: https://readthedocs.org/dashboard/drm-controller-documentation/version/vX.Y.Z/




