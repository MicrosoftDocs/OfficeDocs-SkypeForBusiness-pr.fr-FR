---
title: "Conf. nœud observateur pour la participation à la découverte de System Center"
TOCtitle: "Conf. nœud observateur pour la participation à la découverte de System Center"
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204704(v=OCS.15)
ms:contentKeyID: 49296362
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un nœud observateur pour la participation à la découverte de System Center

 

_**Dernière rubrique modifiée :** 2012-10-22_

Pour s’assurer que votre nœud observateur participe au processus de découverte de System Center Operations Manager, vous devez suivre la procédure ci-dessous sur un ordinateur sur lequel la console System Center Operations Manager est installée :

1.  Sous l’onglet **Administration**, cliquez sur **Géré par agent**.

2.  Cliquez avec le bouton droit sur le nom de l’ordinateur du nœud observateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.

Après avoir configuré le nœud observateur pour qu’il se comporte comme un proxy, démarrez l’ordinateur du nœud observateur. Une fois l’ordinateur redémarré, vérifiez qu’aucun événement d’erreur n’est consigné dans le journal des événements Operations Manager de cet ordinateur. Laissez l’ordinateur s’exécuter pendant 15 minutes environ, puis utilisez la console Operations Manager pour vérifier que vos ordinateurs Lync Server sont répertoriés sous la catégorie **Lync**.

