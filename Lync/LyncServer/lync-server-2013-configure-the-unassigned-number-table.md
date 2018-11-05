---
title: 'Lync Server 2013 : Configuration de la table des numéros non attribués'
TOCTitle: Configuration de la table des numéros non attribués
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399053(v=OCS.15)
ms:contentKeyID: 49299257
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la table des numéros non attribués dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-30_

Dans Lync Server 2013, vous pouvez spécifier la réponse à des appels entrants sur des numéros de téléphone valides pour votre entreprise, mais qui ne sont pas attribués à un utilisateur ou un téléphone. Les appelants peuvent entendre un message, être acheminés vers une autre destination ou les deux.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre entreprise, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’entreprise, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez modifier la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, vous devez avoir défini des annonces ou configuré un standard automatique de la messagerie unifiée Exchange dans le système.

> [!TIP]  
> Lorsqu’une personne appelle un numéro non attribué, Lync Server recherche de haut en bas dans la table des numéros non attribués et utilise la première plage correspondante. Par conséquent, une action que vous voulez voir effectuée en dernier ressort doit être spécifiée pour la dernière plage de la table.

## Dans cette section

[Création ou modification d’une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Création d’une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)

