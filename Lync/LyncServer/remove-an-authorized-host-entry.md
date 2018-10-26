---
title: Suppression d’une entrée hôte non autorisée
TOCTitle: Suppression d’une entrée hôte non autorisée
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204902(v=OCS.15)
ms:contentKeyID: 49297293
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une entrée hôte non autorisée

 

_**Dernière rubrique modifiée :** 2012-09-26_

Cette rubrique décrit comment supprimer une entrée d’hôte autorisé héritée (appelée *entrée d’application approuvée* dans Lync Server 2013). Vous devez supprimer les entrées d’hôtes autorisés existantes pour les passerelles SIP/CSTA dans votre déploiement Office Communications Server 2007 R2 quand vous procédez à la migration du contrôle d’appel distant vers un déploiement de Lync Server 2013. Vous devez utiliser les outils d’administration fournis avec Office Communications Server 2007 R2 pour supprimer les entrées d’hôtes autorisés existantes.

## Pour supprimer une entrée d’hôte autorisé dans un déploiement de Office Communications Server 2007 R2

1.  Ouvrez la console d’administration d’Office Communications Server 2007 R2.

2.  Développez l’arborescence et cliquez avec le bouton droit sur le pool dans lequel l’hôte autorisé a été créé.

3.  Cliquez sur **Propriétés** , puis sur **Propriétés du serveur frontal** .

4.  Cliquez sur l’onglet **Autorisation de l’hôte** .

5.  Sélectionnez un serveur, puis cliquez sur **Supprimer** .

6.  Dans **Propriétés** , cliquez sur **OK** .

