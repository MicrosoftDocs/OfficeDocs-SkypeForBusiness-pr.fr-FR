---
title: Suppression de l’association de serveurs d’archivage
TOCTitle: Suppression de l’association de serveurs d’archivage
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49891568
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de l’association de serveurs d’archivage

 

_**Dernière rubrique modifiée :** 2012-10-04_

Pour supprimer un serveur d’archivage, vous devez modifier ou effacer la dépendance vis-à-vis du pool de serveurs frontaux, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server associés. Vous devez modifier les propriétés du pool de serveurs frontaux, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Lorsque vous avez annulé la dépendance et supprimé le serveur dans le Générateur de topologie, un message vous avertit que l’objet de magasin de base de données associé dans le Générateur de topologie sera également supprimé.

## Pour supprimer l’association au serveur d’archivage

1.  Ouvrez le serveur frontal Lync Server 2013 et le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Dans le Générateur de topologie, développez **Pools frontaux Enterprise Edition** , **Serveurs frontaux Standard Edition** ou **Sites de succursale** selon l’emplacement dans lequel le serveur d’archivage est défini.

4.  Si le serveur Survivable Branch Server est associé, développez **Sites de succursale** , le nom du site de succursale, puis **Survivable Branch Appliances** .
    
    > [!NOTE]  
    > <strong>Survivable Branch Appliances</strong> dans l’interface utilisateur s’applique à la fois au serveur Survivable Branch Server et au Survivable Branch Appliance.

5.  Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur d’archivage, puis cliquez sur **Modifier les propriétés** .

6.  Dans **Modifier les propriétés** , sous **Général** , sous **Associations** , désactivez la case à cocher **Associer un serveur d’archivage** , puis cliquez sur **OK** .

7.  Répétez l’étape précédente pour tout autre pool, serveur ou appareil associé au serveur d’archivage que vous voulez supprimer.

8.  Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **Supprimer**.

9.  Dans **Supprimer les magasins dépendants** , cliquez sur **OK** .

10. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Lync Server si besoin.

