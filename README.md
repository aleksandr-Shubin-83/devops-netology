

1) Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

git show aefea                                                                                                                                                             
commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Jun 18 10:29:58 2020 -0400

    Update CHANGELOG.md
    
Ответ: 
  полный хеш: aefead2207ef7e2aa5dc81a34aedf0cad4c32545
  комментарий коммита: Update CHANGELOG.md


2) Какому тегу соответствует коммит 85024d3?

git show 85024d3            
commit 85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 5 20:56:10 2020 +0000

    v0.12.23

Ответ: 
  tag: v0.12.23

3) Сколько родителей у коммита b8d720? Напишите их хеши.

git show  b8d720                 
commit b8d720f8340221f2146e4e4870bf2ee0bc48f2d5
Merge: 56cd7859e0 9ea88f22fc

git log --pretty=%P -n 1 "b8d720"
56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b

Ответ:
  56cd7859e05c36c06b56d013b55a252d0bb7e158 
  9ea88f22fc6269854151c571162c5bcf958bee2b



4) Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

git show v0.12.23
tag v0.12.23
Tagger: TeamCity <teamcity@ip-192-168-0-113.us-west-2.compute.internal>
Date:   Thu Mar 5 20:56:10 2020 +0000

commit 85024d3100126de36331c6982bfaac02cdab9e76 (tag: v0.12.23)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 5 20:56:10 2020 +0000


git show v0.12.24
tag v0.12.24
Tagger: TeamCity <teamcity@ip-192-168-0-237.us-west-2.compute.internal>
Date:   Thu Mar 19 15:04:05 2020 +0000

commit 33ff1c03bb960b332be3af2e333462dde88b279e (tag: v0.12.24)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 19 15:04:05 2020 +0000


Ответ: Не уверен в правильности этого вопроса. сделал выборку всех коммитов между датами.
Смущает вопрос, что я не могу вообще найти  коммиты 33ff1c03bb960 и 85024d310012....

git log --since "MAR 5 2020 20:56:10" --until "mar 19 2020 15:04:05" --pretty=oneline
5f313a65ad5216e7d7df17e74a21b39bd41ba7c7 command: remove 0.12upgrade (#24403)
109c4bf6efb5c218d9186260976feca028e07e06 website: Remove links to the getting started guide's old location
420e22ece4d1cfee2dc8d5b837b09b4dc98cdd73 Update CHANGELOG.md
8c7a44355ba38d31ae5db3b0765079310ef424f9 command: Fix bug when using terraform login on Windows
fb7035ac3eca1488b0289156d77c058f9fc4d2ab Merge pull request #24364 from hashicorp/alisdair/013upgrade
ed1aebbedad34c902967b4401c10c2014307d539 terraform: large refactor to use Provider from configs.Resource (#24396)
176202b50213e70000831d07ea9453e6eee58ea8 Remove provider listing
3578a5d80aea766b6382b11b590b7c16b6ddefc3 state: update local unlock err (#24320)
a3529cb455cc8645e0480e7ed390f20d518899f1 vendor: Fix checksum for github.com/coreos/etcd (#24343)
8116b9c4934db5d62c1105f72e376d707f13ae2c Merge pull request #24389 from hashicorp/jbardin/module-expansion-getting-there
a8b9547e0d2e4e1d5b1e0919955b6e10f34eecbe fixup states.Resource change throughout packages
ef19fb6203cbc5733fa7c19d4c3334f38a9accc6 configs: attach provider fqn to Resource (#24382)
3b0b29ef52687f36000ffdf878c54751195bfac2 command: Add scaffold for 0.13upgrade command
d905b990a58e0b5d18b56e4abe5f67ae8aced557 s/GraphNodeResource/GraphNodeConfigResource/
a7de3d07b821dd9223ac3a34b88f61a020b7d629 cleanup from resource state mods
ea51b790bca31f05e6661a57fbfdfb7b3906cbf4 states.Resource needs to record its module too
3729e6a705b16943a4a2c252304601f3b1caf894 update MaybeFixUpResourceInstanceAddressForCount
f0e175a83559b6478e8cc8b7201aaa01561c1eee add AbsResource.Config() ConfigResource
42f7beff311306ab87562cd96053d72ebcc93cab Merge pull request #24296 from hashicorp/pselle/module-targetable
e6bac359edeba0d1dbbcd91263a03d22343ff636 Missing ConfigResource checks in TargetContains
e3ad9ffb779315d178aa18d1aba900427b952005 added module targetting tests
bf91bff2c896180b4e873576aa0d9ecd276feb2e TargetContains improvements
076c5400768edf249e2c78a4930bc8bb889f6587 Add a test for whole module targeting
7407fee9c20deab88e551791e44ed073c1281b10 Make modules targetable
50077eabe94079ede2255dfa92918cabe8ad090f Merge pull request #24362 from hashicorp/jbardin/module-expansion-some-more
d65bd64955873bd854d7abf7dcf40ebad3e5ba4b incorporate addrs.ConfigResource
9054716caf838e04723d131d56acba7766c490d6 implement addrs.ConfigResource
482ae66e18c62d4d2c5e1a2d2f4df7a0c14320ae minor cleanup
946eda3f3cf5066b41e1bab4442f5d7ddea79d72 configs: Return diagnostics (almost) directly from ParseProviderSourceString
a851566c56589a1e203d887bb7adbe001923c756 tfdiags: Diagnostics.ToHCL
1c78b260123778aba4f60a185aa535a88ea96636 terraform: provider source test (#24342)
4a1ec050927c3f924809d2de2ca244c4664d8d84 comment fixes
33464568e82ffdcbb02115ef2706bd38fd8cdaaa Merge pull request #24346 from hashicorp/jbardin/module-expansion-another-part
e13eecbc5bd1c54a36013c27e969b02eeee935cc finish provider ModuleInstance replacement
98cfb51f27ccaea1d578c68d294a79d6d2d3eefa convert /terraform to use new provider config
856791ec7e5a65b88b688635bfb0897adf1bb820 Merge pull request #24331 from hashicorp/jbardin/module-expansion-in-part
1252726cda50b5dc64f3225f7fea3e4bc30361c7 update CHANGELOG.md
f6221100ee0760403024cf99a2db4175223f7c83 Merge pull request #24149 from mlafeldt/fix-oss-state-locking
8497adcb6e9386f3b494e7d263699bb1ca778558 AbsProviderConfig to use addrs.Module
fae5f9958d2e18877d61c207cea9f2875ebbebef remove GraphNodeModuleInstance from Resource types
68b500c5c7a4fff5fc7316a2ff2a828941c57121 remove abs addrs from NodeAbstractResource
245296850b3f7dcd6a48cae4fe0a69ee7528e3f3 fix reference transformer comments
ab9a2935ced85ece918e2c960b677abaac15026a implement NodePlannableLocal
67e06f4fbe91f262e8035eca5cf2bbf97a9ca860 remove more UnkeyedInstanceShim
87776913c6e894307ba33c6784cbcaefe18fea80 nodeExpandModule doesn't need a Path() method
a104ecb69d284f2bfa55edd66d270bc499f71c1d GraphNodeExpand is not used
be2629d2f94c4e886d4ac9d0d3ee142a951eb4fe GraphNodeSubPath -> GraphNodeModuleInstance
215f60d5cfacde9ec57309979d088d1a10725293 remove module shims from module expansion nodes
6ae9013c3f14f7d77d79bfca500d1f2d3cc0e3d4 add addrs.Module.Equal
bd9cfca794660982928e370ca3a7dcdb26e14ad5 rename GraphNodeSubPath -> GraphNodeModuleInstance
b1df763541572663df98fc902e08d555cc5ad12a remove UnkeyedInstanceShim from ref transformer
521bdcc241a6cfa81577263ad2d1cffe734a514f implement GraphNodeModulePath
51bdcbb48cbc6c2b65ee81bf6642bbc95aaa27b4 Merge pull request #24341 from hashicorp/jbardin/cbd-test-fix
59019528824cae15d820aa8b3de9754623db2398 command: tests should not leave dirs behind thank you (#24340)
cb99dddb4d3d8f78c12cfd593290c5530c6a2666 fix a flapping test involving CreateBeforeDestroy
c7cc0afb803d6d7039f6c89e201669df068603d4 Mildwonkey/ps schema (#24312)
ca26efc5afe2144ee4116448c41d1e93b401166d Update CODEOWNERS
7bd00717191e1431c2491de82c36da108b44ff91 Update CODEOWNERS
40f251162991a5b94e12d2edce53759dd0b8a8b3 Merge pull request #24335 from hashicorp/cgriggs01-vmc-links
822f608a3c16ee4ed66295d345832689be218b68 [Website] vmc provider links
add16fc67b156b4bb47076bf78fcf70f74795e5c jsonstate: sort child modules by address for consistency (#24329)
ff3895ea26d65c9b2aae2efba075e7b5da5b34c4 Set Codecov threshold to 0.05% to avoid flicker
654e880bb8c2319f251f57e247627e422313c5b3 Merge pull request #24084 from hashicorp/jbardin/cbd-instance-state
3a079b04db0e9c839eb332e455b284f8e5f7e15c Change file permission ordering to avoid race condition
b95daa87c8500e86316b6ac8940fbf40f55d6ea2 Fix permissions of habitat provision's user.toml
94d7236cd4a056156a83b9b6b8bb68aec4eae0bf Merge pull request #24313 from hashicorp/alisdair/fix-coverage-blips-in-statemgr-filesystem
b948856cbbefd5482afec7160f5756c8b4a91799 fix typo
a77d5032d30c8d51c455f7739d63ee121d43a7f5 improve s3.html.md
1b5e2b70c6b113973d3dfe42a23810dcd4cd2d0d Update CHANGELOG.md
f54e2a62bfa36b6a4627ecf16d3c5a1fc592066b states: Fix coverage blips in statemgr/filesystem
6118d22c1f3d57047d51cba4e5fe4334d2aea1ac terraform: refactor ProvidedBy() to return an addrs.ProviderConfig interface (#24295)
e6592dc710be03307b2206bb245be11d37349a26 Add support for provider metadata to modules. (#22583)
4654b45d6b46d2a4fd43229e9bc9e51c538d7af0 Merge pull request #24298 from hashicorp/cgriggs01-website
6969da7d02b317326a898d9478767ca43def366f [Website] Update provider links


5) Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточия перечислены аргументы).

git log -S'func providerSource(' --oneline 
8c928e8358 main: Consult local directories as potential mirrors of providers
                                                                            
git show 8c928e8358                             
commit 8c928e83589d90a031f811fae52a81be7153e82f
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Thu Apr 2 18:04:39 2020 -0700

Ответ: commit 8c928e83589d90a031f811fae52a81be7153e82f

6) Найдите все коммиты в которых была изменена функция globalPluginDirs.

git log -S'globalPluginDirs' --oneline
125eb51dc4 Remove accidentally-committed binary
22c121df86 Bump compatibility version to 1.3.0 for terraform core release (#30988)
35a058fb3d main: configure credentials from the CLI config file
c0b1761096 prevent log output during init
8364383c35 Push plugin discovery down into command package

7) Кто автор функции synchronizedWriters?
git log -S'func synchronizedWriters(' --oneline
bdfea50cc8 remove unused
5ac311e2a9 main: synchronize writes to VT100-faker on Windows
                                                                                      
git show 5ac311e2a9                            
commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Wed May 3 16:25:41 2017 -0700

git show bdfea50cc8                         
commit bdfea50cc85161dea41be0fe3381fd98731ff786
Author: James Bardin <j.bardin@gmail.com>
Date:   Mon Nov 30 18:02:04 2020 -0500

Ответ: Функция впервые появилась в commit 5ac311e2a9 от May 3 16:25:41 2017, значит автором функции является Martin Atkins <mart@degeneration.co.uk>




