---
title: Configuration des numéros de téléphone non attribués
TOCTitle: Configuration des numéros de téléphone non attribués
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182559(v=OCS.15)
ms:contentKeyID: 49298389
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des numéros de téléphone non attribués

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans Lync Server, vous pouvez configurer la réponse aux appels entrants sur des numéros de téléphone valides pour votre organisation mais qui ne sont attribués à aucun utilisateur ou téléphone. Pour gérer ces appels, vous devez configurer une table de numéros non assignée. Vous pouvez utiliser cette table pour acheminer les appels vers une application d’annonce ou vers un serveur messagerie unifiée Exchange.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange. Pour plus d’informations sur la création d’annonces, voir <a href="lync-server-2013-create-an-announcement.md">Création d’une annonce dans Lync Server 2013</a>. Pour vérifier si vous avez configuré les paramètres de la messagerie unifiée Exchange, exécutez l’applet de commande <strong>Get-CsExUmContact</strong>. Pour plus d’informations, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</a>.

## Dans cette section

  - [Création ou modification d’une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Supprimer une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

