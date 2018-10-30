---
title: "Lync Server 2013 : Mod. pool de serv. Edge associé à un pool de serv. front."
TOCTitle: Modification du pool de serveurs Edge associé à un pool de serveurs frontaux
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49891308
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Si un pool de serveurs Edge est défaillant mais que le pool de serveurs frontaux du même site fonctionne encore, vous devrez définir le pool de serveurs frontaux pour qu’il utilise le pool de serveurs Edge d’un autre site jusqu’à ce que le pool de serveurs Edge défaillant soit restauré.

## Modification du pool de serveurs Edge associé à un pool de serveurs frontaux

1.  Dans le générateur de topologie, accédez au nom du pool de serveurs frontaux que vous devez changer.

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés** .

3.  Dans la section **Associations** , sous **Associer le pool de serveurs Edge (pour les composants multimédias)** , utilisez la zone de liste déroulante pour sélectionner le pool de serveurs Edge que vous voulez associer à ce pool de serveurs frontaux.

4.  Cliquez sur **OK** .

## Voir aussi

#### Concepts

[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)

