---
title: Problèmes avec le test de la topologie
TOCTitle: Problèmes avec le test de la topologie
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205045(v=OCS.15)
ms:contentKeyID: 49297905
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problèmes avec le test de la topologie

 

_**Dernière rubrique modifiée :** 2012-09-21_

Tout comme l’applet de commande **Test-CsTopology**, Best Practice Analyzer vous permet de vérifier que Lync Server 2013 fonctionne correctement au niveau global. Par défaut, Best Practice Analyzer, tout comme l’applet de commande, vérifie l’intégralité de votre infrastructure Lync Server 2013, en s’assurant que les services requis s’exécutent et que les droits de l’utilisateur et les autorisations appropriés ont été définis pour ces services et pour les groupes de sécurité universels créés lors de l’installation de Lync Server 2013.

Outre la vérification de la validité de Lync Server dans son ensemble, **Test-CsTopology** vérifie également la validité d’un service spécifique. Pour plus d’informations sur l’utilisation de l’applet de commande pour tester des services spécifiques, voir [Test-CsTopology](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTopology) dans la documentation Lync Server Management Shell. Utilisez les informations suivantes pour vous aider à résoudre les problèmes de topologie.

> [!NOTE]  
> En fonction de la configuration de vos serveurs Edge et des paramètres de réseau de périmètre associés, notamment les paramètres du pare-feu et les autorisations, Best Practices Analyzer peut ne pas être en mesure d’accéder à et d’analyser vos serveurs Edge. Si vous analysez les serveurs Edge et que les rapports indiquent un problème d’accès aux serveurs Edge, décochez <strong>Serveurs Edge</strong> et exécutez de nouveau l’analyse afin que cette erreur ne figure plus dans les rapports.

## Résolution des problèmes de topologie

Si des problèmes sont trouvés pendant le test de votre topologie, ils se sont probablement produits lors de la publication ou de l’activation de votre topologie.

Quand vous apportez des modifications à votre topologie, elles ne sont effectives que lorsque ces modifications ont été publiées et activées. Vous devez utiliser le Générateur de topologie pour apporter des modifications à la topologie. Une fois les modifications apportées, vous pouvez les publier et les activer à l’aide du Générateur de topologie.

Quand vous publiez les modifications, ces nouvelles informations (par exemple un nouveau site ou un nouveau rôle serveur) sont écrites dans le magasin central de gestion. Cependant, ces nouveaux objets (ou objets modifiés) ne rejoignent pas immédiatement votre topologie. Les objets rejoignent votre topologie uniquement quand vous activez la topologie mise à jour. Si vous sélectionnez l’option Publier dans le Générateur de topologie les deux étapes suivantes se produisent : les modifications sont publiées (c’est-à-dire, écrites dans le magasin central de gestion) et la nouvelle topologie est activée.

Par défaut, les membres du groupe RTCUniversalServerAdmins sont autorisés à exécuter l’applet de commande **Publish-CsTopology** et l’applet de commande **Enable-CsTopology**. Cependant, si les autorisations de configuration n’ont pas été déléguées, vous devez être administrateur du domaine pour exécuter **Publish-CsTopology**. Pour donner aux RTCUniversalServerAdmins le droit d’utiliser l’applet de commande **Publish-CsTopology**, vous devez exécuter l’applet de commande **Grant-CsSetupPermission** sur chaque conteneur Active Directory qui contient des ordinateurs exécutant les services Lync Server. Pour donner aux RTCUniversalServerAdmins le droit d’utiliser l’applet de commande **Enable-CsTopology**, vous devez exécuter l’applet de commande **Set-CsSetupPermission** sur chaque conteneur Active Directory Domain Services qui contient des ordinateurs exécutant les services Lync Server. Notez que cela s’applique à l’activation et à la publication d’une topologie avec le Générateur de topologie. Si vous n’avez pas délégué d’autorisations à l’aide de **Set-CsSetupPermission**, seul un administrateur du domaine peut activer et publier une topologie via le Générateur de topologie.

