---
title: Déplacement des autres utilisateurs vers Lync Server 2013
TOCTitle: Déplacement des autres utilisateurs vers Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49891231
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des autres utilisateurs vers Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-26_

Vous pouvez déplacer les utilisateurs vers le nouveau déploiement de Lync Server 2013 à l’aide du Panneau de configuration Lync Server ou de Lync Server Management Shell. Vous devez vous assurer que certaines conditions requises sont remplies pour garantir une transition réussie vers Lync Server 2013. Pour plus d’informations sur les conditions requises liées à l’exécution des procédures de cette rubrique, reportez-vous à [Configuration des clients pour la migration](configure-clients-for-migration_1.md). Pour connaître en détail la marche à suivre pour déplacer des utilisateurs, reportez-vous à [Phase 6 : Déplacement des utilisateurs vers le pool pilote](phase-6-move-users-to-the-pilot-pool.md).

> [!IMPORTANT]  
> Vous ne pouvez pas utiliser le composant logiciel enfichable Utilisateurs et ordinateurs Active Directory ni les outils d’administration de Microsoft Office Communications Server 2007 R2 pour déplacer des utilisateurs depuis votre environnement hérité vers Lync Server 2013.

> [!IMPORTANT]  
> L’applet de commande <strong>Move-CsLegacyUser</strong> nécessite que les noms d’utilisateurs soient correctement formés, sans espaces de début ou de fin. Vous ne pouvez pas déplacer un compte d’utilisateur à l’aide de l’applet de commande <strong>Move-CsLegacyUser</strong> s’il contient des espaces de début ou de fin.

Lorsque vous déplacez un utilisateur vers un pool Lync Server 2013, les données de l’utilisateur sont déplacées vers la base de données principale associée au nouveau pool.

> [!IMPORTANT]  
> Cela comprend des réunions actives créées par l’utilisateur hérité. Par exemple, si un utilisateur hérité a configuré une conférence <strong>ma réunion</strong> , cette conférence sera encore disponible dans le nouveau pool Lync Server 2013 après que l’utilisateur a été déplacé. Les détails permettant d’accéder à cette réunion seront toujours les mêmes <strong>URL de conférence et ID de conférence</strong> . La seule différence tient au fait que la conférence est désormais hébergée dans le pool Lync Server 2013 et pas dans le pool Office Communications Server 2007 R2.

> [!NOTE]  
> L’hébergement d’utilisateurs sur Lync Server 2013 ne vous oblige pas à déployer des clients mis à niveau en même temps. Les nouvelles fonctionnalités sont disponibles pour les utilisateurs uniquement lorsqu’ils ont effectué la mise à niveau vers le nouveau logiciel client.

## Tâche post-migration

1.  Une fois que vous avez déplacé des utilisateurs, vérifiez la stratégie de conférence qui leur est attribuée.

2.  Pour garantir que les réunions organisées par les utilisateurs hébergés sur Lync Server 2013 fonctionnent de manière transparente avec les utilisateurs fédérés hébergés sur Office Communications Server 2007 R2, la stratégie de conférence affectée aux utilisateurs migrés devrait autoriser des participants anonymes.

3.  Les stratégies de conférence qui autorisent les participants anonymes ont l’option **Autoriser les participants à inviter des utilisateurs anonymes** activée dans le Panneau de configuration Lync Server 2013 et l’option **AllowAnonymousParticipantsInMeetings** définie sur **True** dans la sortie de l’applet de commande **Get-CsConferencingPolicy** dans Lync Server Management Shell.

4.  Pour plus d’informations sur la configuration de la stratégie de conférence à l’aide de Lync Server Management Shell, reportez-vous à [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy) dans la documentation de Lync Server Management Shell.

