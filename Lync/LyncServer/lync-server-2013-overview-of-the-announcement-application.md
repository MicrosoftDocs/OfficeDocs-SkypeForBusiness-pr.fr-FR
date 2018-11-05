---
title: 'Lync Server 2013 : Vue d’ensemble de l’application d’annonce'
TOCTitle: Vue d’ensemble de l’application d’annonce
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204757(v=OCS.15)
ms:contentKeyID: 49296699
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de l’application d’annonce dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-13_

Lorsque vous déployez l’application d’annonce, vous devez configurer une table des numéros non attribués qui détermine les mesures à prendre quand une personne compose un numéro non attribué. La table des numéros non attribués contient des plages de numéros de téléphone valides pour l’organisation et spécifie l’application d’annonce qui gère chacune d’elles. Quand un appelant compose un numéro de téléphone valide pour votre organisation mais qui n’est attribué à personne, Lync Server recherche le numéro dans la table de routage des numéros non attribués, identifie la plage concernée et achemine l’appel vers l’application d’annonce spécifiée pour cette plage. L’application d’annonce répond à l’appel et lit un message audio (si vous l’avez configurée ainsi), puis déconnecte l’appel ou le transfère vers une destination prédéterminée, par exemple, un opérateur. Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer plusieurs messages audio ou transférer les destinations.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Si vous avez des numéros spécifiques qui ne sont plus utilisés et que vous voulez lire des messages personnalisés pour chacun d’eux, vous pouvez entrer ces numéros spécifiques dans la table des numéros non attribués. Par exemple, si vous avez changé le numéro du bureau de service client, vous pouvez entrer l’ancien numéro du service client et l’associer à une annonce qui indique le nouveau. Si vous voulez lire un message général à quiconque appelle un numéro non attribué (comme celui d’un employé ayant quitté votre organisation), vous pouvez entrer des plages pour toutes les extensions valides de votre organisation. La table des numéros non attribués est appelée à chaque fois qu’un appelant compose un numéro qui n’est pas actuellement attribué.

Dans Lync Server 2013, l’application d’annonce est automatiquement installée avec l’application Response Group. Les applications d’annonce et Response Group sont des composants standards d’un déploiement Voix Entreprise : lorsque vous déployez Voix Entreprise, ces deux applications sont déployées automatiquement.

