---
title: Suppression de l’association de serveurs de surveillance
TOCTitle: Suppression de l’association de serveurs de surveillance
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49891530
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression de l’association de serveurs de surveillance

 

_**Dernière rubrique modifiée :** 2012-10-04_

Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool de serveurs frontaux, le serveur frontal, Survivable Branch Appliance et le serveur Survivable Branch Server associés. Modifier les propriétés du pool de serveurs frontaux, du serveur frontal, de Survivable Branch Appliance et du serveur Survivable Branch Server permet de supprimer la dépendance. Quand la dépendance est effacée et le serveur supprimé dans le Générateur de topologie, un message vous avertit que l’objet de magasin de la base de données associée dans le Générateur de topologie est aussi sur le point d’être supprimé.

## Pour supprimer l’association du serveur de surveillance

1.  Ouvrez le serveur frontal Lync Server 2013 et le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Dans Générateur de topologie, développez **Serveurs frontaux Enterprise Edition**, **Serveurs frontaux Standard Edition** ou **Sites de succursale**, selon l’emplacement de définition du serveur de surveillance.

4.  Si le serveur Survivable Branch Server est associé, développez **Sites de succursale**, le nom du site de succursale, puis **Survivable Branch Appliances**.
    
    > [!NOTE]  
    > <strong>Survivable Branch Appliances</strong> dans l’interface utilisateur s’applique à la fois au serveur Survivable Branch Server et au Survivable Branch Appliance.

5.  Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **Modifier les propriétés**.

6.  Dans **Modifier les propriétés**, sous **Général**, sous **Associations**, décochez la case **Associer un serveur de surveillance**, puis cliquez sur **OK**.

7.  Répétez l’étape précédente pour tout autre pool, serveur ou appareil associé au serveur de surveillance.

8.  Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **Supprimer**.

9.  Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.

10. Publiez la topologie, vérifiez le statut de réplication, puis exécutez au besoin l’Assistant Déploiement de Lync Server.

