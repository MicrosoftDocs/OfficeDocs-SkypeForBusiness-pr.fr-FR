---
title: Vue d’ensemble de la prise d’appel de groupe
TOCTitle: Vue d’ensemble de la prise d’appel de groupe
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945623(v=OCS.15)
ms:contentKeyID: 53095399
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de la prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2013-02-12_

La prise d’appel de groupe, nouvelle fonctionnalité dans les mises à jour cumulatives pour Lync Server 2013 de février 2013, permet aux utilisateurs de répondre à des appels entrants destinés à leurs collaborateurs depuis leurs propres téléphones. Cette nouvelle fonctionnalité accroît la disponibilité de la ligne d’un utilisateur, car elle permet aux autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Quand la prise d’appel de groupe est déployée, le nombre d’appels entrants routés vers la messagerie vocale peut être réduit de manière significative, ce qui est particulièrement utile pour les appels passés par les clients qui ne font pas partie de votre organisation.

La fonctionnalité de la prise d’appel de groupe est notamment conçue pour les divisions dans des environnements de bureau ouvert. Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe.

Dans les environnements qui ne sont pas organisés en bureau ouvert ou dans lesquels les utilisateurs partageant une responsabilité commune sont relativement éloignés les uns des autres, l’appel d’équipe constitue la solution la plus appropriée. La principale différence entre la prise d’appel de groupe et l’appel d’équipe est que, dans le cas de la prise d’appel de groupe, un appel entrant ne sonne que sur le poste du destinataire, toute personne pouvant prendre l’initiative d’y répondre en composant un numéro de groupe. Dans le cas de l’appel d’équipe, l’appel sonne sur les téléphones de tous les membres de l’équipe et tout utilisateur appartenant à celle-ci peut décrocher son téléphone pour répondre à l’appel. En outre, la prise d’appel de groupe est gérée par un administrateur, via Lync Server, tandis que dans le cas de l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Lync. Ainsi, la prise d’appel de groupe permet de centraliser cet aspect de la gestion des appels.

La prise d’appel de groupe repose sur l’application de parcage d’appel. Quand vous déployez la prise d’appel de groupe, vous configurez la table des numéros d’appel parqué avec des plages distinctes de numéros d’extension définies en tant que numéros de groupe de prise d’appel. À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone. Chaque pool de serveurs frontaux où vous déployez la prise d’appel de groupe peut posséder une ou plusieurs plages de numéros de groupe de prise d’appel. Les plages de numéros de groupe doivent être uniques dans l’ensemble du déploiement Lync Server.

> [!NOTE]  
> Les plages de numéros définies en tant que numéros de prise d’appel de groupe dans la table des numéros d’appel parqué ne peuvent pas être gérées ou affichées à l’aide du Panneau de configuration Lync Server. La seule façon d’afficher toutes les plages de numéros de la table des numéros d’appel parqué consiste à utiliser Lync Server Management Shell. De même, vous ne pouvez ajouter, modifier ou supprimer des numéros de prise d’appel de groupe qu’à l’aide de Lync Server Management Shell.

Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.

> [!NOTE]  
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel.

> [!NOTE]  
> Tout utilisateur dans le déploiement Lync Server peut répondre à un appel destiné à un membre du groupe de prise d’appel, mais il doit connaître le numéro de groupe de prise d’appel exact à composer.

Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.

Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe. En d’autres termes, un appel à destination d’un utilisateur qui bénéficie de la prise d’appel de groupe sonne pour toutes les destinations configurées et un autre utilisateur peut répondre à l’appel. Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.

La prise d’appel de groupe ne permet pas de répondre aux types d’appel suivants :

  - Appels à destination d’une ligne privée

  - Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis
    
    > [!TIP]  
    > Tout utilisateur membre d’un groupe de prise d’appel peut empêcher certains appels d’être récupérés par le biais de la prise d’appel de groupe en marquant le contact en tant que contact personnel dans le client Lync. Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis. Aucun appel entrant en provenance d’un contact dont le niveau de confidentialité est défini sur Famille et amis ne peut être récupéré à l’aide de la prise d’appel de groupe.

  - Partie vidéo d’un appel audio/vidéo
    
    > [!NOTE]  
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo.

  - Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe

  - Appels routés vers un délégué

  - Appels routés vers un service Response Group

Les types d’utilisateur suivants ne peuvent pas participer à la prise d’appel de groupe. En d’autres termes, ils ne doivent pas être inclus dans un groupe de prise d’appel de groupe et ils ne peuvent pas prendre des appels destinés aux utilisateurs pour lesquels la prise d’appel de groupe est activée.

  - Utilisateurs hébergés en ligne dans un déploiement hybride

  - Utilisateurs qui ne sont pas hébergés sur un pool Lync Server 2013 bénéficiant des mises à jour cumulatives pour Lync Server 2013 de février 2013 dans un déploiement local

Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.

