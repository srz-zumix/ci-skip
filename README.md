# ci-skip

CI skip commit meesage
--------------------------------------------------

|CI|Status|[ci skip]|[skip ci]|other|custom|
|:--|:--|:--|:--|:--|:--|
|[AppVeyor](https://www.appveyor.com/docs/how-to/filtering-commits/#skip-commits)|[![Build status](https://ci.appveyor.com/api/projects/status/yagkbieyahgxx7cd?svg=true)](https://ci.appveyor.com/project/srz-zumix/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|[skip appveyor]| [doc](https://www.appveyor.com/docs/how-to/filtering-commits/#skip-commits) |
|[Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/build/triggers?view=azure-devops&tabs=yaml#skipping-ci-for-individual-commits)|[![Build Status](https://dev.azure.com/srz-zumix/ci-skip/_apis/build/status/ci-skip-CI)](https://dev.azure.com/srz-zumix/ci-skip/_build/latest?definitionId=6)|:ballot_box_with_check:|:ballot_box_with_check:|skip-checks: true, \*\*\*NO_CI\*\*\*,<br> [skip KEYWORD] or [KEYWORD skip]<br> (KEYWORD: azurepipelines, azpipelines, azp)|[workaround](https://github.com/Microsoft/azure-pipelines-agent/issues/858#issuecomment-457027046)|
|[Bitrise](http://devcenter.bitrise.io/tips-and-tricks/skip-a-build/)|[![Build Status](https://app.bitrise.io/app/888b3fc92ca7352c/status.svg?token=1zo_JkiGKmgbqRGxtLdieQ&branch=master)](https://app.bitrise.io/app/888b3fc92ca7352c)|:ballot_box_with_check:|:ballot_box_with_check:|||
|[Buddy](https://buddy.works/knowledge/deployments/how-use-commit-commands)|[![buddy pipeline](https://app.buddy.works/zumixcpp/ci-skip/pipelines/pipeline/127277/badge.svg?token=5e58135ab4831252209e7b1fe75bfe9de669b0dc7e95ed4316eebad2187d59a0 "buddy pipeline")](https://app.buddy.works/zumixcpp/ci-skip/pipelines/pipeline/127277)|:x:|:x:|--skip||
|[Circle CI](https://circleci.com/docs/1.0/skip-a-build/)|[![CircleCI](https://circleci.com/gh/srz-zumix/ci-skip/tree/master.svg?style=svg)](https://circleci.com/gh/srz-zumix/ci-skip/tree/master)|:ballot_box_with_check:|:ballot_box_with_check:| | |
|[Cirrus CI](https://cirrus-ci.org/guide/writing-tasks/#conditional-task-execution)|[![Cirrus Build Status](https://api.cirrus-ci.com/github/srz-zumix/ci-skip.svg?branch=master)](https://cirrus-ci.com/github/srz-zumix/ci-skip/master)|:ballot_box_with_check:|:ballot_box_with_check:| | |
|[Codefresh](https://docs.codefresh.io/v1.0/docs/conditional-execution-of-steps)|[![Codefresh build status]( https://g.codefresh.io/api/badges/build?repoOwner=srz-zumix&repoName=ci-skip&branch=master&pipelineName=ci-skip&accountName=srz-zumix&type=cf-1)]( https://g.codefresh.io/repositories/srz-zumix/ci-skip/builds?filter=trigger:build;branch:master;service:5a8d6d36d78094000162db49~ci-skip)|:x:|:x:||[doc1](https://docs.codefresh.io/docs/build-1), [doc2](https://docs.codefresh.io/docs/handling-commit-messages-with-quotes)|
[Codeship](https://documentation.codeship.com/general/projects/skipping-builds/)|[ ![Codeship Status for srz-zumix/ci-skip](https://app.codeship.com/projects/00a08490-f92d-0135-3ab5-029b8e2f450f/status?branch=master)](https://app.codeship.com/projects/278452)|:ballot_box_with_check:|:ballot_box_with_check:|--skip-ci,--ci-skip||
|[Drone Cloud](https://cloud.drone.io/)|[![Build Status](https://cloud.drone.io/api/badges/srz-zumix/ci-skip/status.svg)](https://cloud.drone.io/srz-zumix/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|\*\*\*no_ci\*\*\*|[code](https://github.com/drone/drone/blob/master/trigger/skip.go#L61:L71)|
|[GitHub Actions](https://github.com/features/actions)|[![GitHub Actions Status](https://github.com/srz-zumix/ci-skip/workflows/GitHub%20Actions/badge.svg?branch=master)](https://github.com/srz-zumix/ci-skip/actions)|:x:|:x:||[workaround](./docs/github/WORKAROUND.md)|
|[Peakflow](https://www.peakflow.io/en/faq)|[![Peakflow Build Status](https://www.peakflow.io/en/projects/ci-skip/branch-statuses/master.svg)](https://www.peakflow.io/en/projects/ci-skip/build-groups?build_groups_q%5Bbranch_name_cont%5D=master)|:x:|:x:||
|[Rocro (INSPECODE)](https://rocro.com/)|[![Job Status](https://inspecode.rocro.com/badges/github.com/srz-zumix/ci-skip/status?token=8V-M4dzbmfp7kXb7GgbTPuRnUZEXNJDqJby9hQ0IX9E)](https://inspecode.rocro.com/jobs/github.com/srz-zumix/ci-skip/latest?completed=true)|:x:|:x:||
|[Scrutinizer](https://scrutinizer-ci.com/docs/guides/skipping_a_build_via_commit_message)|[![Build Status](https://scrutinizer-ci.com/g/srz-zumix/ci-skip/badges/build.png?b=master)](https://scrutinizer-ci.com/g/srz-zumix/ci-skip/build-status/master)|:ballot_box_with_check:|:ballot_box_with_check:|||
|[Semaphore CI](https://semaphoreci.com/docs/how-to-skip-building-for-some-commits-with-ci-skip.html)|[![Build Status](https://semaphoreci.com/api/v1/srz_zumix/ci-skip/branches/master/badge.svg)](https://semaphoreci.com/srz_zumix/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|||
|[Semaphore CI 2.0](https://docs.semaphoreci.com/article/146-skip-building-some-commits-with-ci-skip)|[Build](https://srz-zumix.semaphoreci.com/projects/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|||
|[Shippable](http://docs.shippable.com/ci/skip-builds/)|[![Run Status](https://api.shippable.com/projects/5a8d7f96d0386507000fbc70/badge?branch=master)](https://app.shippable.com/github/srz-zumix/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|||
|[Travis CI](https://docs.travis-ci.com/user/customizing-the-build/#skipping-a-build)|[![Build Status](https://travis-ci.com/srz-zumix/ci-skip.svg?branch=master)](https://travis-ci.com/srz-zumix/ci-skip)|:ballot_box_with_check:|:ballot_box_with_check:|[skip KEYWORD] or [KEYWORD skip]<br> (KEYWORD: ci, travis, travis ci, travis-ci, or travisci)| |
|[wercker](http://devcenter.wercker.com/docs/faq/how-can-i-skip-a-build#hs_cos_wrapper_name)|[![wercker status](https://app.wercker.com/status/95dc13c5815e10848c9c7bafbba37e62/s/master "wercker status")](https://app.wercker.com/project/byKey/95dc13c5815e10848c9c7bafbba37e62)|:ballot_box_with_check:|:ballot_box_with_check:| | |

Only the head/last commit message is checked
--------------------------------------------------

* Travis CI  
Travis CI is build with all commit, If you are only interested in building the most recent commit you can use [Auto Cancellation](https://docs.travis-ci.com/user/customizing-the-build/#Building-only-the-latest-commit).  
Commit of the skip comment is not queued, so the previous commit will not be auto canceled.
* Other than  
If you push more than one commit, only the last ("head") commit's message will be checked for the skip ci pattern!

Whether the skip build remains in the history
--------------------------------------------------

|CI|YES/NO|
|:--|:--|
|[AppVeyor](https://www.appveyor.com)|NO|
|[AzurePipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/)|NO|
|[Bitrise](https://www.bitrise.io)|NO|
|[Buddy](https://buddy.works)|YES (Activity Log)|
|[Circle CI](https://circleci.com)|YES (Status SKIPPED)|
|[Cirrus CI](https://cirrus-ci.org/)|YES (Status SKIPPED)|
|[Codefresh](https://codefresh.io/)|YES (Status SUCCESS)|
|[Codeship](https://codeship.com/)|NO|
|[Drone Cloud](https://cloud.drone.io/)|NO|
|[GitHub Actions](https://github.com/features/actions)|NO|
|[Peakflow](https://www.peakflow.io/)|--|
|[Rocro](https://rocro.com/)|--|
|[Scrutinizer](https://scrutinizer-ci.com)|NO|
|[Semaphore CI](https://semaphoreci.com)|NO|
|[Semaphore CI 2.0](https://semaphoreci.com)|NO|
|[Shippable](http://shippable.com)|NO|
|[Travis CI](https://travis-ci.com/)|NO|
|[wercker](http://www.wercker.com/)|NO|

Github commit status
--------------------------------------------------

https://github.com/srz-zumix/ci-skip/commits/master

