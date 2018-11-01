---
title: 'Lync Server 2013 : Configuration d’un serveur de gestion centralisée existant'
TOCTitle: Configuration d’un serveur de gestion centralisée existant
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205315(v=OCS.15)
ms:contentKeyID: 49298992
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un serveur de gestion centralisée existant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Si vous réutilisez un serveur de gestion centralisée d’un déploiement Lync Server 2013 existant, vous devez exécuter la procédure décrite ci-après pour vérifier le bon fonctionnement de Panneau de configuration Lync Server et Windows PowerShell.

## Pour configurer un serveur de gestion centralisée existant

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Utilisez l’applet de commande **Update-CsAdminRole** pour mettre à jour les rôles RBAC (Contrôle d’accès basé sur un rôle) stockés dans le serveur de gestion centralisée.
    
    > [!NOTE]  
    > Sauf erreur, aucun résultat n’est attendu.
