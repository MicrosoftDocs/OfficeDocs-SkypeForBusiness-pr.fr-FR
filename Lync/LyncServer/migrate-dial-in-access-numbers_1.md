---
title: Migration des numéros d’accès entrant
TOCTitle: Migration des numéros d’accès entrant
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204898(v=OCS.15)
ms:contentKeyID: 49297291
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des numéros d’accès entrant

 

_**Dernière rubrique modifiée :** 2012-09-26_

La migration des numéros d’accès entrant nécessite deux étapes : l’exécution de l’applet de commande **Import-CsLegacyConfiguration** (déjà effectuée dans [Importation des stratégies et des paramètres](import-policies-and-settings.md)) pour migrer les plans de numérotation et les autres paramètres des numéros d’accès entrant, puis l’exécution de l’applet de commande **Move-CsApplicationEndpoint** pour migrer les objets contact.

## Pour faire migrer les numéros d’accès entrant

1.  Ouvrez l’outil d’administration Office Communications Server 2007 R2.

2.  Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Forêt, cliquez sur **Propriétés** , puis sur **Propriétés de Intendant Conférence** .

3.  Sous l’onglet **Numéros de téléphone d’accès** , cliquez sur **Traité par le pool** pour trier les numéros de téléphone d’accès par leur pool associé et identifiez tous les numéros d’accès pour le pool à partir duquel vous effectuez la migration.

4.  Pour identifier l’URI SIP de chaque numéro d’accès, double-cliquez sur le numéro d’accès pour ouvrir la boîte de dialogue **Modifier le numéro de l’Intendant Conférence** et regardez sous **URI SIP** .

5.  Ouvrez Lync Server Management Shell.

6.  Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Lync Server 2013, exécutez :
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Dans l’outil d’administration Office Communications Server 2007 R2, sous l’onglet **Numéros de téléphone d’accès** , vérifiez qu’il ne reste aucun numéro d’accès entrant pour le pool Office Communications Server 2007 R2 à partir duquel vous effectuez la migration.

