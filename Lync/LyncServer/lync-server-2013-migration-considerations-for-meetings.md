---
title: Considérations de migration pour les réunions
TOCTitle: Considérations de migration pour les réunions
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61093015
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Considérations de migration pour les réunions

 

_**Dernière rubrique modifiée :** 2014-02-10_

Cette section aborde les aspects suivants :

  - Modifications des réunions dans Microsoft Lync Server 2013

  - Migration des utilisateurs en fonction de leurs besoins de conférence

  - Migration des réunions existantes et du contenu des réunions

  - Expérience utilisateur pendant la migration de Lync Server 2010

  - Expérience utilisateur pendant la migration de Office Communications Server 2007 R2

  - Compatibilité de Microsoft Lync 2013 avec les réunions des versions précédentes sur le serveur

## Modifications des réunions dans Lync Server 2013

Fonctionnalités de **Lync Server 2013.**Lync Server 2013 offre de nouvelles fonctionnalités de conférence qui deviennent disponibles pour les utilisateurs une fois leur compte déplacé vers Lync Server 2013 et après connexion au clientLync 2013. Les nouvelles fonctionnalités sont présentées dans [Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL de la réunion.** Comme dans Lync Server 2010, toutes les réunions récemment planifiées dans Lync Server 2013 ont comme préfixe d'URL https:// et les réunions existantes migrent en même temps que les comptes des utilisateurs. Cependant, Lync Server 2013 ne prend pas en charge les téléconférences Office Communications Server 2007 R2 (préfixe d'URL conf://) ni les conférences Web (préfixe d'URL meet://). Consultez « Migration des réunions depuis Office Communications Server 2007 R2 », plus loin dans cette rubrique, pour plus d'informations.

**Prise en charge des clients.**Contrairement à Lync Server 2010, Lync Server 2013 ne prend pas en charge les clients Office Communicator pour les services de conférence. Vous ne pouvez pas utiliser les clients suivants pour participer aux réunions planifiées via le complément de réunion en ligne pour Lync 2013 :

  - Office Communicator 2007 R2

  - Intendant Microsoft Office Communications Server 2007 R2

  - Office Communicator 2007

  - Office Live Meeting 2007

Lors de la migration, les utilisateurs de Office Communicator 2007 R2 doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013 jusqu'à la mise à niveau de leurs clients. À noter que les utilisateurs de Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant avec Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais les fonctionnalités de conférence ne sont pas prises en charge.


## Migration des utilisateurs en fonction de leurs besoins de conférence

**Organisateurs de réunions fréquentes.**Envisagez de migrer les organisateurs de réunions fréquentes au début du processus afin qu'ils puissent tirer parti des nouvelles fonctionnalités Lync Server 2013 et Lync 2013 présentées dans [Nouvelles fonctionnalités de conférence dans Lync Server 2013](lync-server-2013-new-conferencing-features.md) et [Nouveautés pour les clients dans Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Utilisateurs de Live Meeting.**Si vous effectuez une migration depuis Office Communications Server 2007 R2 et que vous avez des utilisateurs qui nécessitent des fonctionnalités de conférence Web spécifiques à Live Meeting, en particulier la prise en charge de réunions de taille importante et de salles virtuelles, vous disposez des options suivantes :

  - Conseillez aux organisateurs d'utiliser le service Live Meeting, dans le cas où il est disponible dans votre organisation.

  - Laissez les organisateurs hébergés sur la version précédente de Office Communications Server, afin qu'ils continuent à planifier des conférences Web Live Meeting basées sur le serveur.

## Migration des réunions existantes et du contenu des réunions

## Migration des réunions à partir de Lync Server 2010

Lorsque vous déplacez un utilisateur de Lync Server 2010 vers Lync Server 2013, les informations suivantes suivent le compte de l'utilisateur :

  - Les réunions déjà planifiées par l'utilisateur. Elles incluent les répertoires de conférence et les données des conférences.

  - Le code confidentiel (PIN) personnel de l'utilisateur. Le code confidentiel (PIN) actuel de l'utilisateur reste valable jusqu'à ce qu'il expire ou que l'utilisateur demande un nouveau code confidentiel.

Cependant, les informations suivantes du compte de l'utilisateur ne sont pas transférées sur le nouveau serveur :

  - Le contenu de la réunion, par exemple les présentations PowerPoint, le contenu du tableau blanc et les données des sondages

Pour déplacer le contenu qui a été partagé au cours des réunions, utilisez le paramètre MoveMeetingContent de l'applet de commande Move-CsUser. Pour plus d'informations sur l'utilisation de cette applet de commande, consultez [Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser) dans la documentation des applets de commande de Lync Server 2013.

## Migration des réunions à partir de Office Communications Server 2007 R2

Les réunions Office Communications Server 2007 R2 sont soit des téléconférences (préfixe d'URL conf://) soit des conférences Web (préfixe d'URL meet://). Lync Server 2013 ne prend pas en charge les conférences conf:// et meet:// antérieures, et celles-ci ne sont pas migrées avec le compteur d'utilisateur. Après la migration, vous devez indiquer aux utilisateurs de mettre à jour les liens de toutes les réunions en ligne qu'ils ont éventuellement planifiées. Ils peuvent le faire après l'installation du client Lync 2013 en ouvrant une invitation à la réunion planifiée, ce qui met à jour l'URL de la réunion, et en renvoyant l'invitation aux participants.

## Expérience utilisateur pendant la migration de Lync Server 2010

Cette section aborde l'expérience de conférence des utilisateurs lors de la migration à partir de Lync 2010. Pour plus de détails sur la manière dont les clients Lync Server 2013 coexistent et interagissent avec les versions client et serveur précédentes, consultez [Interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Participation aux réunions Lync Server 2010 avec un client Lync 2013

Lors de la migration à partir de Lync Server 2010, il peut y avoir une période de coexistence quand les utilisateurs participent aux réunions de Lync Server 2010 avec un client Lync 2013. Ces utilisateurs ont accès aux fonctionnalités du client Lync 2013, aux exceptions près suivantes :

  - Dans les options de gestion des **Participants**, qui sont accessibles en pointant vers l'icône des personnes dans la fenêtre de la réunion, l'option **Aucune messagerie instantanée de réunion** ne fonctionne pas.

  - La vue Galerie ne fonctionne pas dans les conférences vidéo. L'utilisateur ne voit que le haut-parleur actif, et non pas tous les haut-parleurs. Dans la liste des options **Choisir une disposition**, **Vue Galerie** n'est pas disponible

  - La liste des participants s'affiche par défaut dans les conférences vidéo.

  - Quand vous effectuez un clic droit sur un utilisateur dans la liste des participants, les options de gestion des participants **Verrouiller les actualités vidéo** et **Épingler à la galerie** ne sont pas disponibles.

## Expérience utilisateur pendant la migration de Office Communications Server 2007 R2

Cette section aborde l'expérience de conférence des utilisateurs lors de la migration à partir Office Communications Server 2007 R2, à la fois avant et après l'installation de Lync 2013. Pour plus d'informations sur la façon dont les clients Lync Server 2013 coexistent et interagissent avec les versions client et serveur précédente, consultez [Interopérabilité des clients dans Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

## Après la migration du compte utilisateur et avant l'installation de Lync 2013

Une fois l'utilisateur migré vers le serveur Lync Server 2013, mais avant l'installation des nouveaux clients, les utilisateurs Office Communicator 2007 R2 peuvent continuer à utiliser leur client existant avec Lync Server 2013 pour les fonctionnalités de présence et de messagerie instantanée, mais les fonctionnalités de conférence ne sont pas prises en charge.

## Après la migration du compte d'utilisateur et après l'installation de Lync 2013

Lorsqu'un utilisateur migré installe Lync 2013, le complément de réunion en ligne pour Lync 2013 est également installé. Cela génère les effets suivants :

  - Toutes les réunions planifiées ensuite utilisent le nouveau format de réunion, avec une adresse https:// au lieu d'une adresse Live Meeting meet:// héritée.

  - Lors d'un déploiement Lync 2013 géré par le service informatique, l'administrateur a la possibilité de désinstaller le complément de conférence pour Microsoft Office Outlook, qui sert à planifier les réunions basées sur le service et le serveur Live Meeting. Cependant, certains utilisateurs doivent peut-être continuer à planifier les réunions du service Live Meeting. Dans ce cas, vous pouvez autoriser les deux compléments à coexister.

## Réunions avec des organisations fédérées qui utilisent des clients précédents

Les utilisateurs des organisations fédérées qui se servent de Microsoft Office Communicator 2007 ne peuvent pas participer aux réunions Lync Server 2013 dans votre organisation si ces réunions sont verrouillées par l'organisateur. Vous devez replanifier ces réunions dans Lync Server 2013 de sorte que lorsque les participants fédérés rejoignent la réunion à l'aide de la nouvelle URL de réunion https://, ils ont la possibilité d'utiliser Lync Web App.

