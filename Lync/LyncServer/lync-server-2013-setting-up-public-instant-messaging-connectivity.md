---
title: 'Lync Server 2013 : Configuration de la connectivité PIC'
TOCTitle: Configuration de la connectivité PIC
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205041(v=OCS.15)
ms:contentKeyID: 49297897
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la connectivité PIC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. À la place, effectuez les étapes de la procédure suivante.

## Configuration de la connectivité PIC

1.  Sur le serveur frontal, ouvrez le générateur de topologie. Développez les pools de serveurs Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.

2.  Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.

3.  Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

## Pour créer une demande de certificat pour l’interface externe du serveur Edge afin de prendre en charge la connectivité PIC avec AOL

1.  Lorsque le modèle requis est à la disposition de l’autorité de certification, utilisez l’applet de commande Windows PowerShell suivante depuis le serveur Edge pour demander le certificat :
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom de certificat par défaut du modèle utilisé pour Lync Server est Serveur web. Spécifiez uniquement \<template name\> (nom du modèle) si vous devez utiliser un modèle différent du modèle par défaut.
    
    > [!IMPORTANT]  
    > Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat afin de demander le certificat à affecter au serveur Edge externe pour le service Edge d’accès. Cela est dû au fait que le modèle Serveur web de l’autorité de certification utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration EKU (utilisation avancée de la clé) sur le client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’EKU sur le client.
